# 函数指针常量 & 函数指针变量

[what does sizeof(function name) return?](https://stackoverflow.com/questions/2666392/what-does-sizeof-function-name-return)

[深入理解C语言函数指针](https://www.cnblogs.com/windlaughing/archive/2013/04/10/3012012.html)

## sizeof

**sizeof(函数指针常量) = 1  (编译器相关)**

**sizeof(函数指针变量) = 8  (64位系统)**


## 示例代码

```c
#include <stdio.h>

void (*funcA)(int); //声明也可写成：void(*funcA)(int x)，但习惯上一般不这样。
void (*funcB)(int);
void myfunc(int x); //声明也可写成：void myfunc(int);
int main()
{
    //一般的函数调用
    myfunc(100);

    //myFunc与funcA的类型关系类似于int与int *的关系。
    funcA=&myfunc; //将myFunc函数的地址赋给funcA变量
    (*funcA)(200); //通过函数指针变量来调用函数

    funcB=myfunc;
    funcB(300);

    //三个貌似错乱的调用
    funcA(400);
    (*funcB)(600);
    (*myfunc)(1000);

    printf("funcA: %p\n", funcA);
    printf("funcB: %p\n", funcB);
    printf("myfunc: %p\n", myfunc);

    return 0;
}

void myfunc(int x)
{
    printf("myfunc: %d\n",x);
}
```

**执行结果：**

```bash
$ gcc func.c -o func
$ ./func
myfunc: 100
myfunc: 200
myfunc: 300
myfunc: 400
myfunc: 600
myfunc: 1000
funcA: 0x103d82f40
funcB: 0x103d82f40
myfunc: 0x103d82f40
```

## 最后总结

1、其实，myFunc的函数名与funcA、funcB函数指针都是一样的，即都是函数指针。myFunc函数名是一个**函数指针常量**，而funcA、funcB是**函数指针变量**。

2、但函数名调用如果都得如`(*myfunc)(10)`这样，那书写与读起来都是不方便和不习惯的。所以C语言的设计者们才会设计成可允许`myfunc(10)`这种形式地调用（这样方便多了，并与数学中的函数形式一样）。

3、为了统一调用方式，funcA函数指针变量也可以funcA(10)的形式来调用。

4、赋值时，可以写成`funcA=&myfunc`形式，也可以写成`funcA=myfunc`。

5、但是在声明时，`void myfunc(int)`不能写成`void (*myfunc)(int)`，`void (*funcA)(int)`不能写成`void funcA(int)`。

6、函数指针变量也可以存入一个数组内，函数指针数组的声明方法：`int (*fArray[10])(int)`。


