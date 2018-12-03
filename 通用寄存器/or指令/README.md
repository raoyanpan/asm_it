## OR指令

> 1、OR r/m8,imm8
- **OR CL,0x55**
* ***运行前***
<div align="center"> <img src="../../images/or//_1_or_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_2_or_r8_imm8.png" width=""/> </div><br> 

- **OR BYTE PTR DS:[0x19FFE8],0xDA**
* ***运行前***
<div align="center"> <img src="../../images/or//_3_or_m8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_4_or_m8_imm8.png" width=""/> </div><br>

> 2、OR r/m16,imm16
- **OR AX,6789**
* ***运行前***
<div align="center"> <img src="../../images/or//_5_or_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_6_or_r16_imm16.png" width=""/> </div><br> 

- **OR WORD PTR DS:[19FF90],0ABCD**
* ***运行前***
<div align="center"> <img src="../../images/or//_7_or_m16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_8_or_m16_imm16.png" width=""/> </div><br>

> 3、OR r/m32,imm32
- **OR ECX,0x12345678**
* ***运行前***
<div align="center"> <img src="../../images/or//_9_or_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_10_or_r32_imm32.png" width=""/> </div><br> 

- **OR DWORD PTR DS:[0x19FFE8],0x12345678**
* ***运行前***
<div align="center"> <img src="../../images/or//_11_or_m32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_12_or_m32_imm32.png" width=""/> </div><br>

> 4、OR r/m16,imm8
- **OR AX,0x23**
* ***运行前***
<div align="center"> <img src="../../images/or//_13_or_r16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_14_or_r16_imm8.png" width=""/> </div><br> 

- **OR WORD PTR DS:[19FFE8],1B**
* ***运行前***
<div align="center"> <img src="../../images/or//_15_or_m16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_16_or_m16_imm8.png" width=""/> </div><br>

> 5、OR r/m32,imm8
- **OR EAX,0xAA**
* ***运行前***
<div align="center"> <img src="../../images/or//_17_or_r32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_18_or_r32_imm8.png" width=""/> </div><br> 

- **OR DWORD PTR DS:[0x19FF90],0xCC**
* ***运行前***
<div align="center"> <img src="../../images/or//_19_or_m32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_20_or_m32_imm8.png" width=""/> </div><br>