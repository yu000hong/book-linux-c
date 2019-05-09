# 使用bool类型

https://www.geeksforgeeks.org/bool-in-c/ 

C99标准是支持`bool`类型的，但是C语言要使用bool类型必须引入`stdbool.h`头文件，而C++却可以直接使用bool类型。

```c
int main() 
{ 
  bool arr[2] = {true, false}; 
  return 0; 
}
```

上面这段程序，如果保存为**.c**文件，那么编译就不能通过；但是若保存为**.cpp**文件，就能正常编译正常运行了。

下面我们来看看[`stdbool.h`](https://github.com/gcc-mirror/gcc/blob/master/gcc/ginclude/stdbool.h)头文件核心部分：

```
#define bool    _Bool
#define true    1
#define false   0
```

那么，`bool`和`_Bool`有什么区别呢？

> 这两种类型都是C99标准添加进来的，bool是_Bool的别名，因为C99之前bool不是保留关键字，所以使用_Bool避免命名冲突。