# String
1. To use the string type ,we must include the *string* header.
```C++
#include <string>
using std::string
```
2. initialization
```C++
string s1;				// default initialization; s1 is the empty string  
string s2 = s1;			// s2 is a copy of s1  
string s3 = "hiya";		// s3 is a copy of the string literal  
string s4(10, 'c');		// s4 is cccccccccc
string s5 = "hiya";		// copy initialization
string s6("hiya");		// direct initialization
string s7(10, 'c'); 	// direct initialization; s7 is cccccccccc
string temp(10, 'c'); 	// temp is cccccccccc  
string s8 = temp; 		// copy temp into s8
```
3. basic operation
- os<<s : writes s onto os(output stream) and return os.
```C++
cout<<s<<endl
```
- is>>s : deliver is(input stream) into s and return is.	[**caution : whitespace-separated**]
```C++
cin>>s
```
- getline(is,s) : deliver is(input stream) into s and return is.	[**ignore separated sign(namely,read an entire line)**]
```C++
while (getline(cin, line))  
	cout << line << endl;  
```
- s.empty() : return true if the s is empty,otherwise returns false.
```C++
while (getline(cin, line))  
	if (!line.empty())  
		cout << line << endl;
```
- s.size() : return the number of the character of s.
- s[n] : return the character at the position n in s.
- s1+s2 : return combination of s1 and s2.
```C++
string s1 = "hello, ", s2 = "world\\n";  
string s3 = s1 + s2;	// s3 is hello, world\\n
s1 += s2;	// equivalent to s1 = s1 + s2
```
- s1=s2 : replace characters in s1 with the copy of s2.
- s1\==s2/s1!=s2 : return true or false.
4. dealing **characters** in string
- To use these functions ,we must define *cctype* header.(`#include <cctype>`)
```C++
 isalnum(c)	//return true if c is letter or digit.
 isalpha(c)	//return true if c is letter.
 isdigit(c)	//return true if c is digit.
 isxdigit(c)//return true if c is hexadecimal digit.
 isgraph(c)	//return true if c is not a spcae but is printable.
 islower(c)	//return true if c is a lowercase letter.
 isupper(c)	//return true if c is a uppercase letter.
 isspace(c)	//return true if c is a space.
 ispunct(c)	//return true if c is a punctuation character(not a character\digit\letter\printable whitespace)
```
- At the same time ,if c is a lowercase letter ,and what you need is uppercase letter ,you should call function `toupper(c)`.[/`tolower(c)`]
- **cautious:**Headers in C code have names of the form name.h ,but the C++ code versions of these headers are named c name ——they remove the .h .	
>Ordinarily, C++ programs should use the c name versions of headers and  not the name .h versions. That way names from the standard library are  consistently found in the std namespace. Using the .h headers puts the  burden on the programmer to remember which library names are inherited  from C and which are unique to C++.
>Especially ,if you want to process every characters is a string ,the best approach is to use a statement introduced by the new standard : the range for statement[[Range-based]]. 
```C++
for (declaration : expression)
	statement
```
- for example:[[NoteBook]]
```C++
string str("some string")
for (auto c : str)
	cout << c <<
```

```C++
string s("Hello World!!!");
decltype(s.size()) punct_cnt = 0;	// count the number of punctuation characters in s
for (auto c : s) 					// for every char in s
if (ispunct(c)) 					// if the character is punctuation
	++punct_cnt; 					// increment the punctuation(标点) counter
cout << punct_cnt<< " punctuation characters in " << s << endl;
```