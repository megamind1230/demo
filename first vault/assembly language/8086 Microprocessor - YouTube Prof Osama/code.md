array indirect addressing
 ```asm
 data segment  
    array db 1h,2h,3h  
    copy db 3 dup(?)  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
                 
                 
                 
                 
;     direct addressing               
;   mov al, original[0]    
;   mov copy[0],al    
;   mov al, original[1]    
;   mov copy[1],al   
;   mov al, original[2]    
;   mov copy[2],al   
  
                
                
                
;     index addressing  
;    mov si,0  
;    mov al,original[si]  
;    mov copy[si],al  
;      
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al  
;        
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al    
;      
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al   
;      
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al   
;      
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al     
;          
  
  
  
          
;    indirect addressing    
    mov si, offset array  ; lea si,  array  
    mov di, offset copy  
      
    mov al, [si]  
    mov [di],al   
      
    inc di  
    inc si            
                   
    mov al, [si]  
    mov [di],al  
       
    inc di  
    inc si       
      
    mov al, [si]  
    mov [di],al  
    
        
      
         
ends  
end start
```

lea instruction copy
```asm
 data segment  
    var dw 1020h  
    copy dw ?  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   lea bx,var  ; mov bx, offset var   
   lea si,copy   
   mov ax,[bx]   
   mov [si],ax  
     
            
ends  
end start
```

loop sum of array indirect addressingLEA

```asm
data segment  
    array db 1h,2h,3h  
    sum db ?  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
     ; index addressing         
   ;mov di,0  
;   mov al, array[di]  
;   inc di  
;   add al, array[di]    
;   inc di  
;   add al, array[di]   
;   mov sum ,al  
     
      
    lea si, array   
    mov al,0  
    mov cx,3   
      
    L1: add al, [si]  
    inc si     
      
    loop L1   
      
    mov sum ,al   
    
        
      
         
ends  
end start****
```

swap two dd variables
```asm
; define two double word variables a=123456h and b=7891011 swap their values   
  
  
  
data SEGMENT   
      
   a dd 123456h   
   b dd 7891011h  
     
ENDS  
code  SEGMENT   
    start:   
      
      
      
    mov ax,data  
    mov ds,ax   
      
      
 mov ax ,a  
 mov bx ,a+2  
 mov cx,b  
 mov dx,b+2  
 mov a,cx  
 mov a+2,dx  
 mov b,ax  
 mov b+2,bx      
     
     
ENDS  
end start
```

BOUNS
```
DATA SEGMENT  
    NUM DD 78458296H  
    D DB 10H  
    ARR DW 4 dup(?)  
    RES DD 0  
ENDS   
  
  
CODE SEGMENT  
MAIN:  
    MOV AX, DATA  
    MOV DS, AX  
    MOV AX, 0  
      
    MOV AL, BYTE PTR NUM  
    DIV D  
    MUL AH  
    MOV arr, AX  
      
    MOV AL, BYTE PTR NUM+1  
    DIV D  
    MUL AH  
    MOV arr+2, AX  
      
    MOV AL, BYTE PTR NUM+2  
    DIV D  
    MUL AH  
    MOV arr+4, AX  
      
    MOV AL, BYTE PTR NUM+3  
    DIV D  
    MUL AH  
    MOV arr+6, AX  
      
    MOV AX, 1  
    MUL arr  
    MUL arr+2  
    MUL arr+4  
    MUL arr+6  
      
    MOV res+2,DX  
    MOV res, AX  
ENDS  
END MAIN
```

TASK1
```
DATA SEGMENT  
    ARR DW 3, 4, 5, 6, 7  
    SUM DW 0  
    DIVID DW 5  
    RESULT DW 0  
ENDS   
  
  
CODE SEGMENT  
MAIN:  
    MOV AX, DATA  
    MOV DS, AX  
    MOV AX, 0  
      
    MOV AX, 2  
    MUL ARR[0]  
    ADD SUM ,AX  
    MUL ARR[2]  
    ADD SUM ,AX  
      
    MUL ARR[4]  
    ADD SUM ,AX  
    MUL ARR[6]  
    ADD SUM ,AX  
    MUL ARR[8]  
    ADD SUM ,AX  
    MOV AX, SUM  
    DIV DIVID  
    MOV RESULT, AX  
      
ENDS  
END MAIN
```

imad - Copy

