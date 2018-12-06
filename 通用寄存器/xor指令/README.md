## XOR指令

> 1、XOR r/m8,imm8
- **XOR AL,0x56**
* ***运行前***
<div align="center"> <img src="../../images/xor//_1_xor_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_2_xor_r8_imm8.png" width=""/> </div><br> 

- **XOR BYTE PTR DS:[0x19FF8C],0x7A**
* ***运行前***
<div align="center"> <img src="../../images/xor//_3_xor_m8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_4_xor_m8_imm8.png" width=""/> </div><br>

> 2、XOR r/m16,imm16
- **XOR CX,0x3456**
* ***运行前***
<div align="center"> <img src="../../images/xor//_5_xor_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_6_xor_r16_imm16.png" width=""/> </div><br> 

- **XOR WORD PTR DS:[0x19FF80],0x1A2B**
* ***运行前***
<div align="center"> <img src="../../images/xor//_7_xor_m16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_8_xor_m16_imm16.png" width=""/> </div><br>

> 3、XOR r/m32,imm32
- **XOR ECX,0x12345678**
* ***运行前***
<div align="center"> <img src="../../images/xor//_9_xor_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_10_xor_r32_imm32.png" width=""/> </div><br> 

- **XOR DWORD PTR DS:[0x19FF8C],0x87654321**
* ***运行前***
<div align="center"> <img src="../../images/xor//_11_xor_m32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_12_xor_m32_imm32.png" width=""/> </div><br>

> 4、XOR r/m16,imm8
- **XOR CX,0x34**
* ***运行前***
<div align="center"> <img src="../../images/xor//_13_xor_r16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_14_xor_r16_imm8.png" width=""/> </div><br> 

- **XOR WORD PTR DS:[0x19FF8C],0xAD**
* ***运行前***
<div align="center"> <img src="../../images/xor//_15_xor_m16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_16_xor_m16_imm8.png" width=""/> </div><br>

> 5、XOR r/m32,imm8
- **XOR ECX,0x29**
* ***运行前***
<div align="center"> <img src="../../images/xor//_17_xor_r32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_18_xor_r32_imm8.png" width=""/> </div><br> 

- **XOR DWORD PTR DS:[0x19FF90],0x35**
* ***运行前***
<div align="center"> <img src="../../images/xor//_19_xor_m32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_20_xor_m32_imm8.png" width=""/> </div><br>

> 6、XOR r/m8,r8
- **XOR CH,CL**
* ***运行前***
<div align="center"> <img src="../../images/xor//_21_xor_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_22_xor_r8_r8.png" width=""/> </div><br> 

- **XOR BYTE PTR DS:[0x19FF84],CL**
* ***运行前***
<div align="center"> <img src="../../images/xor//_23_xor_m8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_24_xor_m8_r8.png" width=""/> </div><br>

> 7、XOR r/m16,r16
- **XOR CX,SP**
* ***运行前***
<div align="center"> <img src="../../images/xor//_25_xor_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_26_xor_r16_r16.png" width=""/> </div><br> 

- **XOR WORD PTR DS:[0x19FF8C],CX**
* ***运行前***
<div align="center"> <img src="../../images/xor//_27_xor_m16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_28_xor_m16_r16.png" width=""/> </div><br>

> 8、XOR r/m32,r32
- **XOR EAX,ECX**
* ***运行前***
<div align="center"> <img src="../../images/xor//_29_xor_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_30_xor_r32_r32.png" width=""/> </div><br> 

- **XOR DWORD PTR DS:[0x19FF88],EBX**
* ***运行前***
<div align="center"> <img src="../../images/xor//_31_xor_m32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_32_xor_m32_r32.png" width=""/> </div><br>

> 9、XOR r8,r/m8
- **XOR AH,AL**
* ***运行前***
<div align="center"> <img src="../../images/xor//_33_xor_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_34_xor_r8_r8.png" width=""/> </div><br> 

- **XOR AL,BYTE PTR DS:[0x19FF90]**
* ***运行前***
<div align="center"> <img src="../../images/xor//_35_xor_r8_m8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_36_xor_r8_m8.png" width=""/> </div><br>

> 10、XOR r16,r/m16
- **XOR AX,SP**
* ***运行前***
<div align="center"> <img src="../../images/xor//_37_xor_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_38_xor_r16_r16.png" width=""/> </div><br> 

- **XOR AX,WORD PTR DS:[0x19FF8C]**
* ***运行前***
<div align="center"> <img src="../../images/xor//_39_xor_r16_m16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_40_xor_r16_m16.png" width=""/> </div><br>

> 11、XOR r32,r/m32
- **XOR EAX,EBX**
* ***运行前***
<div align="center"> <img src="../../images/xor//_41_xor_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_42_xor_r32_r32.png" width=""/> </div><br> 

- **XOR EAX,DWORD PTR DS:[0x19FF84]**
* ***运行前***
<div align="center"> <img src="../../images/xor//_43_xor_r32_m32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/xor//_44_xor_r32_m32.png" width=""/> </div><br>