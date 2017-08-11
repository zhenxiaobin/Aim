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
* auto：所有局部变量默认存储类，用在函数内，只能修饰局部变量   auto int totalCount;
* register：定义存储在寄存器中，非RAM中的局部变量,没有内存位置，不可用一元运算符&，变量最大迟钝等于寄存器尺寸。具体存储位置由硬件的实现和限制，定义粗腰快速访问的变量，例如计数器  register int miles;
* static：声明周期内局部变量存储，全局变量默认存储类
* extern：提供全局变量的引用，对所有的程序文件都是可见的。多文件共享全局变量或方法

### 运算符
* 算术运算符
* 关系运算符
* 逻辑运算符
* 位运算符
* 赋值运算符
* 杂项运算符：sizeof()返回变量大小  &a返回a的实际地址  \*a指向一个变量  ?:条件表达式

### 判断
* if
* if else
* 嵌套 if else
* switch
* 嵌套switch
* ?:三元运算符

### 循环
* while
* for
* do ... while
* 嵌套循环
* 循环控制：break continue goto
* 无限循环 for( ; ; )

### C函数
* 定义：returnType functionName(param list) { body of function };
* 函数声明：int max(int a, int b); 可在主函数中调用
* 函数参数：传值调用、引用调用，传递指针

### 作用域规则
* 函数内部的局部变量
* 函数外部的全局变量
* 形参中的函数参数定义
* 初始化局部变量和全局变量
* int = 0;  char = '\0';  float = 0;  double = 0;  pointer = NULL;

### C数组
* 声明：type arrayName [arraySize]; -> double balance[40];
* 初始化数组：double balance[2] = {0, 1.0};
* 访问数组元祖：double index2 = balance[1];
* C其它数组知识

### C指针
* 指针是一个变量，值是另一个变量的地址 type \*varName;  -> int \*a;
* 使用指针：int var = 20;  int \*ip;  ip = &var;
* C中NULL指针：标准库中值为0的常量
* 指针详解等

### C函数指针
* 指向函数的指针变量
* typedef int (\*fun_point)(int, int);
* int max(int a, int b); --> int (\*p)(int, int) = &max
* 回调函数：具体理解参考如下代码
```C
#include <stdlib.h>  
#include <stdio.h>
// 回调函数
void populate_array(int *array, size_t arraySize, int (*getNextValue)(void))
{
    for (size_t i=0; i<arraySize; i++)
        array[i] = getNextValue();
}
// 获取随机值
int getNextRandomValue(void)
{
    return rand();
}
int main(void)
{
    int myarray[10];
    populate_array(myarray, 10, getNextRandomValue);
    for(int i = 0; i < 10; i++) {
        printf("%d ", myarray[i]);
    }
    printf("\n");
    return 0;
}
```

### C字符串
