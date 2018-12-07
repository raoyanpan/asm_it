## 寻址公式

### 1、寻址公式一：[立即数]
> 1、读取内存的值
```asm
MOV EAX,DWORD PTR DS:[0x19FF84]
```
<div align="center"> <img src="../images/memory//_1_1_1_memory.png" width=""/> </div><br>

<div align="center"> <img src="../images/memory//_1_1_2_memory.png" width=""/> </div><br>

> 2、向内存中写入数据
```asm
MOV DWORD PTR DS:[0x19FF88],ECX
```
<div align="center"> <img src="../images/memory//_1_2_1_memory.png" width=""/> </div><br>

<div align="center"> <img src="../images/memory//_1_2_2_memory.png" width=""/> </div><br>

> 3、获取内存编号
```asm
LEA ECX,DWORD PTR DS:[0x19FF84]
```
<div align="center"> <img src="../images/memory//_1_3_1_memory.png" width=""/> </div><br>

<div align="center"> <img src="../images/memory//_1_3_2_memory.png" width=""/> </div><br>

### 2、寻址公式一：[reg]
**【reg:代表寄存器 可以是8个通用寄存器中的任意一个】**
> 1、读取内存的值
```asm
MOV ECX,0x19FF84

MOV EAX,DWORD PTR DS:[ECX]
```
<div align="center"> <img src="../images/memory//_2_1_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_1_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_1_3_memory.png" width=""/> </div><br>

> 2、向内存中写入数据
```asm
MOV ECX,0x19FF88

MOV DWORD PTR DS:[ECX],0xAABBCCDD
```
<div align="center"> <img src="../images/memory//_2_2_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_2_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_2_3_memory.png" width=""/> </div><br>

> 3、获取内存编号
```asm
MOV EAX,ESP

LEA ECX,DWORD PTR DS:[EAX]

;或 LEA ECX,DWORD PTR DS:[ESP]
```
<div align="center"> <img src="../images/memory//_2_3_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_3_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_2_3_3_memory.png" width=""/> </div><br>

### 3、寻址公式三：[reg+立即数]
> 1、读取内存的值
```asm
MOV ECX,0x19FF84

MOV EAX,DWORD PTR DS:[ECX+4]
```
<div align="center"> <img src="../images/memory//_3_1_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_3_1_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_3_1_3_memory.png" width=""/> </div><br>

> 2、向内存中写入数据
```asm
MOV EAX,0x19FF7C

MOV DWORD PTR DS:[EAX+4],0x12345678
```
<div align="center"> <img src="../images/memory//_3_2_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_3_2_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_3_2_3_memory.png" width=""/> </div><br>

> 3、获取内存编号
```asm
LEA ECX,DWORD PTR DS:[EAX+8]
```
<div align="center"> <img src="../images/memory//_3_3_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_3_3_2_memory.png" width=""/> </div><br>

### 4、寻址公式四:[reg+reg*{1,2,4,8}]
> 1、读取内存的值
```asm
MOV EAX,0x19FF84

MOV ECX,0x2

MOV EDX,DWORD PTR DS:[EAX+ECX*4]
```
<div align="center"> <img src="../images/memory//_4_1_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_1_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_1_3_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_1_4_memory.png" width=""/> </div><br>

> 2、向内存中写入数据
```asm
MOV EAX,0x19FF84

MOV ECX,0x2

MOV DWORD PTR DS:[EAX+ECX*4],12345678
```
<div align="center"> <img src="../images/memory//_4_2_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_2_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_2_3_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_2_4_memory.png" width=""/> </div><br>

> 3、获取内存编号
```asm
LEA EDX,DWORD PTR DS:[EAX+ECX*4]
```
<div align="center"> <img src="../images/memory//_4_3_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_4_3_2_memory.png" width=""/> </div><br>

### 5、寻址公式五:[reg+reg*{1,2,4,8}+立即数]
> 1、读取内存的值
```asm
MOV EAX,0x19FF80

MOV ECX,0x2

MOV EDX,DWORD PTR DS:[EAX+ECX*4+4]
```
<div align="center"> <img src="../images/memory//_5_1_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_5_1_2_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_5_1_3_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_5_1_4_memory.png" width=""/> </div><br>

> 2、向内存中写入数据
```asm
MOV DWORD PTR DS:[EAX+ECX*4+4],0x12345678
```
<div align="center"> <img src="../images/memory//_5_2_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_5_2_2_memory.png" width=""/> </div><br>

> 3、获取内存编号
```asm
LEA EBX,DWORD PTR DS:[EAX+ECX*4+2]
```
<div align="center"> <img src="../images/memory//_5_3_1_memory.png" width=""/> </div><br>
<div align="center"> <img src="../images/memory//_5_3_2_memory.png" width=""/> </div><br>