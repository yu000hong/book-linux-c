# 如何快速查询函数所在的头文件

**我们可以使用系统自带的`man`命令来查询函数所在的头文件！**

**例如：**

想知道getenv()方法的具体定义，那么使用`man 3 getenv`命令；

想知道sleep()方法的具体定义，可以使用`man 3 sleep`命令；

想知道getpid()方法的具体定义，可以使用`man 2 getpid`命令；


**man手册一共分为8个不同的节：**

Section | Description
:--|:--
1 | General commands
2 | System calls
3 | Library functions, covering in particular the C standard library
4 | Special files (usually devices, those found in /dev) and drivers
5 | File formats and conventions
6 | Games and screensavers
7 | Miscellanea
8 | System administration commands and daemons
