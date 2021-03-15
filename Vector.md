# Vector
1. To use a *vector* ,we must include the appropriate header.
```C++
#include <vector>
using std::vector
```
2. initialization
```C++
vector<T> v1		//vector that holds objects of type T.Default initialization - v1 is empty.
vector<T> v2(v1)	//v2 has copy of each element in v1.
/* Equivalent to vector<T> v2 = v1 */
vector<T> v3(n,val)	//v3 has n elements with value val.
vector<T> v4(n)		//v4 has n copies of a value-initialized object.
vector<T> v5{a,b,c...}	//v5 has as many elements as there are initializers.
/* vector<T> v5 = {a,b,c...} */
```
**caution:**`vector<string> v1{"a","an","the"}`is right, but `vector<string> v2("a","an","the")`is wrong. 
3. basic operation
- v.empty():returns true if v is empty;otherwise returns false.
- v.size():returns the number of elements in v.
- v.push_back(t):adds an element with the value t to the end of v.
- v\[n\]:returns a reference to the element at position n in v.
- v1=v2:replaces the elements in v1 with a copy of the elements in v2.
- v1={a,b,c...}:replace the elements in v1 with a copy of elements in the comma-seperated list.

**caution:**

situation 1:
```C++
vector<int> ivec;		// empty vector
cout << ivec[0];		// error: ivec has no elements!
vector<int> ivec2(10);	// vector with ten elements
cout << ivec2[10];		// error: ivec2 has elements 0 . . 9
```
situation 2:
```C++
vector<int> ivec;	// empty vector
for (decltype(ivec.size()) ix = 0; ix != 10; ++ix)
	ivec[ix] = ix;	// disaster: ivec has no elements
	
for (decltype(ivec.size()) ix = 0; ix != 10; ++ix)  
	ivec.push\_back(ix); 	// ok: adds a new element with value ix
```
