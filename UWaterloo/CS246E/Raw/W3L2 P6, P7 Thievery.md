<u>Recall</u>:
```c++
Node &Node::operator=(const Node &other) {
	if (this == &other)
		return *this;
	// ...
}
```

<u>Alternative</u>: copy + swap idiom
```c++
import <utility>;
struct Node {
	void swap(Node &other) {
		using std::swap;
		swap(data, other.data);
		swap(next, other.next);
	}
	
	Node &operator=(const Node &other) {
		Node tmp = other;
		swap(tmp);
		return *this;
	}
}
```


# Problem 7: Thievery

<u>Consider</u>:
```c++
Node oddsOrEvens() {
	Node odds{1, new Node{3, new Node{5, nullptr}}};
	Node evens{2, new Node{4, new Node{6, nullptr}}};
	char c;
	cin >> c;
	if (c == '0') return evens;
	return odds;
}

Node n = oddsOrEvens(); // copy constructor
```
What is "other" here? -Reference to something...
-> To a <u>temporary</u> object created to hold the result of oddsOrEvens.
-> Other is a ref to this temporary.
-> Copy constructor deep-copies the data from this temporary.

<u>But</u>: 
-> the temporary is going to be destroyed anyway, as soon as the struct `Node n = __ `, it is done.
-> Wasteful to deep-copy the temp. Why not just steal the data instead? - Save the cost of a copy.
-> Need to be able to tell whether other is a ref to a temporary object or standalone object.


**Rvalue references**:  `Node &&` is a reference to a <u>temporary object</u> (rvalue) of type `Node`.
Version of the constructor that takes a `Node &&`:
```c++
struct Node {
	...
	Node(Node &&other): // called a move constructor
		data{other.data}, next{data.next} {
		other.next = nullptr;
	}
};
```

Similarly:
```c++
Node m;
...
m = oddsOrEvens(); // Assignment from temporary
```

Move assignment operator:
```c++
struct Node {
	...
	Node &operator=(Node &&other) { // steal other's data
		swap(data, other.data); // destroy my old data
		swap(next, other.next); // easy: swap without the copy
		return *this;
	}	
};
```


Can combine copy / move assignment:
```c++
struct Node {
	...
	Node &operator=(Node other) { // unified assignment operator, pass-by-value; 
	// invokes copy constructor if arg is an lvalue
	// invokes move constructor if the arg is an rvalue
	// copies <=> arg is an lvalue.
		swap(other);
		return *this;
	}
};
```


But now we consider:
```c++
struct Student {
	std::string name; //string is a class
	
	Student(const string &name): name{name} {}
	// copies arg into field(copy constructor)
};
```
What if name points to an rvalue?
```c++
	Student(string name): name{name} {}
	// copies <=> name is an lvalue, moves if rvalue.
	// but name{name} is another copy
```
name may refer to an rvalue, but it <u>is</u> an lvalue.
```c++
struct Student {
	Student(string name): name{std::move(name)} { }
};
```