# Gcc

C, C++, Objective-C, Fortran, Ada, Go, and D 언어를 컴파일 할 수 있는 컴파일러 입니다.


## 설치
```
$ su
# yum install gcc
```

hello.c
```
#include <stdio.h>
int main()
{
   // printf() displays the string inside quotation
   printf("Hello, World!\n");
   return 0;
}
```

코드 컴파일과 실행
```
$ gcc hello.c
$ ./a.out
```

Output
```
Hello, World!
```
