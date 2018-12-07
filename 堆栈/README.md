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