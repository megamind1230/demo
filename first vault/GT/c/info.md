![[Pasted image 20230105123833.png]]
![[Pasted image 20230105124025.png]]
```c
0 1 are those before 2 .. notice % x == 0 تعني يقبل القسمة على x باقي القسمة دائما أقل من المقسوم عليه
```
![[Pasted image 20230105124209.png]]
#still_GT
-   system conversions
    -   Bin to
        -   Dec
        -  ![[Pasted image 20230105124404.png]]
    -   Dec to { same method }
	    -   Bin
		    - ![[info#1]]
	    -   Oct
		    - ![[info#2]]
	    -   Hex
	        -   needs A = 10 and so on
    -   Oct to
	    - Dec
		    - ![[info#3]]
- octal
    - scanning & printing
	    - ![[info#4]]
-   hexadecimal
    -   printing hex
	    - ![[info#5]]
    -   also can be scanned
	    - ![[info#6]]
-   global var
    - ![[Pasted image 20230105125855.png]]inside fun() > no need for the :: related to the global x specification
    - ![[Pasted image 20230105125928.png]]
- c string p2
	- ![[Pasted image 20230105130008.png]]
-   string header file
    -   some c string funcs { must have string.h included }
        -   strcpy(y, x) copy into y whatever in x ... provided that y is big enough
        -   strcmp(x, y ) gives 0 when same
        -   strcat(x, y ) appends y at the end of x ... provided that x is big enough

-   small tricky syntax
    -   number of digits
        - ![[info#7]]
    -   nested ternary operator
        - `printf(x>0? "+ve" : (x<0 ? "-ve" : "Zero"));`
    -   switch ranges
        - ![[info#8]]
- c write in file
	- ![[info#9]]
-   c read form file
    -   reading one word
        - ![[info#a]]]
    -   reading all chars {one char a time} {using while}
        - ![[info#b]]
    -   optimized scanning
        - reading a string
        - ![[info#c]]
    -   reading all chars using op sc {all chars in a str once} {no while}
        - ![[info#d]]
    -   simple application { email splitting }
        - ![[info#e]]
    -   `\n` trick {don't **unintentional** read it }
        - read a fullname `\n` then a gender char
            - ![[info#f]]
    -   note
        - ![[info#g]]
    -   fclose(x)→x is the ptr to file
- how to trace
	- ![[Pasted image 20230105131539.png]]

---

سؤال واقف !!!
![[Pasted image 20230105144119.png]]


---
# g
```c
 scanf("%[^\n]%*c%c", FullName, &genderChar);
%*c	ignores an unknown char
but when knowing the char for sure and want to ignore it.. put it like

 scanf("%[^\n]\n%c", FullName, &genderChar); 
  scanf("%[^\n]Z%c", FullName, &genderChar);
```
# f
```c
#include <stdio.h>
int main()
{
    char FullName[100];
    scanf("%[^\n]s", FullName);

    scanf("%*c");

    char genderChar;
    scanf("%c", &genderChar);

    /*
    also all 3 scanf can be like
    scanf("%[^\n]%*c%c", FullName, &genderChar);
    */
    printf("%s & %c", FullName, genderChar);
}
```
# e
```c
//splitting email parts { username , canceling @ , domain }

#include <stdio.h>
int main()
{
    char username[100], domain[100];

// reading
    printf("Email with the format username@domain.com : \n");
    scanf("%[^@]s", username);

    //canceling a letter {@}
    scanf("%*c");
    //

    scanf("%[^\n]s", domain);
    //these 3 scanf can be like
    /*
    scanf("%[^@]%*c%[^\n]", username, domain);//better not to use s here
    
    */

// printing

    printf("your username is :%s\n", username);
    printf("your domain is :%s\n", domain);

}
```
# d
```c
//reading.. there should be a file previously

#include <stdio.h>
int main()
{
    FILE * MyFile = fopen("Darwish.txt", "r"); //having the text{hassan darwish}
    char Gulp[200];
    fscanf(MyFile, "%[^EOF]", Gulp);// only one gulping fscanf
    /*same as    
    fscanf(MyFile, "%[^EOF]s", Gulp);// only one gulping fscanf
    */
    printf("%s",Gulp);

}
//out
//	hassan darwish
```
# c
```c
 //optimized scanning.. read until

#include <stdio.h>
int main()
{

    char x[200]; //string
    scanf("%[^#]", x); /*same as

    scanf("%[^#]s", &x);
    }
     where s stands for string*/
    //read whatever .. until {^} reaching the \n {can be any other thing }

    printf("%s",x);
}


/*
tc
in
	flslfkslf fkjf
	dlsj#lkfjs

out
	flslfkslf fkjf
    dlsj
*/
```
# b
```c
//reading.. there should be a file previously

#include <stdio.h>
int main()
{
    FILE * MyFile = fopen("Darwish.txt", "r"); //having the text{hassan darwish}
    char JustAChar;
    while( fscanf(MyFile, "%c", &JustAChar) !=EOF ) //without !=EOF it goes nuts
        printf("%c",JustAChar);
        //prints every char inside MyFile

}
```
# a
```c
//reading.. there should be a file previously
#include <stdio.h>
int main()
{
    FILE * MyFile = fopen("Darwish.txt", "r");
    char firstName[50];
    fscanf(MyFile , "%s",firstName);
    // 1st argument must be the ptr to the file
    printf("%s\n",firstName);
    // { fscanf & fprintf } are specified for file management
}
/*
if Darwish.txt has >>hassan darwish
then output >>hassan
*/
```
# 9
```c
#include <stdio.h>
int main()
{
    FILE * MyFileToWrite= fopen("Write Something.txt","w");
    fprintf(MyFileToWrite, "something yooo\n");//\n is translated 
    //done
    
}
```
# 8
```c
//switch ranges { inclusively }
#include <stdio.h>
int main()
{
    int x;
    scanf("%d",&x);
    switch(x)
    {
    case 100 ... 999: printf("yes %d\n", x); break;
    default: printf("No\n");

    }
main();
}
/*
tc
in
    100
out
    yes 100

in
    999
out
    yes 999
in
    160
out
    yes 160
in
    20
out
    no
*/
```
# 7
```c

#include <stdio.h>
int main()
{
    int x = 1500, counter = 1;
    while(x/=10)
        counter++;
    printf("%d",counter);

}
```
# 6
```c
#include <stdio.h>
int main()
{
    int x = 4; //read int .. print int & hex
    scanf("%d", &x);
    printf("%d\n", x);
    printf("%x\n", x);
    
    scanf("%x", &x);//reading lowercase hex
    printf("%x\n", x);
    printf("%d\n", x);
    printf("\n");
    
    scanf("%X", &x);//reading uppercase hex
    printf("%x\n", x);
    printf("%d\n", x);
}
/*
in
31
out
1f
31

in
1f
out
1f
31

in
10
out
10
16
*/
```
# 5
```c
#include <stdio.h>
int main()
{
    int x = 31; 
    printf("%d\n", x);
    printf("%x\n", x);
    printf("%X\n", x);
}
/*
31
1f
1F
*/ 
```

# 4
```c

#include<iostream>

using namespace std;

int main()
{
   int x = 3;
   scanf("%d", &x);
   printf("%d\n", x);
   printf("%o\n", x);
   
   printf("\n");
   scanf("%o", &x);
   printf("%d\n", x);
   printf("%o\n", x);
}
/*
in
8
out
8
10

in
10
out
8
10
*/
```

# 3
```c
//oct to dec
#include <stdio.h>

int main()
{
    int oct, dec=0, y=1;

    printf("Enter octal \n");
    scanf("%d", &oct);

    while(oct)
    {
        dec+=oct%10*y;
        oct/=10;
        y*=8;
    }
    printf("%d\n", dec);
}
/*
in
17
out
15
*/
```
# 2
```c
#include <stdio.h>
//dec to oct... depending on the modulus method
int main()
{
    int dec;
    printf("Enter a decimal number < 37449\n");
    scanf("%d", &dec);
    if(dec == 0)
    {
        printf("oct = 0 0 0 0 0 0 \n"); // just print all of them 0's
        return 0;
    }

    int oct_digits[7];// 6 + null terminator
    int modulus ;
    int i = 0; // the while counter
    while(dec!=0)
    {
        modulus =  dec % 8;
        oct_digits[i++] = modulus;
        dec /=8;
        /*
        just for testing
        oct_digits[i] = modulus;   dec /=8;
        printf("%d ", oct_digits[i]);
        i++;
        */
    }

    //last index is now i - 1 .. don't forget the effect of the last i++
    printf("oct = ");

    //print the leading left-sided zeros if any 1st.. depending on i value
    for(int j = 6 - 1 ; j>= i ; j--) // 6 - 1 is the index of the last active digit in the array
    {
        printf("0 ");
    }
    //print reversely
    for(int j = i-1 ; j>=0 ; j--)
    {
        printf("%d ", oct_digits[j]);
    }
  printf("\n");
}

/*
Enter a decimal number < 37449
15
oct = 0 0 0 0 1 7 

Enter a decimal number < 37449
37449
oct = 1 1 1 1 1 1

Enter a decimal number < 37449
0
oct = 0 0 0 0 0 0
*/

```
# 1

```c

#include <stdio.h>
//dec to bin... depending on the modulus method
int main()
{
    int dec;
    printf("Enter a decimal number < 1023\n");
    scanf("%d", &dec);
    if(dec == 0)
    {
        printf("bin = 0 0 0 0 0 0 0 0 0 0\n"); // just print all of them 0's
        return 0;
    }

    int bin_digits[11];// 10 + null terminator
    int modulus ;
    int i = 0; // the while counter
    while(dec!=0)
    {
        modulus =  dec % 2;
        bin_digits[i++] = modulus;
        dec /=2;
        /*
        just for testing
        bin_digits[i] = modulus;   dec /=2;
        printf("%d ", bin_digits[i]);
        i++;
        */
    }

    //last index is now i - 1 .. don't forget the effect of the last i++
    printf("bin = ");

    //print the leading left-sided zeros if any 1st.. depending on i value
    for(int j = 10 - 1 ; j>= i ; j--) // 10 - 1 is the index of the last active digit in the array
    {
        printf("0 ");
    }
    //print reversely
    for(int j = i-1 ; j>=0 ; j--)
    {
        printf("%d ", bin_digits[j]);
    }
}

```
