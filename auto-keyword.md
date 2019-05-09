# auto关键字

https://www.includehelp.com/c/automatic-auto-variables-in-c-language.aspx

我们定义在代码块或函数里面的变量叫做`局部变量`，也叫`自动变量`，他们的作用域也就是对应的代码块或函数。`auto`关键字就是用来定义自动变量的，但是我们的代码中几乎看不见这个关键字的身影，因为变量申明时默认就是自动变量。

```
int main()
{
    auto int a;
    int b;
    ....
    return 0;
}
```

代码中**a**和**b**都是自动变量！


