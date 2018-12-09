## PUSH指令 & POP指令

### PUSH指令
> PUSH r16
```asm
MOV AX,0x1234
PUSH AX
```
<div align="center"> <img src="../../images/stack/push&pop//_1_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_2_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_3_push_pop.png" width=""/> </div><br>

> PUSH r32
```asm
MOV ECX,0x12345678
PUSH ECX
```
<div align="center"> <img src="../../images/stack/push&pop//_4_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_5_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_6_push_pop.png" width=""/> </div><br>

> PUSH m16
```asm
PUSH WORD PTR DS:[0x19FFEE];*注:须着重理解
```
<div align="center"> <img src="../../images/stack/push&pop//_7_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_8_push_pop.png" width=""/> </div><br>

> PUSH m32
```asm
PUSH DWORD PTR DS:[0x19FFF0]
```
<div align="center"> <img src="../../images/stack/push&pop//_9_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_10_push_pop.png" width=""/> </div><br>


> PUSH imm8/imm16/imm32
```asm
PUSH 0xCD
```
<div align="center"> <img src="../../images/stack/push&pop//_11_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_12_push_pop.png" width=""/> </div><br>

```asm
PUSH 0x8765
```
<div align="center"> <img src="../../images/stack/push&pop//_13_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_14_push_pop.png" width=""/> </div><br>

```asm
PUSH 0xFEDCBA98
```
<div align="center"> <img src="../../images/stack/push&pop//_15_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_16_push_pop.png" width=""/> </div><br>


### POP指令
> POP r16
```asm
POP AX 
```
<div align="center"> <img src="../../images/stack/push&pop//_17_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_18_push_pop.png" width=""/> </div><br>

> POP r32
```asm
POP EBX
```
<div align="center"> <img src="../../images/stack/push&pop//_19_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_20_push_pop.png" width=""/> </div><br>

> POP m16
```asm
POP WORD PTR DS:[0x19FFDE]
```
<div align="center"> <img src="../../images/stack/push&pop//_21_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_22_push_pop.png" width=""/> </div><br>

> POP m32
```asm
POP DWORD PTR DS:[0x19FFE4]
```
<div align="center"> <img src="../../images/stack/push&pop//_23_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_24_push_pop.png" width=""/> </div><br>

### PUSHAD指令
```asm
PUSHAD
```
<div align="center"> <img src="../../images/stack/push&pop//_25_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_26_push_pop.png" width=""/> </div><br>

### POPAD指令
```asm
POPAD
```
<div align="center"> <img src="../../images/stack/push&pop//_27_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_28_push_pop.png" width=""/> </div><br>

### 练习题
> 1、使用4种方式实现：push ecx
```asm
PUSH ECX
```
<div align="center"> <img src="../../images/stack/push&pop//_29_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_30_push_pop.png" width=""/> </div><br>

```asm
;实现push ecx,方式一
MOV DWORD PTR DS:[ESP-4],ECX
SUB ESP,0x4
```
<div align="center"> <img src="../../images/stack/push&pop//_31_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_32_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_33_push_pop.png" width=""/> </div><br>

```asm
;实现push ecx,方式二
SUB ESP,0x4
MOV DWORD PTR DS:[ESP],ECX
```
<div align="center"> <img src="../../images/stack/push&pop//_34_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_35_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_36_push_pop.png" width=""/> </div><br>

```asm
;实现push ecx,方式三
MOV DWORD PTR DS:[ESP-4],ECX
LEA ESP,DWORD PTR DS:[ESP-4]
```
<div align="center"> <img src="../../images/stack/push&pop//_37_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_38_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_39_push_pop.png" width=""/> </div><br>

```asm
;实现push ecx,方式四
LEA ESP,DWORD PTR DS:[ESP-4]
MOV DWORD PTR DS:[ESP],ECX
```
<div align="center"> <img src="../../images/stack/push&pop//_40_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_41_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_42_push_pop.png" width=""/> </div><br>

> 5、使用2种方式实现：pop ecx
```asm
POP ECX
```
<div align="center"> <img src="../../images/stack/push&pop//_43_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_44_push_pop.png" width=""/> </div><br>

```asm
;实现pop ecx,方式一
MOV ECX,DWORD PTR DS:[ESP]
ADD ESP,0x4
```
<div align="center"> <img src="../../images/stack/push&pop//_45_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_46_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_47_push_pop.png" width=""/> </div><br>

```asm
;实现pop ecx,方式二
ADD ESP,0x4
MOV ECX,DWORD PTR DS:[ESP-4]
```
<div align="center"> <img src="../../images/stack/push&pop//_48_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_49_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_50_push_pop.png" width=""/> </div><br>

```asm
;实现pop ecx,方式三
LEA ESP,DWORD PTR DS:[ESP+4]
MOV ECX,DWORD PTR DS:[ESP-4]
```
<div align="center"> <img src="../../images/stack/push&pop//_51_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_52_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_53_push_pop.png" width=""/> </div><br>

```asm
;实现pop ecx,方式四
MOV ECX,DWORD PTR DS:[ESP]
LEA ESP,DWORD PTR DS:[ESP+4]
```
<div align="center"> <img src="../../images/stack/push&pop//_54_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_55_push_pop.png" width=""/> </div><br>
<div align="center"> <img src="../../images/stack/push&pop//_56_push_pop.png" width=""/> </div><br>
