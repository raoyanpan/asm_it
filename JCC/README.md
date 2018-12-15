## JCC

### JMP指令
**修改EIP的值**
```asm
;MOV EIP,寄存器/立即数   简写为:JMP 寄存器/立即数
```

### CALL指令
**修改EIP(CALL的值),并且将返回地址压入栈中**
```asm
;PUSH 返回地址
;MOV EIP,地址A/立即数  简称为:CALL 地址A/立即数
```

### RET指令
```asm
;LEA ESP,[ESP+4]
;MOV EIP，[ESP-4]  简写为：RET
```

### CMP指令
**指令格式：CMP  R/M,R/M/IMM**
- `该指令是比较两个操作数,实际上,它相当于SUB指令,但是相减的结构并不保存到第一个操作数中`
- `比较两个操作数,不影响结果,只影响标志寄存器`
```asm
MOV EAX,100	
MOV ECX,100	
CMP EAX,ECX
;EAX=ECX,ZF = 1,PF=1,最低有效字节值为0	
```
```asm
MOV EAX,100	
MOV ECX,200	
CMP EAX,ECX
;EAX<ECX,CF=1,PF=1,最低有效字节值为0,SF=1,
```

### TEST指令
**指令格式：TEST  R/M,R/M/IMM**
- `该指令在一定程序上和CMP指令时类似的,两个数值进行与操作,结果不保存,但是会改变相应标志位`

```
;与的操作表项如下
1 and 1 = 1
1 and 0 = 0
0 and 1 = 0
0 and 0 = 0
```

## JCC
| 序号 | 操作符 | 释义 | 标志位 |
| :---: | :---: | :---: | :---: |
| 1 | JE,JZ | 结果为零则跳转(相等时跳转) | ZF=1 |
| 2 | JNE,JNZ | 结果不为零则跳转(不相等时跳转) | ZF=0 |
| 3 | JS | 结果为负则跳转 | SF=1 |
| 4 | JNS | 结果为非负则跳转 | SF=0 |
| 5 | JP,JPE | 结果中1的个数为偶数则跳转 | PF=1 |
| 6 | JNP,JPO | 结果中1的个数为奇数则跳转 | PF=0 |
| 7 | JO | 结果溢出了则跳转 | OF=1 |
| 8 | JNO | 结果没有溢出则跳转 | OF=0 |
| 9 | JB,JNAE | 小于则跳转 (无符号数) | CF=1 |
| 10 | JNB,JAE | 大于等于则跳转 (无符号数) | CF=0 |
| 11 | JBE,JNA | 小于等于则跳转 (无符号数) | CF=1 or ZF=1 |
| 12 | JNBE,JA | 大于则跳转(无符号数) | CF=0 and ZF=0 |
| 13 | JL,JNGE | 小于则跳转(有符号数) | SF≠ OF |
| 14 | JNL,JGE | 大于等于则跳转(有符号数) | SF=OF |
| 15 | JLE,JNG | 小于等于则跳转(有符号数) | ZF=1 or SF≠ OF |
| 16 | JNLE,JG | 大于则跳转(有符号数) | ZF=0 and SF=OF |

- **1、JE,JZ:ZF=1**
```asm
MOV AL,1
MOV CL,1
CMP AL,CL
JE  0x778DCE5D
```
- **2、JNE,JNZ:ZF=0**
```asm
MOV AL,1
MOV CL,2
CMP AL,CL
JNE 0x778DCE5D
```
- **3、JS:SF=1**
```asm
MOV AL,1
MOV CL,2
CMP AL,CL
JS 0x778DCE5D
```
- **4、JNS:SF=0**
```asm
MOV AL,1
MOV CL,2
CMP CL,AL
JNS 0x778DCE5D
```
- **5、JP,JPE:PF=1**
```asm
MOV AL,1
MOV CL,2
CMP AL,CL
JPE 0x778DCE5D
```
- **6、JNP,JPO:PF=0**
```asm
MOV AL,11
MOV CL,1
CMP AL,CL
JPO 0x778DCE5D
```
- **7、JO:OF=1**
```asm
MOV AL,7F
MOV CL,0xFE
CMP AL,CL
JO 0x778DCE5D
```
- **8、JNO:OF=0**
```asm
MOV AL,7
MOV CL,2
CMP AL,CL
JNO 0x778DCE5D
```
- **9、JB,JNAE:CF=1**
```asm
MOV AL,0x7F
MOV CL,0x80
CMP AL,CL
JB 0x778DCE5D
```
- **10、JNB,JAE:CF=0**
```asm
MOV AL,0x7F
MOV CL,0xF
CMP AL,CL
JNB 0x778DCE5D
```
- **11、JBE,JNA:CF=1 or ZF=1**
```asm
;CF=1,ZF=0
MOV AL,0x7F
MOV CL,0x80
CMP AL,CL
JBE 0x778DCE5D

;CF=0,ZF=1
MOV AL,0x7F
MOV CL,0x7F
CMP AL,CL
JBE 0x778DCE5D
```
- **12、JNBE,JA:CF=0 and ZF=0**
```asm
MOV AL,0x7F
MOV CL,0xF
CMP AL,CL
JA 0x778DCE5D
```
- **13、JL,JNGE:SF≠OF**
```asm
;SF=1,OF=0
MOV AL,0x81
MOV CL,0x8F
CMP AL,CL
JL 0x778DCE5D

;SF=0,OF=1
MOV AL,0xFE
MOV CL,0x7F
CMP AL,CL
JL 0x778DCE5D
```
- **14、JNL,JGE:SF=OF**
```asm
;SF=OF=1
MOV AL,0x7F
MOV CL,0xFE
CMP AL,CL
JNL 0x778DCE5D

;SF=OF=0
MOV AL,0x7F
MOV CL,0x70
CMP AL,CL
JNL 0x778DCE5D
```
- **15、JLE,JNG:ZF=1 or SF≠ OF**
```asm
;ZF=1
MOV AL,0x5A
MOV CL,0xA5
TEST AL,CL
JLE 0x778DCE5D

;ZF=0,SF=1,OF=0
MOV AL,0x81
MOV CL,0x8F
CMP AL,CL
JLE 0x778DCE5D

;ZF=0,SF=0,OF=1
MOV AL,0xFE
MOV CL,0x7F
CMP AL,CL
JLE 0x778DCE5D
```
- **16、JNLE,JG:ZF=0 and SF=OF**
```asm
;ZF=0,SF=OF=0
MOV AL,0x5A
MOV CL,0xAA
TEST AL,CL
JNLE 0x778DCE5D

;ZF=0,SF=OF=1
MOV AL,0x7F
MOV CL,0xFE
CMP AL,CL
JNLE 0x778DCE5D
```