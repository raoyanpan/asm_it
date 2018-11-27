## MOV指令

### MOV指令释义
- **语法结构:** MOV 目标操作数,源操作数
- **作用:** 拷贝源操作数到目标操作数
*  1、源操作数可以是立即数(imm)、通用寄存器(r)、段寄存器、或者内存单元.
*  2、目标操作数可以是通用寄存器、段寄存器或者内存单元.
*  3、操作数的宽度必须一样.
*  4、源操作数和目标操作数不能同时为内存单元.

> 1、MOV r/m8,r8
- **MOV CL,BH**
* ***运行前***
<div align="center"> <img src="../../images/mov//_1_mov_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_2_mov_r8_r8.png" width=""/> </div><br>

- **MOV BYTE PTR DS:[0x19FFF0],AH**
* ***运行前***
<div align="center"> <img src="../../images/mov//_3_mov_m8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_4_mov_m8_r8.png" width=""/> </div><br>

> 2、MOV r/m16,r16
- **MOV CX,BX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_5_mov_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_6_mov_r16_r16.png" width=""/> </div><br>

- **MOV WORD PTR DS:[0x19FFF0],BX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_7_mov_m16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_8_mov_m16_r16.png" width=""/> </div><br>

> 3、MOV r/m32,r32
- **MOV ECX,EBX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_9_mov_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_10_mov_r32_r32.png" width=""/> </div><br>

- **MOV DWORD PTR DS:[0x19FFF0],EAX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_11_mov_m32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_12_mov_m32_r32.png" width=""/> </div><br>

> 4、MOV r8,r/m8
- **MOV CH,AH**
* ***运行前***
<div align="center"> <img src="../../images/mov//_13_mov_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_14_mov_r8_r8.png" width=""/> </div><br>

- **MOV AH,BYTE PTR DS:[0x19FFE8]**
* ***运行前***
<div align="center"> <img src="../../images/mov//_15_mov_r8_m8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_16_mov_r8_m8.png" width=""/> </div><br>

> 5、MOV r16,r/m16
- **MOV CX,BX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_17_mov_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_18_mov_r16_r16.png" width=""/> </div><br>

- **MOV AX,WORD PTR DS:[0x19FFE8]**
* ***运行前***
<div align="center"> <img src="../../images/mov//_19_mov_r16_m16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_20_mov_r16_m16.png" width=""/> </div><br>

> 6、MOV r32,r/m32
- **MOV ECX,EAX**
* ***运行前***
<div align="center"> <img src="../../images/mov//_21_mov_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_22_mov_r32_r32.png" width=""/> </div><br>

- **MOV EAX,DWORD PTR DS:[0x19FFE8]**
* ***运行前***
<div align="center"> <img src="../../images/mov//_23_mov_r32_m32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_24_mov_r32_m32.png" width=""/> </div><br>

> 7、MOV r8,imm8
- **MOV CL,0xFF**
* ***运行前***
<div align="center"> <img src="../../images/mov//_25_mov_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_26_mov_r8_imm8.png" width=""/> </div><br>

> 8、MOV r16,imm16
- **MOV DX,0x1234**
* ***运行前***
<div align="center"> <img src="../../images/mov//_27_mov_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_28_mov_r16_imm16.png" width=""/> </div><br>

> 9、MOV r32,imm32
- **MOV ECX,0x12345678**
* ***运行前***
<div align="center"> <img src="../../images/mov//_29_mov_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/mov//_30_mov_r32_imm32.png" width=""/> </div><br>