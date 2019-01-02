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
#include "stdafx.h"

int __cdecl plus2(int a,int b)
{
    return a + b;
}

int __stdcall plus1(int a,int b,int c)
{
    return a + b + c;
}

int __fastcall plus(int a,int b,int c,int d,int e)
{
	int x,y;

	x = plus1(a,b,c);
    
    y = plus2(a,b);
    
    return plus2(x,y);
}


//程序入口
void main(int argc, char* argv[])
{
    int a;
    a = plus(1,3,4,6,7);
    
    printf("%d\n", a);
}
```

> 定义4个int类型的全局变量，分别是g_x,g_y,g_z,g_r,使用if..else..分支语句，将最大的值存储到g_r中
> int g_x = 5;	
> int g_y = 4;	
> int g_z = 7;	
> int g_r = 0;	
```C
#include "stdafx.h"

void Max()
{
	int g_x = 5;	
	int g_y = 4;	
	int g_z = 7;	
	int g_r = 0;	

	if(g_x > g_r) {
		g_r = g_x;
	}

	if(g_y > g_x) {
		g_r = g_y;
	}

	if(g_z > g_x) {
		g_r = g_z;
	}
}

//程序入口
int main(int argc, char* argv[])
{
	Max();
	return 0;
}
```

> 找出数组里面最大的值,并存储到全局变量中(if..esle)					
> int arr[4] = {2,5,7,9};					
> int g_r;					
```C
int arr[4] = {2,5,7,9};
int g_r;

void ArrMax()
{
	if(arr[0] < arr[1]) {
		g_r = arr[1];
	}else {
		g_r = arr[0];
	}

	if(g_r < arr[2]) {
		g_r = arr[2];
	} 

	if(g_r < arr[3]) {
		g_r = arr[3];
	}
}
```

> 将数组所有的元素相加，将结果存储到g_r中
> int arr[10] = {2,5,7,9,22,4,8,22,3,18};
> int g_r;
```C
int arr[10] = {2,5,7,9,22,4,8,22,3,18};
int g_r;

int ArrMax()
{
	
	for(int i=0;i<10;i++) {
		g_r += arr[i];
	}
	printf("%d\n",g_r);
	return 0;
}
```

> 俩俩比较数组的值，将最大的一个存储到数组的最后一个位置(要求使用for循环实现)
> int arr[10] = {2,7,5,9,22,4,8,22,3,18};
> int g_r;
```
实现过程：
1、先比较2 7 因为2比7小 所有不交换位置
2、再比较7 5 7比5大 所以讲7的位置和5的位置互换，也就是将5存储到7的位置，将7存储到5的位置
3、再比较7 9 7比9小 不交换位置
4、再比较9 22 9比22小 交换位置
5、一直重复上面的过程，最后22存储在数组的最后一个位置，程序结束
```

```C
int ArrMax()
{
	int length = 10;

	for(int j=0;j<length-1;j++){
		for(int i=0;i<length-1-j;i++) {
			if(arr[i] >= arr[i+1]){
				int t = arr[i];
				arr[i] = arr[i+1];
				arr[i+1] = t;
			}
		}
	}
	return 0;
}
```

> 全局变量 局部变量 参数

> **全局变量: 基址**
- 程序编译完成后地址就已经确认

- 全局变量的值可以被所有函数修改,里面存储的是最后一次修改的值

- 全局变量所占内存会一直存在,直到整个进程结束

- 全局变量的识别
 - MOV 寄存器,BYTE/WORD/DWORD PTR DS:[0x12345678]
 - 通过寄存器的宽度,或者BYTE/WORD/DWORD 来判断全局变量的宽度

> **局部变量**
- 局部变量在程序编译完成后并没有分配固定的地址

- 只有所属的程序被调用了才会分配内存地址

- 局部变量只能在函数内部使用,函数A不能使用函数B的局部变量

- 局部变量的识别
 - ebp-0x4 或 esp+0x44
 
```asm
;调用处代码
push        5								
push        4								
call        0040100f								
add         esp,8
	
;函数内部
                                                ;函数内部功能分析：		