```
;week 1  
DATA SEGMENT ;Start OF DATA SEGMENT   
    ;We Create our variables and arrays here  
  
    ;Create vars  
    var1 DB 25 ; BYTE VARIABLE  
    VAR2 DW 257; 2 BYTES VARIABLE (Word)  
    VAR3 DD 257; 4 BYTES VARIABLE (Double Word)  
    VAR4 DQ 257; 8 BYTES VARIABLE (Quad Word)  
  
    ;values in different number systems  
    d_var DB 25     ;variable with decimal value  
    b_var DB 10110B ;variable with binary value  
    o_var DB 25O    ;variable with Octal value  
    h_var DB 0EFH   ;variable with Hexadecimal value  
  
    ;Create variable without assign value  
    empty_var DB ?  
  
    ;Create Byte Array that save every value in 1 Bytes  
    bt_array DB 1, 2, 3, 4, 7, 5, 8, 9  
    ;Create word Array that save every value in 2 Bytes  
    w_array DW 1, 2, 3, 4, 7, 5, 8, 9  
    ;Create DoublWord Array that save every value in 4 Bytes  
    d_array DD 1, 2, 3, 4, 7, 5, 8, 9  
    ;Create QuadWord Array that save every value in 8 Bytes  
    q_array DQ 1, 2, 3, 4, 7, 5, 8, 9  
  
    ;the name of the array always refere to the first element of the array if you want the second element add one to array name  
    ;(my_array) is a byte array so when u type (my_array) this means u refer to first element (10) only  
    my_array db 10,20,30,40  
  
    ;The asssembler save each character in a byte in the memory so this string varable will be a character array  
    ;the name of the array always refere to the first element of the array if you want the second element add one to array name  
    ;(my_name) is a character array so when u type (my_name) this means u refer to first character (M) only  
    my_name db "My Name is mohamed"  
    my_name2 db 'Ahmed'  
  
    ;create an array with initial value  
    ;arr_name (size of values) (size of array) dup(init value)  
    array db 100 DUP(12) ; This line creates an array of 100 place each place is a byte and each byte has 12 as initial value in it.  
    array2 dw 50 DUP(5) ; This line creates an array of 50 place each place is a word (2 Byte) and each word has 5 as initial value in it.  
    array2 DD 30 DUP(3) ; This line creates an array of 30 place each place is a Double Word (4 Byte) and each Double word has 3 as initial value in it.  
    array2 DQ 10 DUP(7) ; This line creates an array of 10 place each place is a Quad Word (8 Byte) and each Quad word has 7 as initial value in it.  
  
    ;create an array without initial value  
    array db 100 DUP(?) ; This line creates an array of 100 place each place is a byte and each byte has no value in it.  
    array2 dw 50 DUP(?) ; This line creates an array of 50 place each place is a word (2 Byte) and each word has no value in it.  
    array2 DD 30 DUP(?) ; This line creates an array of 30 place each place is a Double Word (4 Byte) and each Double Word has no value in it.  
    array2 DQ 10 DUP(?) ; This line creates an array of 10 place each place is a Quad Word (8 Byte) and each Quad word has no value in it.  
  
  
    ;Create a constant variable   
    PIE EQU 3  
    Gravity EQU 10  
  
  
  
ENDS ;END OF DATA SEGMENT  
  
CODE SEGMENT ;Start OF CODE SEGMENT   
;Instruction syntax  -> LABEL: Mnemonic [OPERAND(S)] ;Comment  
  
MAIN: ;label with name main as function main in c++  
  
;MOV Instruction take the value of second operand(memory or regester or immediate value) and move it to first operand (memory or regester)  
;the line below will move 10 into ax register  
MOV AX, 10   
  
;Remember: When u use Move to move between two operands the two operands must match the same size  
;the line below move a (word variable) var2 (2 Bytes = 16 bit) to AX (16 bit) register   
MOV AX, VAR2  
  
  
;The MOV instruction cannot:  
;set the value of the CS and IP registers.  
;copy value of one segment register to another segment register (should copy to general register first).  
;copy immediate value to segment register (should copy to general register first).  
  
;as a recap the MOV register MUST do any opration with the GPR Registers (AX, BX, CX, DX)  
  
CODE ENDS   ;End OF CODE SEGMENT   
END MAIN ;End of main label
```

