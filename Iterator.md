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
- iter->mem:deferences iter and fetches the member named *mem* form the underlying element. equivalent to (\*iter).mem.
- ++iter:increments iter to refer to the next element in the container.
```C++
for (auto it = s.begin();it != s.end() && !isspace(*it);++it)	//process characters in s until we run out of th echaracters or we hit a whitespace
	*it = toupper(*it)	//capitalize the current character
```
- --inter:decrements iter to refer to th eprevious element in the container.
- iter1 == iter2/inter1 != inter2:compares two interators for equality.\[two iterators are equal if they denote the same element or if they are the off-the-end iterator for the same container.\]
2. iterator types
- iterator and const_iterator : A *const_iterator* behaves like a const pointer. Like a const pointer, a const_interator may read but not write the eleme nt it denotes.
```C++
vector<int>::iterator it;	   // it can read and write vector<int> elements
string::interator it2;	  // it2 can read and write characters in a string
vector<int>::const_iterator v3;	// it3 can read but not write elements
string::const_iterator v4	  // it4 can read but not write characters
```
3. the begin and end operations
p157