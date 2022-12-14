- upward compatibility is when the previous CPS instructions can run on the successive CPU’s also
- ![[Pasted image 20221217134116.png]]
- ISA
- architecture
	- ![[Pasted image 20221217134153.png]]
	- ![[Pasted image 20221217134221.png]]
- registers
	- ![[Pasted image 20221217134302.png]]
		- `#` only B is used for addre
			- used with arith & logical oper
			- ![[Pasted image 20221217134441.png]] #still_coal
			- ![[Pasted image 20221217134457.png]] #still_coal 
		- `@` 
			- ending with P > SS
			- ending with I > DS
			- called OR .. offset registers .. offset > الذي يسبب الموازنة / العوض
			- ![[Pasted image 20221217134630.png]]
			- ![[Pasted image 20221217134640.png]]
		- `$` 
			- ![[Pasted image 20221217134721.png]]
			- ![[Pasted image 20221217134730.png]]
		- `&` #still_coal 
			- ![[Pasted image 20221217134806.png]]
			- ![[Pasted image 20221217134818.png]]
			- ![[Pasted image 20221217134830.png]]
	- ![[Pasted image 20221217134319.png]]
- 8086 successors (children)
	- ![[Pasted image 20221217134955.png]]
	- ![[Pasted image 20221217135006.png]]
- ![[Pasted image 20221217194810.png]]


---

مميزات اللغة
	سرعة
	تحكم في الذاكرة
عيبها إنها مش portable
	لازم تغير الكود حسب ال cpu
#still_coal 
	![[Pasted image 20221217141830.png]]
![[Pasted image 20221217142042.png]]


---


![[Pasted image 20221217143309.png]]

![[Pasted image 20221217194911.png]]
	parity
		even {btw that's when the 1's count is even} > 1
		odd
	#still_coal aux carry
	direction
		0 > incr index

```ASM
;---------------------------------------
hey segment ;hey = name of data segment

	;data decl

hey ends
;---------------------------------------

stack segment
stack ends
;---------------------------------------
code segment ;code = name of code segment
begin:

mov si, hey
mov ds, si
	;فايدتهم تعرف إن ال hey = data segment

	;list whatever

code ends

end begin ;end of the prog with the label of 1st intruction
;---------------------------------------



```


---


- data directives
	- Dsomething = define by something ممكن بحروف صغيرة عادي
		- DB 1B
		- DW 2
		- DD 4
		- DQ 8
		- DT 10
	- ![[Pasted image 20221217201831.png]]no over-write
	- arr
		- ![[Pasted image 20221217202030.png]]
		- to duplicate![[Pasted image 20221217202257.png]]
		- 
	- val can be char/str/int
	- const![[Pasted image 20221217202142.png]]
	- ![[Pasted image 20221217202539.png]]


Addressing modes

![[Pasted image 20221217203747.png]]

![[Pasted image 20221217205231.png]]

---

# types of instructions


### assignment statements

mov


---


### arith

add
sub
inc
dec
neg negative of
>mul
	`mul bx ; ax *= bx`
	`mul bh ; ah *= bh`

cmp comparing
	![[Pasted image 20221224121434.png]]

---

### shift and rotate

