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
* 字符串：使用null或\'0'终止的一维字符数组 char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
* 等价：char hello[] = "Hello";
* strcpy(s1, s2) -> 复制字符串2到1
* strcat(s1, s2) -> 连接字符2到1的末尾
* strlen(s1) -> 字符串1的长度
* strchar(s1, ch) -> 返回一个指针，指向ch在字符串中第一次出现的位置
* strstr(s1, s2) -> 返回一个指针，指出字符串1第一次出现2的位置

### C结构体
* 结构体：允许存储不同类型的变量
* 语句格式： struct 结构体名称 { 内含不同类型变量 } 一个或多个结构体变量，可选;
* 访问结构成员：book.title
* 结构体作为函数参数：void printBook(struct 结构体名 参数名);
* 指向结构的指针：struct Book \*struct_pointer; 存储结构体变量的地址
* struct_pointer = &book;
* 使用->访问成员：struct_pointer->title;      printBook( &Book1 );  void printBook( struct Books *book );

* 位域：有些信息在存储时，并不需要占用一个完整的字节，而只需占几个或一个二进制位。
* 用 1 位二进位存放一个开关量时，只有 0 和 1 两种状态。
* 读取外部文件格式——可以读取非标准的文件格式。例如：9 位的整数。
* struct 位域结构名 { 类型说明符 位域名: 位域长度; ...; ... };
* 一个位域必须存储在同一个字节中，不能跨两个字节。如一个字节所剩空间不够存放另一位域时，应从下一单元起存放该位域。也可以有意使某位域从下一单元开始。例如：    unsigned  :4;  空域形式

### C共用体
* 共用体是一种特殊的数据类型，允许您在相同的内存位置存储不同的数据类型
* union [union tag] { member definition; member definition;  ... member definition; } [one or more union variables];
* 访问共用体成员：union Data data; data.i;
* 只能保留最大的成员那么大小的内存

### 位域
* 位域：指定字节来进行存储

### C Typedef
* 给原有类型起一个新的名字 typedef unsigned char BYTE;
* typedef 仅可以为类型定义别名。#define还可以为数值定义别名
* typedef编译器执行解释、#define预编译器处理

### C输入输出
* stdin:标准输入
* stdout：标准输出
* stderr：标准错误
* printf();
* scanf();
* 格式化输出：("%f, f);
* 格式化输入:("%f", &f);给地址所在地赋值
* getChar() putChar() 单一字符操作
* gets(char \*s) puts(const char \*s)

### C文件读写
* 打开文件： File \*fopen(const char \* fileName, const char \* mode);
* mode:r读取 w写 r+读写 w+读写，已存在截断为0长度 a+读写。读取从开头，写入只能追加
* 处理二进制文件Mode:"rb", "wb", "ab", "rb+", "r+b", "wb+", "w+b", "ab+", "a+b"
* 关闭文件：  int fclose( FILE \*fp ); 错误返回EOF，定义的常量
* 下面是把字符写入到流中的最简单的函数：int fputc( int c, FILE \*fp );
* 把一个以 null 结尾的字符串写入到流中 int fputs( const char *s, FILE *fp );
* 读取文件 int fgetc( FILE \* fp );
* char \*fgets( char \*buf, int n, FILE \*fp );
* 二进制输入和输出:
```C
size_t fread(void *ptr, size_t size_of_elements, 
             size_t number_of_elements, FILE *a_file);
              
size_t fwrite(const void *ptr, size_t size_of_elements, 
             size_t number_of_elements, FILE *a_file);
```

### C预处理器
* 编译过程中一个单独的步骤。文本替换工具。编译之前完成所需要的处理
* #define 定义宏
* #include包含源代码文件
* #undef取消已定义宏
* #ifdef若宏已定义返回真
* #ifndef若宏未定义返回真
* #if如果给定条件为真则执行以下代码
* #else上一条替代方案
* #elif
* #endif结束一个ifelse模块
* #error遇到标准错误时输出错误信息
* #pragma标准化方案向编译器发送特殊命令
* \_\_DATE\_\_  TIME FILE LINE STDC
* 宏延续运算符 \\单行容纳不下则在下一行继续

### C头文件
* #include <系统文件>
* #include "用户头文件"
* 只引用一次头文件 #ifndef HEADER_FILE #define HEADER_FILE ... #endif
* 有条件引用 #if #elif #elif #endif

### C强制类型转换
* 格式：(type_name)expression
* 整数提升：17 + 'c' = 116 'c'转化为ascii值
* 算数转换 int->unsigned int->long->unsigned long->long long->float->double->long double

###  C错误处理
* perror 您传给他的字符串，后跟冒号，空格和当前错误的描述语句
* strerror() 返回一个指针，指向当前错误的文本形式
* fprintf(stderr, "打开文件错误: %s\n", strerror( errnum ));输出错误的方法

### C递归
* 自身调用自身。阶乘、菲波那切数列等实例、汉诺塔
* 未经精心设计，一般不要使用递归

### C可变参数
* 函数 func() 最后一个参数写成省略号，即三个点号（...），省略号之前的那个参数是 int，代表了要传递的可变参数的总数。为了使用这个功能，您需要使用 stdarg.h 头文件，该文件提供了实现可变参数功能的函数和宏。
* 在函数定义中创建一个 va_list 类型变量，该类型是在 stdarg.h 头文件中定义的。
* 使用 int 参数和 va_start 宏来初始化 va_list 变量为一个参数列表。宏 va_start 是在 stdarg.h 头文件中定义的。
* 使用 va_arg 宏和 va_list 变量来访问参数列表中的每个项。
* 使用宏 va_end 来清理赋予 va_list 变量的内存。

### C内存管理
* C 中的动态内存管理。C 语言为内存的分配和管理提供了几个函数。这些函数可以在 <stdlib.h> 头文件
* void \*calloc(int num, int size);在内存中动态地分配 num 个长度为 size 的连续空间，并将每一个字节都初始化为 0。所以它的结果是分配了 num*\size 个字节长度的内存空间，并且每个字节的值都是0。
* void free(void \*address); 该函数释放 address 所指向的内存块,释放的是动态分配的内存空间
* void \*malloc(int num); 在堆区分配一块指定大小的内存空间，用来存放数据。这块内存空间在函数执行完成后不会被初始化，它们的值是未知的。
* void \*realloc(void \*address, int newsize); 该函数重新分配内存，把内存扩展到 newsize。
* 使用 free() 函数释放内存 free(description);

#
