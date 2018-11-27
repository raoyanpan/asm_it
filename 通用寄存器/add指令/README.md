## ADD指令
> 1、ADD r/m8,imm8
- **ADD AL,0xFF**
* ***运行前***
<div align="center"> <img src="../../images/add//_1_add_r8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_2_add_r8_imm8.png" width=""/> </div><br>

- **ADD BYTE PTR DS:[0x19FFE8],0xB5**
* ***运行前***
<div align="center"> <img src="../../images/add//_3_add_m8_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_4_add_m8_imm8.png" width=""/> </div><br>

> 2、ADD r/m16,imm16
- **ADD BX,0x5FFF**
* ***运行前***
<div align="center"> <img src="../../images/add//_5_add_r16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_6_add_r16_imm16.png" width=""/> </div><br>

- **ADD WORD PTR DS:[0x19FFF0],0x1234**
* ***运行前***
<div align="center"> <img src="../../images/add//_7_add_m16_imm16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_8_add_m16_imm16.png" width=""/> </div><br>

> 3、ADD r/m32,imm32
- **ADD EAX,0xFFBFEFFF**
* ***运行前***
<div align="center"> <img src="../../images/add//_9_add_r32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_10_add_r32_imm32.png" width=""/> </div><br>

- **ADD DWORD PTR DS:[0x19FFF4],0xFFBFEFFF**
* ***运行前***
<div align="center"> <img src="../../images/add//_11_add_m32_imm32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_12_add_m32_imm32.png" width=""/> </div><br>

> 4、ADD r/m16,imm8
- **ADD CX,1**
* ***运行前***
<div align="center"> <img src="../../images/add//_13_add_r16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_14_add_r16_imm8.png" width=""/> </div><br>

- **ADD WORD PTR DS:[0x19FFF4],0xFF**
* ***运行前***
<div align="center"> <img src="../../images/add//_15_add_m16_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_16_add_m16_imm8.png" width=""/> </div><br>

> 5、ADD r/m32,imm8
- **ADD EBX,0x12**
* ***运行前***
<div align="center"> <img src="../../images/add//_17_add_r32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_18_add_r32_imm8.png" width=""/> </div><br>

- **ADD DWORD PTR DS:[0x19FFE8],0x9D**
* ***运行前***
<div align="center"> <img src="../../images/add//_19_add_m32_imm8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_20_add_m32_imm8.png" width=""/> </div><br>

> 6、ADD r/m8,r8
- **ADD DH,CL**
* ***运行前***
<div align="center"> <img src="../../images/add//_21_add_r8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_22_add_r8_r8.png" width=""/> </div><br>

- **ADD BYTE PTR DS:[19FFE8],0xAC**
* ***运行前***
<div align="center"> <img src="../../images/add//_23_add_m8_r8.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_24_add_m8_r8.png" width=""/> </div><br>

> 7、ADD r/m16,r16
- **ADD AX,CX**
* ***运行前***
<div align="center"> <img src="../../images/add//_25_add_r16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_26_add_r16_r16.png" width=""/> </div><br>

- **ADD WORD PTR DS:[0x19FFF4],CX**
* ***运行前***
<div align="center"> <img src="../../images/add//_27_add_m16_r16.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_28_add_m16_r16.png" width=""/> </div><br>

> 8、ADD r/m32,r32
- **ADD EAX,ECX**
* ***运行前***
<div align="center"> <img src="../../images/add//_29_add_r32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_30_add_r32_r32.png" width=""/> </div><br>

- **ADD DWORD PTR DS:[0x19FFF4],ECX**
* ***运行前***
<div align="center"> <img src="../../images/add//_31_add_m32_r32.png" width=""/> </div><br>

* ***运行后***
<div align="center"> <img src="../../images/add//_32_add_m32_r32.png" width=""/> </div><br>