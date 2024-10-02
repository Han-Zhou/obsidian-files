<u>Recall</u>:
```c++
struct Student {
	...
	Student (string name): name{std::move(name)} { }
	// now a move construction
	// std::move forces an lvalue to be treated as an rvalue
	
	Student(Student &&other): // move constructor
	name{std::move(other.name)} { }

	Student &operator=(Student other) { // unified assignment
		name = std::move(other.name); // invokes string's move assign
		return *this;
	}
};


```

If you don't define move operations, copy operations will be used.
If you do define them, they replace copy operations when the arg is a temp.


<u>Puzzle/Curiosity: what's better than O(1)?</u>
<u>Ans</u>: O(0).
Here we discover how much of the code we've built up amounts to nothing.

```c++
vector makeAVector() {returns vector{};} // (basic constructor)

vector v = makeAVector();
// copy constructor? move constructor? destructor?
```
Try in g++ - just the basic constructor runs - no copy, no move.
In many circumstances (including this one), the compiler will/must skip calling copy/move constructors.

`makeAVector` writes its result directly into the space occupied by `v` in the caller, rather than copy it later.

<u>E.g.</u>: `Student s = Student{ ... }`
-> Looks like a basic construction of a temporary + a copy/move construction
-> But the compiler is required not to make a temp object, so there is no copy/move construction - basic constructor only.

<u>E.g.</u>: `void doSomething(vector v) {...}`
-> Pass-by-value, -copy/move construction
`doSomething(makeAVector());`
-> Result of `makeAVector`, written directly into the param - no copy/move

This happens even if dropping constructor calls would change the behavior of the program (e.g. if the constructors print something)


So does that mean copy/move operations never run?
<u>Answer</u>: No, they do run, just not as often as you might expect.

(Rabbit hole time...)

**C++ value categories**
Isn't just as simple as lvalue/rvalue.
|                |   glvalues  |                     |  rvalue | 
| lvalues |                      |  xvalue.      |              |  prvalue

- *glvalues*
	-denote a storage location "generalized lvalues"
	-inclues lvalues+xvalues
- *lvavlue*
	-can be on the lhs of assignment
	-variables (including const), field references, array lookups, pointer derefs, etc.
- *xvalue*
	-"expiring values"
	-considered both rvalues and glvalues.
	-can't take its address, but denote a storage location.
- *rvalue*
	-can't be on the lhs of assignment
	-address cannot be taken
	-includes xvalues and prvalues.
- *prvalue*
	-"pure rvalues"
	-do <u>not</u> denote storage locations
	-e.g. literals, arithmetic exps, function calls with non-ref return type
	-most rvalues you would come up with are prvalues.

example for xvalue:
```c++
Student{_, _, _}.name

Student{_, _, _} -> prvalue
Student{_, _, _}.name -> xvalue
```

The rule is: prvalues do not generate temporaries (so no copy/move happens).
Only xvalues generate temporaries, so only xvalues get moved from, only xvalues and lvalues get moved from.

Before c++17, copy/move elision was optional. Now it is required, since prvalue does not create temporaries.


<u>Consider</u>:
```c++
vector f() {
	...
	return makeAVector(); // prvalue, no temporary.
}

//But consider now:
vector g() {
	vector v = makeAVector();
	... // do something with v
	return v; // not a prvalue
}
```
Could v be elided? 
Yes - the compiler could create v in the caller's frame, where the result would go. 
But v is not a prvalue, so <u>this is not required</u>


And now consider:
```c++
vector h() {
	vector v = makeAVector();
	vector w = makeAVector();
	... // do things with v + w
	if (_) {
		return v;
	}
	else {
		return w;
	}
}
```
which one of v or w would the compiler put in the caller's stack frame?
No way to know, so eliminating the temp might not be possible.
In this situation -  called <u>Named Return Value Optimization</u> - elision is allowed, but not required.


*In summary*: (Rule of 5)
If you need to customized any one of:
1. copy constructor
2. copy assignment 
3. move constructor
4. move assignment
5. destructor
Then you usually need to customize all 5.


# Problem 8: I don't like change.

Say we want to print a vector/
```c++
ostream &operator<<(ostream &out, const vector &v) {
	for (size_t i = 0; i < v.size(); ++i) {
		out << v.itemAt(i) << " ";
	}
	return out;
}
```
Won't compile! - can't call size + itemAt on a const object - what if these methods change fields?

Since they don't - declare them const:
```c++
struct Vector {
	...
	size_t size() const;
	int &itemAt(size_t i) const;
	// means these methods will not odify fields
	// => can be called on const objects
};

size_t vector::size() const {return n;}
int &vector::itemAt(size_t i) const {
	return theVector[i];
}
```
Now the loop will work.

But:
```c++
void f(const vector &v) {
	v.itemAt(0) = 4; //works!!
	// but v is not very const
}
```