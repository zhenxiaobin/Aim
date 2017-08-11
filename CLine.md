# 走心的[C](http://www.runoob.com/cprogramming/c-tutorial.html)语言

### 程序结构
* 预处理指令
* 主函数
* 其它函数
* return 0； 终止函数

### 编译执行程序
```C
#include <stdio.h>
int main() {
  printf("Hello\n");
  return 0;
}
```
* $ gcc hello.c
* $ ./a.out
* 输出结果： Hello

### C的令牌
* 关键字、标识符、常量、字符串值，或者是一个符号
* printf("Hello, World! \n");可分解为5个单独的令牌
* 分号、注释、标识符、空格 略

### 数据类型
* 基本类型：算数类型->整数+浮点  
        * 整数  
                * char  
                * unsign char  
                * signed char  
                * int  
                * unsign int  
                * short  
                * unsigned short  
                * long  
                * unsigned long  
        * 浮点
* 枚举类型：它们也是算术类型，被用来定义在程序中只能赋予其一定的离散整数值的变量。
* void：表明没有可用的值
* 派生类型：指针、数组、结构、共用体、函数
