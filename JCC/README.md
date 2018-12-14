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
| 1 | JE,JZ (**1、JE,JZ**)| 结果为零则跳转(相等时跳转) | ZF=1 |
| 2 | JNE,JNZ | 结果不为零则跳转(不相等时跳转) | ZF=0 |
| 3 | JS | 结果为负则跳转 | SF=1 |
| 4 | JNS | 结果为非负则跳转 | SF=0 |
| 5 | JP,JPE | 结果中1的个数为偶数则跳转 | PF=1 |
| 6 | JNP,JPO | 结果中1的个数为偶数则跳转 | PF=0 |
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

- **1、JE,JZ**
```asm
MOV AL,1
MOV CL,1
CMP AL,CL
JE  0x778DCE5D
```
- **2、JNE,JNZ**
```asm
MOV AL,1
MOV CL,2
CMP AL,CL
JNE 0x778DCE5D
```
- **3、JS**