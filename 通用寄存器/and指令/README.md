## AND指令

> 1、AND r/m8,imm8
- **AND CL,0xF8**
* ***运行前***
<div align="center"> <img src="../../images/and//_1_and_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_2_and_r8_imm8.png" width=""/> </div><br> 

- **AND BYTE PTR DS:[0x19FFE8],0x9E**
* ***运行前***
<div align="center"> <img src="../../images/and//_3_and_m8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_4_and_m8_imm8.png" width=""/> </div><br>

> 2、AND r/m16,imm16
- **AND AX,0xABCD**
* ***运行前***
<div align="center"> <img src="../../images/and//_5_and_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_6_and_r16_imm16.png" width=""/> </div><br> 

- **AND WORD PTR DS:[0x19FFE8],0x1A2D**
* ***运行前***
<div align="center"> <img src="../../images/and//_7_and_m16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_8_and_m16_imm16.png" width=""/> </div><br>

> 3、AND r/m32,imm32
- **AND EDX,0x3A11B5**
* ***运行前***
<div align="center"> <img src="../../images/and//_9_and_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_10_and_r32_imm32.png" width=""/> </div><br> 

- **AND DWORD PTR DS:[0x19FF84],0xABCD9876**
* ***运行前***
<div align="center"> <img src="../../images/and//_11_and_m32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_12_and_m32_imm32.png" width=""/> </div><br>

> 4、AND r/m16,imm8
- **AND AX,0xFF**
* ***运行前***
<div align="center"> <img src="../../images/and//_13_and_r16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_14_and_r16_imm8.png" width=""/> </div><br> 

- **AND WORD PTR DS:[0x19FF84],0xFC**
* ***运行前***
<div align="center"> <img src="../../images/and//_15_and_m16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_16_and_m16_imm8.png" width=""/> </div><br>

> 5、AND r/m32,imm8
- **AND EAX,0x99**
* ***运行前***
<div align="center"> <img src="../../images/and//_17_and_r32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_18_and_r32_imm8.png" width=""/> </div><br> 

- **AND DWORD PTR DS:[0x19FF80],0xF8**
* ***运行前***
<div align="center"> <img src="../../images/and//_19_and_m32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/and//_20_and_m32_imm8.png" width=""/> </div><br>