00401030   push        ebp								
00401031   mov         ebp,esp                  ;1、分析参数：		
00401033   sub         esp,44h					[ebp+8]:X [ebp+0Ch]:Y		
00401036   push        ebx								
00401037   push        esi								
00401038   push        edi                      ;2、分析局部变量		
00401039   lea         edi,[ebp-44h]			[ebp-4]	= eax = [004225c4]			
0040103C   mov         ecx,11h								
00401041   mov         eax,0CCCCCCCCh								
00401046   rep stos    dword ptr [edi]								
00401048   mov         eax,[004225c4]           ;3、分析全局变量		
0040104D   mov         dword ptr [ebp-4],eax	[004225c4] G						
00401050   mov         ecx,dword ptr [ebp+8]								
00401053   cmp         ecx,dword ptr [ebp+0Ch]								
00401056   jg          00401064								
00401058   mov         edx,dword ptr [ebp+0Ch]  ;4、功能分析		
0040105B   add         edx,dword ptr [ebp-4]	如果X<=Y,那么执行:						
0040105E   mov         dword ptr [004225c4],edx	00401058   mov         edx,dword ptr [ebp+0Ch] 			
00401064   pop         edi					    0040105B   add         edx,dword ptr [ebp-4]	
00401065   pop         esi                      0040105E   mov         dword ptr [004225c4],edx		
00401066   pop         ebx                      ;5、返回值分析								
00401067   mov         esp,ebp                      无								
00401069   pop         ebp								
0040106A   ret                                  ;6、还原成C函数		
```

```C
//还原成C函数
#include "stdafx.h"

int G;

void Test(int x,int y)
{
	int z = G;

	if(x <= y){
		G = y + z;
	}
}

//程序入口
int main(int argc, char* argv[])
{
	Test(4,5);

	return 0;
}
```

```asm
004010B0   push        ebp							    函数内部功能分析：	
004010B1   mov         ebp,esp								
004010B3   sub         esp,48h							1、分析参数：	
004010B6   push        ebx								[ebp+8]:X [ebp+0Ch]:Y
004010B7   push        esi								
004010B8   push        edi								
004010B9   lea         edi,[ebp-48h]                    2、分析局部变量	
004010BC   mov         ecx,12h							[ebp-4] = eax = G
004010C1   mov         eax,0CCCCCCCCh					[ebp-8] = 2			
004010C6   rep stos    dword ptr [edi]								
004010C8   mov         eax,[004225c4]								
004010CD   mov         dword ptr [ebp-4],eax            3、分析全局变量	
004010D0   mov         dword ptr [ebp-8],2				[004225c4]				
004010D7   mov         ecx,dword ptr [ebp+8]			4、功能分析						
004010DA   cmp         ecx,dword ptr [ebp+0Ch]			比较X,Y的大小					
004010DD   jl          004010e8							如果X>=Y	
004010DF   mov         edx,dword ptr [ebp-8]            004010DF   mov         edx,dword ptr [ebp-8] 
004010E2   add         edx,1							004010E2   add         edx,1	
004010E5   mov         dword ptr [ebp-8],edx			004010E5   mov         dword ptr [ebp-8],edx					
004010E8   mov         eax,dword ptr [ebp+8]			如果X<Y					
004010EB   cmp         eax,dword ptr [ebp+0Ch]          004010F0   mov         ecx,dword ptr [ebp-8]	
004010EE   jge         004010fb							004010F3   mov         dword ptr [004225c4],ecx	
004010F0   mov         ecx,dword ptr [ebp-8]			否则					
004010F3   mov         dword ptr [004225c4],ecx			004010FB   mov         edx,dword ptr [ebp-4]					
004010F9   jmp         00401107							004010FE   add         edx,dword ptr [ebp-8]
004010FB   mov         edx,dword ptr [ebp-4]			00401101   mov         dword ptr [004225c4],edx
004010FE   add         edx,dword ptr [ebp-8]			5、返回值分析					
00401101   mov         dword ptr [004225c4],edx			无			
00401107   pop         edi								6、还原成C函数
00401108   pop         esi								
00401109   pop         ebx								
0040110A   mov         esp,ebp								
0040110C   pop         ebp								
0040110D   ret								            
```
```C
#include "stdafx.h"

int g;

void Test(int x,int y)
{
	int a = g;
	int b = 2;

	if(x>=y){
		b = b + 1;
	}
	if(x<y){
		g = b;
	}else {
		g = a +b;
	}
}

//程序入口
int main(int argc, char* argv[])
{
	Test(4,5);

	return 0;
}
```