TASK 2 - Copy
```
;1-  You are given two byte variables: a = 20, b = 40.  
  
;Calculate the following equation:    
  
;(a^3) * b + 5 * (b^2)  
  
;and store the result inside result variable.  
  
;(note the result of equation is: 328,000)  
  
  
DATA SEGMENT  
    a DB 20  
    b DB 40  
    aw DW ?  
    bw DW ?  
    fi DW 5  
    fpart DD ?  
    result DD ?  
      
ENDS  
   
   
CODE SEGMENT  
MAIN:  
    MOV AX, DATA  
    MOV DS, AX  
    MOV AX, 0  
      
    IN AX, 1  
    MOV AL, a  
    MOV aw, AX  
      
    MOV AL, b  
    MOV bw, AX  
      
    MOV AX, aw  
    MUL aw  
    MUL aw  
    MUL bw  
      
    MOV WORD PTR fpart, AX  
    MOV fpart+2, DX  
      
    MOV AX, 0  
    MOV DX, 0  
      
    MOV AX, bw  
    MUL bw  
    MUL fi  
      
    ADC fpart, AX  
    ADC WORD PTR fpart+2, 0  
      
    MOV AX, WORD PTR fpart  
    MOV BX, WORD PTR fpart+2  
    MOV result, AX  
    MOV result +2, BX  
      
ENDS  
END MAIN
```

---

cx high-low order
```
;program initialize the low order byte of cx register by efh ,  
;save it's one complement at high order byte of cx register   
  
  
data segment  
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
      
     
   mov cl, 0efh  
   mov ch,cl  
   not ch  
      
         
ends  
end start
```

define variables
```
    data segment  
      
       var1 dw equ 50h     ;define constant (50 without h mean 32)    
       var2 dw 0e2h        ;error without zero  
       var3 dw "f"         ;we can use 'f'   
       var4 dw ?           ;without initial value  
       var5 dw 5 dup(2h)   ;define array  
       var6 db 03h  
       var7 db 'ab'        ; define 2 bytes  
       var8 dw 0203h  
            
    data ends     
      
      
    code segment  
       start:  
        mov ax,data  
        mov ds,ax  
          
        mov ax, var1      ;ax=0050  
          
        mov ax, var2      ;ax=00e2  
          
        mov ax, var3      ;ax=0066  
          
        mov ax, var4      ;ax=0000  
          
        mov ax, var5      ;ax=0002 ((var5+1) ax=0200)  
          
        mov al, var6      ;ax=0003  
          
        mov ah, var6      ;ax=0303  
          
        mov al, var7      ;ax=0361  
          
        mov ah, var7      ;ax=6161 ((var7+1) ax=6261)  
           
        mov al, byte ptr var8      ;ax=6103  
          
        mov ah, byte ptr var8+1    ;ax=0203  
          
             
           code ends  
    end start
```

div and mul of two numbers 
```
data segment  
    a dw 8h  
    b dw 4h   
    sum dw ?  
data ends  
  
  
code segment  
    start :  
    mov ax,data  
    mov ds,ax   
    mov ax,a  
    add bx,b  
      
    div bx  
    mul bx  
       
code ends   
end start
```

extra segment
```
;a* initialize ax with string data "no", si with 0200h and bp with 0100h   
;then copy content of ax into stack segment memory location address by si+bp+20h  
  
  
;b* initialize di with 0300h then copy string data "hi" into extra data  
;segment memory location address by di+100h   
  
  
  
data SEGMENT   
         
ENDS  
  
  
code  SEGMENT   
    start:   
        
    mov ax,data  
    mov ds,ax  
      
     ;a  
    mov ax,"no"  
    mov si,0200h  
    mov bp,0100h  
    mov ss:[si+bp+20h],ax  
      
      
    ;b  
   mov di,0300h  
   mov es:[di+100h],"hi"  
      
      
    
     
ENDS  
end start


```

factorial
```
data segment   
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                
                
                
    mov al,5  
    mov bl,4  
    mul bl  
    mov bl,3  
    mul bl    
    mov bl,2  
    mul bl  
        
      
         
ends  
end start
```

index addressing
```
data SEGMENT  
   original db 25h,4fh,85h,1fh,2bh,0c4h  
    copy db 6 dup(?)  
     
ENDS  
code  SEGMENT   
    start:   
      
      
      
    mov ax,data  
    mov ds,ax  
      
      
      
    mov si,0  
    mov al,original[si]  
    mov copy[si],al  
      
    inc si  
    mov al,original[si]  
    mov copy[si],al  
        
    inc si  
    mov al,original[si]  
    mov copy[si],al    
      
    inc si  
    mov al,original[si]  
    mov copy[si],al   
      
    inc si  
    mov al,original[si]  
    mov copy[si],al   
      
    inc si  
    mov al,original[si]  
    mov copy[si],al   
     
     
ENDS  
end start
```

initialize ax,bx
```
;program initialize ax,bx by 100h and 200h respectively   
  
  
  
data segment  
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
      
     
    mov ax,100h  
    mov bx,200h  
         
ends  
end start

```

jmp instruction 
```
data segment  
    var dw 1020h  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   mov ax ,5h  
   mov bx ,2h   
   jmp s1  
   back: inc ax  
   jmp s2  
   s1:sub ax, bx  
   jmp back  
   s2:dec bx    
     
     
ends  
end start
```

