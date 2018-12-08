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
MOV EBX,19FFFC
MOV EDX,19FFFC
MOV DWORD PTR DS:[EDX],0xAAAAAAAA
SUB EDX,0x4
MOV DWORD PTR DS:[EDX],0xBBBBBBBB
LEA EDX,DWORD PTR DS:[EDX-4]
SUB EDX,4
MOV DWORD PTR DS:[EDX+4],0xCCCCCCCC
LEA EDX,DWORD PTR DS:[EDX-4]
MOV DWORD PTR DS:[EDX+4],0xDDDDDDDD
MOV DWORD PTR DS:[EDX],0xEEEEEEEE
SUB EDX,4
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