## 标志寄存器

<div align="center"> <img src="../images/eflags//_1_eflags.png" width=""/> </div><br>

### 1、进位标志CF(Carry Flag)
如果运算结果的**最高位**产生了一个**进位或借位**，那么，其值为1，否则其值为0。
```asm
;8位 最高位进位
MOV AL,0xFD

ADD AL,0x10

;8位 最高位借位
MOV AL,0x10

SUB AL,0xF0

;16位 最高位进位
MOV AX,0xFFF1

ADD AL,0x10

;16位 最高位借位
MOV AX,0x2001

SUB AX,0xF000

;32位 最高位进位
MOV EAX,0xFFFFFFF1  ;-F0

ADD EAX,0x10

;32位 最高位借位
MOV EAX,0x40000001

SUB EAX,0xE0000000
```

### 2、奇偶标志PF(Parity Flag)
反映运算**结果中最低有效字节(AL)中"1"的个数的奇偶性**。如果"1"的个数为偶数，则PF的值为1，否则其值为0。
```asm
;8位 AL中"1"的个数为偶数 PF值为1
MOV AL,0x1

ADD AL,0x2

;16位 AL中"1"的个数为偶数 PF值为1
MOV AX,0x1000

ADD AX,0x2000

;32位 AL中"1"的个数为偶数 PF值为1
MOV EAX,0x10000000

ADD EAX,0x20000000
```

### 3、辅助进位标志AF(Auxiliary Carry Flag)
在发生下列情况时，辅助进位标志AF的值被置为1，否则其值为0：<br/>
**(1)、在字(WORD:16位;DWORD:32位)操作时，发生低字节向高字节进位或借位时。** <br/>
**(2)、在字节(BYTE:8位)操作时，发生低4位向高4位进位或借位时。** <br/>

```asm
;8位 AL中高位受到进位
MOV AL,0xF

ADD AL,0x1

;8位 AL中高位受到借位
MOV AL,0x10

SUB AL,0x2

;16位 AL中高位受到进位
MOV AX,0x4EDE

ADD AX,0x2

;16位 AL中高位受到借位
MOV AX,0x1C

SUB AX,0xF

;32位 AL中高位受到进位
MOV EAX,0x1000000F

ADD EAX,0x1

;32位 AL中高位受到借位
MOV EAX,0x10000021

SUB EAX,0x2
```

### 4、零标志ZF(Zero Flag)
反映**运算结果是否为0**。
如果运算结果为0，则其值为1，否则其值为0。在判断运算结果是否为0时，可使用此标志位。
```asm
XOR EAX,EAX ;清零
```
### 5、符号标志SF(Sign Flag)
反映**运算结果的符号位**，它与运算结果的最高位相同。

8位  FF   -> `1`111 1111<br/>
16位 FFFF -> `1`111 1111 1111 1111<br/>
32位 FFFFFFFF -> `1`111 1111 1111 1111 1111 1111 1111 1111<br/>

**如果最高位是1,那么SF为1,如果最高位是0，那么SF为0。**

```asm
;8位 高位为"1",那么其大于"7F",所以,OF溢出,会受影响
MOV AL,0x70

ADD AL,0x10

;16位 高位为"1",那么其大于"7FFF",所以,OF溢出,会受影响
MOV AX,0x7001

ADD AX,0x1000

;32位 高位为"1",那么其大于" 7FFFFFFF",所以,OF溢出,会受影响
MOV EAX,0x70000001

ADD EAX,0x10000000
```

### 6、溢出标志OF(Overflow Flag)
**反映有符号数加减运算所得结果是否溢出。**<br/>
如果运算结果超过当前运算位数所能表示的范围，则称为溢出，OF的值被置为1，否则，OF的值被清为0。

**最高位进位与溢出的区别：**<br/>
进位标志(CF)表示:无符号数运算结果是否超出范围。<br/>
溢出标志(OF)表示:有符号数运算结果是否超出范围。<br/>

```
溢出主要是给有符号运算使用的，在有符号的运算中，有如下的规律:
正 + 正 = 正 如果结果是负数，则说明有溢出。
负 + 负 = 负 如果结果是正数，则说明有溢出。
正 + 负 永远都不会有溢出。						
```

```asm
;1、无符号、有符号都不溢出
MOV AL,8

ADD AL,8

;2、无符号溢出、有符号不溢出
MOV AL,0xFF

ADD AL,2

;3、无符号不溢出、有符号溢出
MOV AL,7F

ADD AL,2

;4、无符号、有符号都溢出	
MOV AL,0xFE

ADD AL,80	
```

# [ADC等指令](https://github.com/raoyanpan/asm_it/blob/master/标志寄存器/ADC等指令/README.md)