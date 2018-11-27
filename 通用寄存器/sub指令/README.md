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

> 6、SUB r/m8,r8
- **SUB ECX,0xAC**
* ***运行前***
<div align="center"> <img src="../../images/sub//_21_sub_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_22_sub_r8_r8.png" width=""/> </div><br>

- **SUB BYTE PTR DS:[0x19FFE8],0xAL**
* ***运行前***
<div align="center"> <img src="../../images/sub//_23_sub_m8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_24_sub_m8_r8.png" width=""/> </div><br>

> 7、SUB r/m16,r16
- **SUB AX,CX**
* ***运行前***
<div align="center"> <img src="../../images/sub//_25_sub_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_26_sub_r16_r16.png" width=""/> </div><br>

- **SUB WORD PTR DS:[0x19FFE8],AX**
* ***运行前***
<div align="center"> <img src="../../images/sub//_27_sub_m16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_28_sub_m16_r16.png" width=""/> </div><br>

> 8、SUB r/m32,r32
- **SUB EAX,ECX**
* ***运行前***
<div align="center"> <img src="../../images/sub//_29_sub_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_30_sub_r32_r32.png" width=""/> </div><br>

- **SUB DWORD PTR DS:[0x19FFE8],EAX**
* ***运行前***
<div align="center"> <img src="../../images/sub//_31_sub_m32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_32_sub_m32_r32.png" width=""/> </div><br>

> 9、SUB r8,r/m8
- **SUB CH,CL**
* ***运行前***
<div align="center"> <img src="../../images/sub//_33_sub_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_34_sub_r8_r8.png" width=""/> </div><br>

- **SUB AL,BYTE PTR DS:[0x19FFE8]**
* ***运行前***
<div align="center"> <img src="../../images/sub//_35_sub_r8_m8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_36_sub_r8_m8.png" width=""/> </div><br>

> 10、SUB r16,r/m16
- **SUB AX,CX**
* ***运行前***
<div align="center"> <img src="../../images/sub//_37_sub_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_38_sub_r16_r16.png" width=""/> </div><br>

- **SUB AX,WORD PTR DS:[0x19FF90]**
* ***运行前***
<div align="center"> <img src="../../images/sub//_39_sub_r16_m16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/sub//_40_sub_r16_m16.png" width=""/> </div><br>