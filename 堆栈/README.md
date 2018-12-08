## 堆栈

### 1、压入数据
```asm
MOV EBX,0x19FFFC ;栈底 Base
MOV EDX,0x19FFFC ;栈顶 Top
```
<div align="center"> <img src="../images/stack//_1_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_2_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_3_stack.png" width=""/> </div><br>

> 方式一
```asm
;先压入数据,再提升栈顶
MOV DWORD PTR DS:[EDX-4],0xAAAAAAAA
SUB EDX,0x4
```
<div align="center"> <img src="../images/stack//_4_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_5_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_6_stack.png" width=""/> </div><br>

> 方式二
```asm
;先提升栈顶,再压入数据
SUB EDX,0x4
MOV DWORD PTR DS:[EDX],0xBBBBBBBB
```
<div align="center"> <img src="../images/stack//_7_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_8_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_9_stack.png" width=""/> </div><br>

> 方式三
```asm
;先压入数据,再将压入数据的地址放入栈顶
MOV DWORD PTR DS:[EDX-4],0xCCCCCCCC
LEA EDX,DWORD PTR DS:[EDX-4]
```
<div align="center"> <img src="../images/stack//_10_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_11_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_12_stack.png" width=""/> </div><br>

> 方式四
```asm
;先将压入数据的地址放在栈顶,再压入数据
LEA EDX,DWORD PTR DS:[EDX-4]
MOV DWORD PTR DS:[EDX],0xDDDDDDDD
```
<div align="center"> <img src="../images/stack//_13_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_14_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_15_stack.png" width=""/> </div><br>

### 二、读取第N个数据
> 方式一
```asm
;通过Base加偏移来读取第一个压入的数据
MOV EAX,DWORD PTR DS:[EBX-4]
```
<div align="center"> <img src="../images/stack//_16_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_17_stack.png" width=""/> </div><br>

> 方式二
```asm
;通过Top加偏移来读取第二个压入的数据
MOV ECX,DWORD PTR DS:[EDX+8]
```
<div align="center"> <img src="../images/stack//_18_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_19_stack.png" width=""/> </div><br>

### 三、弹出数据
> 方式一
```asm
;先弹出数据,再降低栈顶
MOV ECX,DWORD PTR DS:[EDX+4]
ADD EDX,0x4
```
<div align="center"> <img src="../images/stack//_20_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_21_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_22_stack.png" width=""/> </div><br>

> 方式二
```asm
;先降低栈顶,再弹出数据
ADD EDX,0x4
MOV EAX,DWORD PTR DS:[EDX]
```
<div align="center"> <img src="../images/stack//_23_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_24_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_25_stack.png" width=""/> </div><br>

> 方式三
```asm
;先弹出数据,再将弹出数据的地址放入栈顶
MOV ECX,DWORD PTR DS:[EDX+4]
LEA EDX,DWORD PTR DS:[EDX+4]
```
<div align="center"> <img src="../images/stack//_26_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_27_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_28_stack.png" width=""/> </div><br>

> 方式四
```asm
;先将弹出数据的地址放入栈顶,再弹出数据
LEA EDX,DWORD PTR DS:[EDX+4]
MOV EAX,DWORD PTR DS:[EDX]
```
<div align="center"> <img src="../images/stack//_29_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_30_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_31_stack.png" width=""/> </div><br>

### 练习题
> 1、使用EBX存储栈底地址，EDX存储栈顶地址，连续存储5个不同的数.
```asm
MOV EBX,19FFFC ;栈底
MOV EDX,19FFFC ;栈顶
MOV DWORD PTR DS:[EDX],0xAAAAAAAA ;压入数据(一)
SUB EDX,0x4 ;提升栈顶
MOV DWORD PTR DS:[EDX],0xBBBBBBBB ;压入数据(二)
LEA EDX,DWORD PTR DS:[EDX-4] ;提升栈顶
SUB EDX,4 ;提升栈顶(三)
MOV DWORD PTR DS:[EDX+4],0xCCCCCCCC ;压入数据
LEA EDX,DWORD PTR DS:[EDX-4] ;提升栈顶(四)
MOV DWORD PTR DS:[EDX+4],0xDDDDDDDD ;压入数据
MOV DWORD PTR DS:[EDX],0xEEEEEEEE ;压入数据(五)
SUB EDX,4 ;提升栈顶
```
<div align="center"> <img src="../images/stack//_32_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_33_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_34_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_35_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_36_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_37_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_38_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_39_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_40_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_41_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_42_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_43_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_44_stack.png" width=""/> </div><br>

> 2、分别使用栈底加偏移、栈顶加偏移的方式读取这5个数，并存储到寄存器中.
```asm
MOV EAX,DWORD PTR DS:[EBX] ;栈顶加偏移
MOV ECX,DWORD PTR DS:[EBX-4] ;栈顶加偏移
MOV EBP,DWORD PTR DS:[EBX-8] ;栈顶加偏移
MOV ESI,DWORD PTR DS:[EDX+8] ;栈底加偏移
MOV EDI,DWORD PTR DS:[EDX+4] ;栈底加偏移
```
<div align="center"> <img src="../images/stack//_45_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_46_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_47_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_48_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_49_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_50_stack.png" width=""/> </div><br>

> 3、弹出这5个数，恢复栈顶到原来的位置.
```asm
;弹出第一个数据
MOV EAX,DWORD PTR DS:[EDX] ;弹出0xEEEEEEEE
ADD EDX,4 ;降低堆栈
;弹出第二个数据
ADD EDX,4 ;降低堆栈
MOV ECX,DWORD PTR DS:[EDX-4] ;弹出0xDDDDDDDD
;弹出第三个数据
MOV EBP,DWORD PTR DS:[EDX] ;弹出0xCCCCCCCC
LEA EDX,DWORD PTR DS:[EDX+4] ;降低堆栈
;弹出第四个数据
MOV ESI,DWORD PTR DS:[EDX] ;弹出0xBBBBBBBB
;弹出第五个数据
MOV EDI,DWORD PTR DS:[EBX] ;弹出0xAAAAAAAA
;恢复堆栈
MOV EDX,EBX 
```
<div align="center"> <img src="../images/stack//_51_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_52_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_53_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_54_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_55_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_56_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_57_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_58_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_59_stack.png" width=""/> </div><br>
<div align="center"> <img src="../images/stack//_60_stack.png" width=""/> </div><br>