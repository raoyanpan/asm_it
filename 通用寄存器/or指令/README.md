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

> 6、OR r/m8,r8
- **OR AL,CL**
* ***运行前***
<div align="center"> <img src="../../images/or//_21_or_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_22_or_r8_r8.png" width=""/> </div><br> 

- **OR BYTE PTR DS:[0x19FF84],CL**
* ***运行前***
<div align="center"> <img src="../../images/or//_23_or_m8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_24_or_m8_r8.png" width=""/> </div><br>

> 7、OR r/m16,r16
- **OR AX,CX**
* ***运行前***
<div align="center"> <img src="../../images/or//_25_or_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_26_or_r16_r16.png" width=""/> </div><br> 

- **OR WORD PTR DS:[0x19FF84],AX**
* ***运行前***
<div align="center"> <img src="../../images/or//_27_or_m16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_28_or_m16_r16.png" width=""/> </div><br>

> 8、OR r/m32,r32
- **OR EAX,ECX**
* ***运行前***
<div align="center"> <img src="../../images/or//_29_or_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_30_or_r32_r32.png" width=""/> </div><br> 

- **OR DWORD PTR DS:[0x19FF84],EAX**
* ***运行前***
<div align="center"> <img src="../../images/or//_31_or_m32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_32_or_m32_r32.png" width=""/> </div><br>

> 9、OR r8,r/m8
- **OR AH,CH**
* ***运行前***
<div align="center"> <img src="../../images/or//_33_or_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_34_or_r8_r8.png" width=""/> </div><br> 

- **OR AL,BYTE PTR DS:[0x19FF90]**
* ***运行前***
<div align="center"> <img src="../../images/or//_35_or_r8_m8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_36_or_r8_m8.png" width=""/> </div><br>

> 10、OR r16,r/m16
- **OR CX,BX**
* ***运行前***
<div align="center"> <img src="../../images/or//_37_or_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_38_or_r16_r16.png" width=""/> </div><br> 

- **OR CX,WORD PTR DS:[0x19FF90]**
* ***运行前***
<div align="center"> <img src="../../images/or//_39_or_r16_m16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_40_or_r16_m16.png" width=""/> </div><br>

> 11、OR r32,r/m32
- **OR EAX,ECX**
* ***运行前***
<div align="center"> <img src="../../images/or//_41_or_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_42_or_r32_r32.png" width=""/> </div><br> 

- **OR ECX,DWORD PTR DS:[0x19FF90]**
* ***运行前***
<div align="center"> <img src="../../images/or//_43_or_r32_m32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/or//_44_or_r32_m32.png" width=""/> </div><br>