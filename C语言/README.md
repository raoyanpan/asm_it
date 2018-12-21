## C语言

### 无参,无返回值的函数调用
> **见Test.exe**

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
00401068   call        @ILT+5(plus) (0040100a) ;无参,调用函数

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
00401036   rep stos    dword ptr [edi] ;填充缓冲区
00401038   pop         edi
00401039   pop         esi
0040103A   pop         ebx ;恢复现场
0040103B   mov         esp,ebp
0040103D   pop         ebp ;降低堆栈
0040103E   ret ;函数返回
```

### 有参数,无返回值的函数调用
> **见Demo.exe**

```C
#include "stdafx.h"

//有参,无返回值
void plus(int x, int y)
{
	int z;
	z = x + y;
}

//程序入口
int main(int argc, char* argv[])
{
	plus(2,3);

	return 0;
}
```

```asm
00401068   push        3
0040106A   push        2
0040106C   call        @ILT+0(plus) (00401005);两个参数,调用函数
00401071   add         esp,8

00401005   jmp         plus (00401020)

00401020   push        ebp
00401021   mov         ebp,esp
00401023   sub         esp,44h ;提升堆栈
00401026   push        ebx
00401027   push        esi
00401028   push        edi ;保护现场
00401029   lea         edi,[ebp-44h]
0040102C   mov         ecx,11h
00401031   mov         eax,0CCCCCCCCh
00401036   rep stos    dword ptr [edi] ;填充缓冲区
00401038   mov         eax,dword ptr [ebp+8]
0040103B   add         eax,dword ptr [ebp+0Ch]
0040103E   mov         dword ptr [ebp-4],eax ;函数具体功能
00401041   pop         edi
00401042   pop         esi
00401043   pop         ebx ;恢复现场
00401044   mov         esp,ebp
00401046   pop         ebp ;降低堆栈
00401047   ret ;函数返回
```

### 无参数,有返回值的函数调用
> **见Demo2.exe**

```C
#include "stdafx.h"

//无参,有返回值函数
int plus()
{
	int x = 3;
	int y = 4;

	return x+ y;
}

//程序入口
int main(int argc, char* argv[])
{
	plus();

	return 0;
}
```

```asm
00401078   call        @ILT+5(plus) (0040100a) ;无参,函数调用

0040100A   jmp         plus (00401020)

00401020   push        ebp
00401021   mov         ebp,esp
00401023   sub         esp,48h ;提升堆栈
00401026   push        ebx
00401027   push        esi
00401028   push        edi ;保护现场
00401029   lea         edi,[ebp-48h]
0040102C   mov         ecx,12h
00401031   mov         eax,0CCCCCCCCh
00401036   rep stos    dword ptr [edi] ;填充缓冲区
00401038   mov         dword ptr [ebp-4],3
0040103F   mov         dword ptr [ebp-8],4
00401046   mov         eax,dword ptr [ebp-4]
00401049   add         eax,dword ptr [ebp-8] ;函数具体功能,eax为返回值
0040104C   pop         edi
0040104D   pop         esi
0040104E   pop         ebx ;恢复现场
0040104F   mov         esp,ebp
00401051   pop         ebp ;降低堆栈
00401052   ret ;函数返回
```

### 有参数,有返回值的函数调用
> **见Demo3.exe**

```C
#include "stdafx.h"

//有参数,有返回值函数
int plus(int x,int y)
{
    return x+y;
}

//程序入口
int main(int argc, char* argv[])
{
	plus(5, 6);

	return 0;
}
```

```asm
00401068   push        6
0040106A   push        5
0040106C   call        @ILT+0(plus) (00401005) ;两个参数,函数调用
00401071   add         esp,8

00401005   jmp         plus (00401020)

00401020   push        ebp
00401021   mov         ebp,esp
00401023   sub         esp,40h ;提升堆栈
00401026   push        ebx
00401027   push        esi
00401028   push        edi ;保护现场
00401029   lea         edi,[ebp-40h]
0040102C   mov         ecx,10h
00401031   mov         eax,0CCCCCCCCh
00401036   rep stos    dword ptr [edi] ;填充缓冲区
00401038   mov         eax,dword ptr [ebp+8]
0040103B   add         eax,dword ptr [ebp+0Ch] ;函数具体功能
0040103E   pop         edi
0040103F   pop         esi
00401040   pop         ebx ;恢复现场
00401041   mov         esp,ebp
00401043   pop         ebp ;降低堆栈
00401044   ret ;函数返回
```

## 练习
> **见Demo4.exe**

> **见Excel**
```C
#include "stdafx.h"

//两个任意整数加法
int plus1(int x, int y)
{
	return x + y;
}

//三个任意整数的加法
int plus2(int x,int y, int z)
{
	return x + y + z;
}

//五个任意整数的加法
int plus3(int x,int y,int z,int v, int k)
{
	int a,b;
	a = plus1(x,y);
	b = plus2(z,v,k);
	
	return a + b;
}

//程序入口
int main(int argc, char* argv[])
{
	//两个任意整数的加法
	plus1(1,2);

	//三个任意整数的加法
	plus2(3,4,5);

	//五个任意整数的加法
	plus3(6,7,8,9,10);

	return 0;
}
```

> 用__declspec(naked)裸函数实现下面的功能						

```C
#include "stdafx.h"

/*
 * 用__declspec(naked)裸函数实现下面的功能						
 * 练习目的:
 * 熟悉堆栈结构						 
 * 参数、局部变量的位置
 * 返回值存储的位置					
 *	int plus(int x,int y,int z)	
 *	{						
 *		int a = 2;					
 *		int b = 3;					
 *		int c = 4;					
 *		return x+y+z+a+b+c;					
 *	}
 */
int __declspec(naked) plus(int x,int y,int z)
{
    __asm
    {
        //保存原来栈底
        push ebp
        //提升堆栈
        mov ebp,esp
        sub esp,0x40
        //保护现场
        push edi
        push esi
        push ebx
        //填充缓冲区
        mov eax,0xcccccccc
        mov ecx,0x10
        lea edi,dword ptr ds:[ebp-0x40]
        rep stosd
        //函数核心功能
        //存储局部变量
        mov dword ptr ds:[ebp-0x4],2
        mov dword ptr ds:[ebp-0x8],3
        mov dword ptr ds:[ebp-0xc],4
        
        //参数计算
        mov eax,dword ptr ds:[ebp+0x8]
        add eax,dword ptr ds:[ebp+0xc]
        add eax,dword ptr ds:[ebp+0x10]
        
        add eax,dword ptr ds:[ebp-0x4]
        add eax,dword ptr ds:[ebp-0x8]
        add ebp,dword ptr ds:[ebp-0xc]
        
        //恢复现场
        pop ebx
        pop esi
        pop edi
        //降低堆栈
        mov ebp,esp
        pop ebp
        
        ret
    }
}

//程序入口
int main(int argc, char* argv[])
{
    plus(1,2,3);
    
    return 0;
}
```					

> 将float类型的12.5 转换成16进制
```
;整数部分
12 --> C --> 1100
;小数部分
0.5 x 2 = 1.0

1100.1 --> 1.1001   指数:3

0 00000000 00000000000000000000000
0          10010000000000000000000

127 + 3 = 130 --> 82  1000 0010

0 1000 0010 10010000000000000000000

0100 0001 0100 1000 0000 0000 0000 0000
```

> 将CallingConvention.exe逆向成C语言

> **见CallingConvention.exe**

```C

```