[Shift Instructions in assembly language : SHL,SHR,SAL,SAR - YouTube](https://www.youtube.com/watch?v=jyHxez9W51s&ab_channel=MahaMohammad)

	تشفيت من غير حفظ اشارة السالب
	shl shift left
	shr

	تشفيت مع حفظ اشارة السالب
	sar   shift arith left
	sal

اللي فوق بيأثروا على ال cf

	rol rotation left
	ror

---
```assembly
comment !
!
```

### loop

```assembly
loopName:
	what ever
loop loopName        ;stops when cx = 0
```


---

# types of instructions

### bool & bitwise
d, s لازم نفس الحجم

and , or , xor , not
![[Pasted image 20221224144151.png]]

---

how to

 >from lower to UPPER
	 and 1101 1111
	 and 0dfH
	 لأن مكان الصفر دا الديجيت بيكون متفعل في السمول
	 وتعطيله بيمثل الفارق الوحيد بين الكابيتال والسمول



>from UPPER to lower
	or 0010 0000
	or 20h





--------------------------------------
- ### memory management/ organization

- ![[Pasted image 20221217135123.png]]
![[Pasted image 20221217135139.png]]
![[Pasted image 20221217135153.png]] #still_coal 
![[Pasted image 20221217135213.png]]

![[Pasted image 20221217135248.png]]
![[04#reg assoc]]

at least 3 segments should be used CS / SS / DS
#still_coal  [this link](https://youtu.be/22Bx4-EiZ0M?t=570) rules of memory segmentation

![[Pasted image 20221217135449.png]]
![[Pasted image 20221217135458.png]]


shifting digits can be done on any number system

#still_coal  [this link also](https://youtu.be/22Bx4-EiZ0M?t=1380)




------------------



# 3- 8086 Assembly Program Structure

data  = directives .. to the assembler

![[Pasted image 20221224154513.png]]


![[Pasted image 20221224154751.png]]
مينفعش كونست على طول مع ال دي اس
لذلك كان فيه ريجيستر وسيط

![[Pasted image 20221224155237.png]]

![[Pasted image 20221224155535.png]]

الستاك بيتحجز بالوورد مش البايت

![[Pasted image 20221224160133.png]]

---



```asm
MOV destination, source
```
destination can't be value
	reg
	mem addr
source
	reg
	mem addr
	value

```asm
ADD destination, source
```

```asm
SUB destination, source
// d-s > d
```

```asm
INC something
// something++
```

```asm
DEC something
// something--
```

```asm
ADC D, S
// add with carry .. D+S+c > D
```

```asm
SBB D, S
// subtraction with borrow .. D-S-b > D
```




```asm
;loooooooooooooooooop
MOV AX,00H
MOV BX,02H
MOV CX,03H//cntr

WHATEVER: ADD AX,BX
LOOP WHATEVER
HLT
//AX will have 6 at the end
```

---




# 4- 8086 Addressing Modes

![[Pasted image 20221224161107.png]]


### reg assoc

![[Pasted image 20221225141000.png]]

#### [stopped here](https://youtu.be/NgUhbUnZ1Pg?t=641)
#still_coal 


------------

#elsany_coal
### 1-Data types ,Data Definition ,Register Definition

![[Pasted image 20221224165145.png]]
![[Pasted image 20221224165414.png]]
![[Pasted image 20221224165555.png]]



![[Pasted image 20221224170421.png]]
### 2- Arithmetic instrucations

mov
	لا تؤثر على ال flags

adc add with carry
ssb sub with borrow

mul > unsigned mul
	multiplicand is always AL
```asm
//mul
MOV AL, 14H
MOV BL, 24H
MUL BL //--> al * bl > AX(if 8bit) else DX as high then AX as low
```

imul > signed mul


div unsigned
idiv singed
```asm
//div
MOV ax, 19
MOV bx, 2
; divident / divisor = quotien R remainder
div divisor 
commnet !
                              rem   quo
ax / divisro > if(divisor 8)  ah    al
              > else          Dx   Ax

!

```



-----------

### 4-Help Instructions 

Cbw convert signed B (byte) to signed W للتوسعة

![[Pasted image 20221224190030.png]]


	![[Pasted image 20221224121434.png]]
![[Pasted image 20221224190907.png]]

Cwd word to doubleword للتوسعة برضو


clc clear the carry flag
STC (STAY THE CARRY FLAG =1 )


Xchg (Swaping/exchange)
![[Pasted image 20221225133958.png]]

--------

### Addressing modes

![[Pasted image 20221225141121.png]]

![[Pasted image 20221225143710.png]]
![[Pasted image 20221225143739.png]]

![[Pasted image 20221225144045.png]]

--------


### 6-unconditional/conditional control, jump instruction : 

compare cmp
![[Pasted image 20221225165131.png]]
 jump jmp
 ![[Pasted image 20221225165150.png]]

unsigned
![[Pasted image 20221225164550.png]]
signed
![[Pasted image 20221225164621.png]]

---

### subroutines

![[Pasted image 20221225174426.png]]
[subroutine in Computer organization | COA - YouTube](https://www.youtube.com/watch?v=IX6PNkHrRo4&ab_channel=Education4u)

not > 1's complement

---

### loops


![[Pasted image 20221225194223.png]]

![[Pasted image 20221225195738.png]]


