
```c++
std::istream f {"name-of-file"} //ofstream for output
char c;
while (f >> c) { // f>>c has value f
				// implicitly converted to bool
				// true if state of success (read succeeded, false fails
				
	std::cout << c;
}
```

Consider:
Input: the quick brown fox
Then output: thequickbrownfox
-> Stream input skips whitespace
To include whitespace:
```c++
std::ifstream f{"name-of-file"}
f >> std::noskipws;
char c;
while (f >> c) ...
```

std::endl flushes the buffer
(buffers queue up characters and make printing to stream easier)
std::endl makes everything in the buffer forced to go to the screen

std::err is unbuffered

*Note (important)*: 
- No **explicit** calls to fopen/fclose
- initializing `f({"name-of-file"})` opens the file
- when f's scope ends, the file is closed


Write "cat" in c++:

```c++
import <iostream>;
import <fstream>;
using namespace std;

void echo(istream f) {
	f >> noskipws;
	char c;
	while (f >> c) cout << c;
}

int main(int argc, char *argv[]) {
	if (argc == 1) echo(cin);
	else for (int i = 1; i < argc; ++i) {
		istream f {argv[i]};
		echo(f);
	}
}

```

This doesn't work - doesn't even compile.
Why not?

cin has type istream - echo takes an istream
f has type ifstream - is echo(f) a type mismatch?
<u>No</u>
This is actually fine.
-> ifstream is a *subtype* of istream
-> any ifstream can be treated as an istream
-> foundational concept in OOP (details later)

The error is - you can't write a function that takes an istream the way that echo does.
Why not?
Compare the following:

```c
int x;
scanf("%d", &x);
```
and
```c++
int x;
cin >> x;
```

Why doesn't `cin>>` need to take an address?
=> c++ has another pointer-like type



**References**
```c++
int y = 10;
int &z = y; // z is an lvalue reference to y
			// similar to int* const z = &y;, 
			// but with auto-dereferencing

			// int *p = &z -> gives the address of y
```

In all cases, z acts as if it were y.
z is an <u>alias</u> for y

lvalue references <u>must</u> be initialized, and <u>must</u> be initialized to something that has an address:
```c++
int &z = y //OK
int &z = 4 //WRONG
int &z = x + y // WRONG
```

Cannot: 
- create a ptr to a reference
	Reference to ptr OK. `int * & p`
- create a ref to a ref (will compile though - means something different)
- create an array. of refs. 

Can:
- Pass as function params.
	```c++
	void inc(int &n) {
		++n;
	}
```
`cin>>` works because x is passed as a reference.
```c++
istream& operator>>(istream &in, int &n);
```

Now consider: 
```c++
struct ReallyBig {...};
int f(ReallyBig rb){...} // don't have to say "struct ReallyBig rb"
// rb is passed by value, copies the struct.

int g(ReallyBig &rb) {...} 
// passed by ref, no copy, fast. But could propagate changes to rb to the caller

int h(const ReallyBig &rb) {...}
// h can't change rb

// Prefer pass-by-const-ref over pass-by-value for anything larger than a ptr
// unless the function needs to make a copy anyway.
```

