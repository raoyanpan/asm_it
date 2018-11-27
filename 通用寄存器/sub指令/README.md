## SUB指令

> 1、SUB r/m8,imm8
- **SUB DL,0xE4**
* ***运行前***
<div align="center"> <img src="../../images/sub//_1_sub_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_2_sub_r8_imm8.png" width=""/> </div><br>

- **SUB BYTE PTR DS:[0x19FFE8],0x4E**
* ***运行前***
<div align="center"> <img src="../../images/sub//_3_sub_m8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_4_sub_m8_imm8.png" width=""/> </div><br>

> 2、SUB r/m16,imm16
- **SUB CX,0x101**
* ***运行前***
<div align="center"> <img src="../../images/sub//_5_sub_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_6_sub_r16_imm16.png" width=""/> </div><br>

- **SUB WORD PTR DS:[19FFE8],0xDC56**
* ***运行前***
<div align="center"> <img src="../../images/sub//_7_sub_m16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_8_sub_m16_imm16.png" width=""/> </div><br>

> 3、SUB r/m32,imm32
- **SUB EAX,0x11000**
* ***运行前***
<div align="center"> <img src="../../images/sub//_9_sub_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_10_sub_r32_imm32.png" width=""/> </div><br>

- **SUB DWORD PTR DS:[0x19FFE8],0x67ABDC6B**
* ***运行前***
<div align="center"> <img src="../../images/sub//_11_sub_m32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_12_sub_m32_imm32.png" width=""/> </div><br>

> 4、SUB r/m16,imm8
- **SUB CX,0xDD**
* ***运行前***
<div align="center"> <img src="../../images/sub//_13_sub_r16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_14_sub_r16_imm8.png" width=""/> </div><br>

- **SUB WORD PTR DS:[0x19FFE8],0x49**
* ***运行前***
<div align="center"> <img src="../../images/sub//_15_sub_m16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_16_sub_m16_imm8.png" width=""/> </div><br>

> 5、SUB r/m32,imm8
- **SUB ECX,0xAC**
* ***运行前***
<div align="center"> <img src="../../images/sub//_17_sub_r32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_18_sub_r32_imm8.png" width=""/> </div><br>

- **SUB DWORD PTR DS:[0x19FF88],0x1**
* ***运行前***
<div align="center"> <img src="../../images/sub//_19_sub_m32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_20_sub_m32_imm8.png" width=""/> </div><br>