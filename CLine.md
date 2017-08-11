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
* 枚举类型：它们也是算术类型，被用来定义在程序中只能赋予其一定的离散整数值的变量。
* void：表明没有可用的值
* 派生类型：指针、数组、结构、共用体、函数
* 为了得到某个类型或某个变量在特定平台上的准确大小，您可以使用 sizeof 运算符。表达式 sizeof(type) 得到对象或类型的存储字节大小
* FLT_MIN最小值 FLT_MAX最大值 FLT_DIG精度
* void：void exit(){};    int rand(void) {};    
* 指针指向void：void \*代表对象的地址，而不是类型。内存分配函数 void \*malloc(size_t size)->指向void的指针，可以转换为任意数据类型

### C变量
* 定义：type variable_list; -> int i, j, k;
* 声明并初始化：int i = 5;
* 声明的时候分配了存储空间
* extern int i; 声明但不定义，没有分配存储空间
* 左值、右值

### C常量
* 字面量，固定值，执行期间不会改变
* 函数外定义常量 预处理器 #define identifier value -> #define AGE 24
* 函数内定义常量 const type variable = value; -> const int AGE = 24;
* 常量定义为大写字母是一个很好的编程实践

### C存储类
* auto：所有局部变量默认存储类，用在函数内，只能修饰局部变量
```C
{
  int count;
  auto int totalCount;
}
```
