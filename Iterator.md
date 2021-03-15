# Iterator
1. basic operation
- \*iter:return a reference to the element denoted by the iterator iter.
```C++
string s("some string")
if(s.begin() != s.end()){	//make sure s is not empty
	auto it = s.begin();	//it denotes the first character in s
	*it = toupper(*it);		//make the character uppercase
}
//OUTPUT:Some string
```
- iter->mem:dereferences iter and fetches the member named *mem* form the underlying element. equivalent to (\*iter).mem.
```C++
for(auto it = text.cbegin();it != text.cend() && !it->empty();++it)	//print each line in text up to the first blank line
	cout<<*it<<endl;
```
- ++iter:increments iter to refer to the next element in the container.
```C++
for (auto it = s.begin();it != s.end() && !isspace(*it);++it)	//process characters in s until we run out of th echaracters or we hit a whitespace
	*it = toupper(*it)	//capitalize the current character
```
- \--inter:decrements iter to refer to th eprevious element in the container.
- iter1 == iter2/inter1 != inter2:compares two interators for equality.\[two iterators are equal if they denote the same element or if they are the off-the-end iterator for the same container.\]
2. iterator types
- iterator and const_iterator : A *const_iterator* behaves like a const pointer. Like a const pointer, a *const_interator* may read but not write the eleme nt it denotes.
```C++
vector<int>::iterator it;	   // it can read and write vector<int> elements
string::interator it2;	  // it2 can read and write characters in a string
vector<int>::const_iterator v3;	// it3 can read but not write elements
string::const_iterator v4	  // it4 can read but not write characters
```
3. the begin and end operations
- The type returned by begin and end depends on whether the objects on which they operator is const. If the object is const, then begin and end return a const_iterator; otherwise ,the object is not const, they return iterator.
```C++
vector<int> v;
const vector<int> cv;
auto it1 = v.begin();	//it1 has type vector<int>::iterator
auto it2 = cv.begin();	//it2 has type vector<int>::const_iterator
```
- To let us ask specifically for the *const_iterator* type ,the new standard introduced two new functions named `cbegin()` and `cend()`
```C++
auto it3 = v.cbegin();	//it3 has type vector<int>::const_iterator
```
4. combing dereference and member access
- If that objects has a class type, we may want to access a member of that object.For example, we might have a vector of strings and we might need to know whether a given element is empty.Assuming it is an iterator into this vector, we can check whether the string that it denote is empty as follows:
`(*it).empty()`is right, but `*it.empty()*`is wrong. Because the second one attempt to fetch the member named empty from it and there is no member named empty actually.
- To simplify expression such as this one ,the language defines the arrow operator\[the ->operator\]

p160