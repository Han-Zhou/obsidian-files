<u>Recall:</u>
```c++
void f(const vector &v) {
	v.itemAt(0) = 4; // works! not very const ...
}
```
v is a const object - cannot change `n`, `cap`, `theVector(ptr)`
-> <u>Can</u> change items <u>pointed to</u> by `theVector`.

Can we fix this?
```c++
struct Vector {
	...
	const int& itemAt(size_t i) const;
};
const int& Vector::itemAt(size_t i) const {return theVector[i];}
```
Now `v.itemAt(0) = 4` won't compile when `v` is `const`,
But it also won't compile if `v` isn't `const`.

To fix: <u>const overloading</u>.
```c++
struct Vector {
	...
	const int& itemAt(size_t i) const; // called when object is const
	int& itemAt(size_t i); // called if object is not const
	...
};
inline const int& vector::itemAt(size_t i) const {return theVector[i];}
inline int& vector::itemAt(size_t i) {return theVector[i];}
```
inline:
- suggests to the compiler to replace the function call with the function body
- saves the cost of a function call

Now 
```c++
v.itemAt(0) = 4;
```
compiles <=> v is not const.


Now let's make it more idiomatic:
```c++
struct Vector {
	...
	const int& operator[](size_t i) const {return theVector[i];};
	// method body inside struct -> implicitly inline
	int& operator[](size_t i) {return theVector[i];};

}
ostream& operator<<(ostream &out, const Vector &v) {
	for (size_t i = 0; i < v.size(); i++) {
		out << v[i] << ' ';
	}
	return out;
}
```



# Problem 9: keep it a secret to everybody

```c++
vector v;
v.cap = 100; // sets cap without allocating memory
v.push_back(1); // undefined behavior - will likely crash
```

Interfering with ADTs:
1) Forgery - creating an object without calling a constructor function
    -Not possible once we wrote constructors
2) Tampering - accessing the internals without using a provided interface function

What's the big deal? -> <u>Invariants.</u>
invariants - statement that will always be true about an abstraction

ADTs provide + rely on invariants

-> stacks. - provide the invariant that the last item pushed is the first item popped.
-> vectors - rely on the invariant that elements `0, ..., cap - 1` are valid locations.

Can't garantee invariants if the use can interfere - program is harder to mason about
<u>Fix:</u> **encapsulation** - seal objects into "black boxes"

```c++
// vector.cc
export module vector;
namespace cs246e {
	export struct vector { // if no access specifier given: public
		private: // only accessible inside the vector class
			int *theVector;
			size_t n, cap;
		public: // accessible to all
			vector();
			size_t size() const;
			void push_back(int n);
			...
	}
}
```

```c++
// vector-impl.cc
module vector;
void increaseCap(vector &v) {...} // doesn't work anymore!
// doesn't have access to v's internals!
```


Try again...
```c++
// vector.cc
export module vector;
namespace cs246e {
	export struct vector {
		private:
			int *theVector;
			size_t n, cap;
		public:
			vector();
			...
		private:
			void increaseCap(); // now a private method
	};
}
```

structs - public default access
private default access would be better.
**class** -  exactly like struct, except private default access.
```c++
export class vector {
		int *theVector;
		size_t n, cap;
	public:
		vector();
		...
	private:
		void increaseCap();
};
```


A similar problem with linked lists:
```c++
Node n {3, nullptr}; // stack-allocated
Node m {4, &n}; // destructor for m will try to delete &n UB
```
There was an invariant - next is either `nullptr` or allocated by new

How can we achieve this? Encapsulate Node inside a "wrapper" class

```c++
class list {
	// private nested class - not accessible outside class list (Assume Big 5)
	struct Node {
		int data;
		Node *next;
	};
	Node *theList = nullptr;
	size_t len = 0;

	public:
		~list {delete theList;}
		size_t size() const {return len;}
		void push_front(int n) {
			theList = new Node{n, theList};
			len++;
		}

		void pop_front() {
			if (theList) {
				Node *tmp = theList;
				theList = theList->next;
				tmp->next = nullptr;
				delete tmp;
				len--;
			}
		}

		const int& operator[](size_t i) const {
			// loop
		}
}
```


