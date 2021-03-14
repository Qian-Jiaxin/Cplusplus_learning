# auto
<https://zh.wikipedia.org/zh-cn/Auto_(C%2B%2B)>
1. 声明变量时根据初始化表达式自动推断该变量的类型
```C++
std::vector<int> vect
for (auto it = vect.begin();it != vect.end();++it)	//it的类型是std::vector<int>::iterator
	std::cin>>*it;
```
2. 声明函数时函数返回值的占位符

# decltype
<https://zh.wikipedia.org/wiki/Decltype>
对于变量或函数参数作为表达式，右decltype推导出的类型和源码中的*定义精确匹配*
`decltype(exp()) x;`

# iterator