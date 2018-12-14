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
`该指令是比较两个操作数,实际上,它相当于SUB指令,但是相减的结构并不保存到第一个操作数中`
`比较两个操作数,不影响结果,只影响标志寄存器`
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
`该指令在一定程序上和CMP指令时类似的,两个数值进行与操作,结果不保存,但是会改变相应标志位`

```
;与的操作表项如下
1 and 1 = 1
1 and 0 = 0
0 and 1 = 0
0 and 0 = 0
```

## JCC
| 操作符 | 释义 | 标志位 |
| :---: | :---: | :---: |
| JE,JZ | 结果为零则跳转(相等时跳转) | ZF=1 |
| JNE,JNZ | 结果不为零则跳转(不相等时跳转) | ZF=0 |
| JS | 结果为负则跳转 | SF=1 |
| JNS | 结果为非负则跳转 | SF=0 |
| JP,JPE | 结果中1的个数为偶数则跳转 | PF=1 |
| JNP,JPO | 结果中1的个数为偶数则跳转 | PF=0 |
| JO | 结果溢出了则跳转 | OF=1 |
| JNO | 结果没有溢出则跳转 | OF=0 |
| JB,JNAE | 小于则跳转 (无符号数) | CF=1 |
| JNB,JAE | 大于等于则跳转 (无符号数) | CF=0 |
| JBE,JNA | 小于等于则跳转 (无符号数) | CF=1 or ZF=1 |
| JNBE,JA | 大于则跳转(无符号数) | CF=0 and ZF=0 |
| JL,JNGE | 小于则跳转(有符号数) | SF≠ OF |
| JNL,JGE | 大于等于则跳转(有符号数) | SF=OF |
| JLE,JNG | 小于等于则跳转(有符号数) | ZF=1 or SF≠ OF |
| JNLE,JG | 大于则跳转(有符号数) | ZF=0 and SF=OF |
