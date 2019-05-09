# static关键字

## 静态变量

https://www.geeksforgeeks.org/static-variables-in-c/ 

静态变量(static variable)会一直保存在内存里，而普通变量或自动变量(auto variable)会随着它所在函数的返回而销毁；

静态变量内存分配在数据段(data segment)，而不是在栈内存上；

静态变量跟全局变量一样，如果没有显示初始化，那么会被初始化为零值；

静态变量只能使用常量字面值来进行赋值；

静态全局变量的作用和静态函数一样，用于限制变量或函数的访问作用域；


## 静态函数

https://www.geeksforgeeks.org/what-are-static-functions-in-c/ 

C语言中，函数默认是全局作用域，对函数使用`static`关键字进行限定，可以将函数的作用域限制到定义它的文件中。