lea instruction
```
data segment  
    var dw 1020h  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   lea bx,var  
   mov ax,[bx]  
     
            
ends  
end start
```

loop copy array element index addressing
```
data SEGMENT   
      
  original db 1h,2h,3h  
   copy db 3 dup(?)  
     
ENDS  
code  SEGMENT   
    start:   
      
      
      
    mov ax,data  
    mov ds,ax  
      
      
     ;index addressing  
    ;mov si,0  
;    mov al,original[si]  
;    mov copy[si],al  
;      
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al  
;        
;    inc si  
;    mov al,original[si]  
;    mov copy[si],al   
  
  
     mov cx, 3  
     mov si,0  
     L1: mov al, original[si]  
         mov copy[si],al  
         inc si  
           
     loop L1   
      
      
     
     
ENDS  
end start
```

loop cx.3
```
data segment  
    var dw 1020h  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   mov al,4h  
   mov bl, 8h  
   mov cx,3h  
   L1:  
   add al,2h  
   inc bl  
   loop L1  
      
     
     
ends  
end start
```

memory location [600h]
```
;program save data of 300h and 400h into data segment memory   
;location address by 600h and its consecutives addresses respectively ,  
;add the contents of previous memory locations and save result into cx register   
  
  
  
data segment  
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
      
     
   mov [600h],300h  
   mov [602h],400h  
   mov cx,[600h]  
   add cx,[602h]  
      
         
ends  
end start
```

---


nested loop 
```
data segment  
    count dw 5  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   mov ax,0  
   mov bx,0  
   mov cx,count   
   L1: inc bl  
   mov count ,cx  
      mov cx,2  
      L2: inc al  
      loop L2  
   mov cx,count  
   loop L1  
     
     
      
     
     
ends  
end start
```

rectangle
```
data segment   
      
    area dw ?  
    halfArea dw ?  
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                
                
                
    mov al, 7h  
    mov bl, 3h  
    mul bl  ; ax= al*bl    ; 15  
    mov area , ax     ;15  
    mov bl,2      ;bl 2  
    div bl                 ; al/bl =  7 / 2 = 3{al} R 1{ax}  
    mov halfArea, ax  
        
      
         
ends  
end start
```

stack segment
```
;a* initialize al,bl,cl,dl registers with 10h,20h,30h and 40h    
;b* copy content of al,bl,cl,dl into bh,ch,dh,ah respectively    
;c* swap between ax,bx  
;d* copy content of ax into data segment memory location address by   
;0200h then copy the content of bx,cx at the consecutive offset address   
;e* copy content of dx into stack segment memory location address by 0100h then  
;copy immediate data 4433h,2211h into consecutive offset address  
  
  
  
data SEGMENT   
         
ENDS  
  
  
code  SEGMENT   
    start:   
        
    mov ax,data  
    mov ds,ax  
      
     ;a  
    mov al,10h  
    mov bl,20h  
    mov cl,30h  
    mov dl,40h  
      
      
      
      ;b  
    mov bh,al  
    mov ch,bl  
    mov dh,cl  
    mov ah,dl    
      
      
      
     ;c  
    mov cx,ax  
    mov ax,bx  
    mov bx,cx   
      
      
      
    ;d  
    mov [0200h],ax  
    mov [0202h],bx  
    mov [0204h],cx  
      
      
      
    ;e  
    mov ss:[0100h],dx  
    mov ss:[0102h],4433h  
    mov ss:[0104h],2211h  
      
      
    
     
ENDS  
end start
```

sum of array

```
data segment  
    array db 1h,2h,3h  
    sum db ?  
     
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
                 
             
   mov di,0  
   mov al, array[di]  
   inc di  
   add al, array[di]    
   inc di  
   add al, array[di]   
   mov sum ,al  
     
    
        
      
         
ends  
end start
```

sum two numbers 
```
data segment  
    a dw 10  
    b dw 20   
    sum dw ?  
data ends  
  
  
code segment  
    start :  
    mov ax,data  
    mov ds,ax   
    mov ax,a  
    add ax,b  
    mov sum,ax  
       
code ends   
end start
```

swap ax,bx
```
;program add 50h to content of ax then increase result by one ,   
;substract 50h from content of bx then decrease result by one then  
; swap data in previous registers    
  
  
  
data segment  
   ends  
  
  
code segment  
    start:  
    mov ax,data  
    mov ds,ax  
      
     
    add ax,50h  
    inc ax  
    sub bx,50h  
    dec bx   
    mov dx,ax  
    mov ax,bx  
    mov bx,dx  
      
         
ends  
end start
```