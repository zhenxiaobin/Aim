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
     * printf("Hello, World! \n");
             * 可分解为5个单独的令牌