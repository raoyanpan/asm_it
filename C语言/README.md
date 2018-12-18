## C语言

### 无参,无返回值的函数调用
```C
#include "stdafx.h"

//无参,无返回值函数
void plus()
{
}

//程序入口
int main(int argc, char* argv[])
{
	plus();
	return 0;
}
```

```asm
;无参,无返回值的函数调用
00401068   call        @ILT+5(plus) (0040100a)

0040100A   jmp         plus (00401020)

00401020   push        ebp
00401021   mov         ebp,esp
00401023   sub         esp,40h ;提升堆栈
00401026   push        ebx
00401027   push        esi
00401028   push        edi ;保护现场
00401029   lea         edi,[ebp-40h]
0040102C   mov         ecx,10h
00401031   mov         eax,0CCCCCCCCh
00401036   rep stos    dword ptr [edi] ;为缓冲区填充数据
00401038   pop         edi
00401039   pop         esi
0040103A   pop         ebx ;恢复现场
0040103B   mov         esp,ebp
0040103D   pop         ebp ;降低堆栈
0040103E   ret  ;函数返回
```