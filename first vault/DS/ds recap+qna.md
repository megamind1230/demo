```c
char str1[100] = "This is ", str2[] = "programiz.com";

   // concatenates str1 and str2
   // the resultant string is stored in str1.
   strcat(str1, str2);

   puts(str1);
   puts(str2);
/*This is programiz.com
programiz.com*/
```

```cpp
//string funcs
y.assign(x) or y = x
//---------------------
#include <bits/stdc++.h>
using namespace std;
#define sp <<' '<<
#define ln <<'\n';
int main()
{
string str; getline(cin, str);
//reads the new line an deletes it from the buffer
char a; cin>> a;
string str1; getline(cin, str1);
cout<< str  sp str1 ln
// getline(cin< str,terminatorChar)
//cin.ignore() release what's in the buffer of str
}
/*
ha sa
mo dar
ha sa o dar
*/
//---------------------
x.at(i) or x[i]
s.size() is better in complexity than s.length()
substr(st, howLong) ... substr(4) means from [4] till the end
a.swap(b) to swap strings

//----------------------
#include <bits/stdc++.h>
using namespace std;
#define sp <<' '<<
#define ln <<'\n';
int main()
{

#ifndef ONLINE_JUDGE
    freopen("input.txt",  "r",  stdin);
    freopen("output.txt", "w", stdout);
#endif
    string name = "armandor";
    cout<< name.find_first_of("am") ln//finds for either the whole string on its chars //0
    cout<< name.find("am") ln // searches for the specified "am"//npos

    cout<< name.find("r") ln // LTR search // 1
    cout<< name.rfind("r") ln // RTL search // 7


		string num = "6543215";
    cout<< num.find("321") ln // LTR search // 3
    /*
    654{(3)21}5
    012{(3)54}6 ->> 3

    */
    cout<< num.rfind("543") ln // RTL search // 1
     /*
    6{(5)43}215
    0{(1)23}456 ->> 1

    */
string a, b, c ; a = b = c = "655342387";
    a.erase(0); cout<< a ln//nothing
    b.erase(3); cout<< b ln //655
    c.erase(3,5); cout<< c ln //6557 // erase(st, length)
//erase(lengthOfStr) or erase(0,length)
d.replace(3,5," Deleted "); cout << d ln //655 Deleted 7 
// replace(st, length , something)
}
//----------------------
str.push_back(ch)  works ok also pop_back() , clear() , str.resize(newsize)
a.insert(4," hello ");//a  = "something"
    cout<< a ln //some hello thing
//-------------
string a; a = "something";
    cout<< a.empty() ln //0
    a.clear();
    cout << a.empty() ln //1
//-------
```
![[Pasted image 20230102103707.png]]

---
---
---

# qna

### 2021
![[Pasted image 20230102103942.png]]
![[Pasted image 20230102104003.png]]
![[Pasted image 20230102104010.png]]
![[Pasted image 20230102104019.png]]
![[Pasted image 20230102104030.png]]
![[Pasted image 20230102104053.png]]
![[Pasted image 20230102104137.png]]
![[Pasted image 20230102104200.png]]
![[Pasted image 20230102104326.png]]
![[Pasted image 20230102104344.png]]
![[Pasted image 20230102104402.png]]
![[Pasted image 20230102112030.png]]
![[Pasted image 20230102104415.png]]
![[Pasted image 20230102104449.png]]
![[Pasted image 20230102104510.png]]
![[Pasted image 20230102104527.png]]
![[Pasted image 20230102111913.png]]


---
### 2022
![[Pasted image 20230102123259.png]]
![[Pasted image 20230103094323.png]]
![[Pasted image 20230103094343.png]]

![[Pasted image 20230103094449.png]]
![[Pasted image 20230103095220.png]]
![[Pasted image 20230103094517.png]]
معلق=leaf vertex
![[Pasted image 20230103165059.png]]
![[Pasted image 20230102132241.png]]
![[Pasted image 20230102132730.png]]
![[Pasted image 20230103094844.png]]
![[Pasted image 20230103095007.png]]
![[Pasted image 20230103093306.png]]
![[Pasted image 20230103180416.png]]
![[Pasted image 20230103181022.png]]
![[Pasted image 20230103180506.png]]
#still_ds

```c
// working
typedef struct student
{
 int no;
 char name[20];
} something;
	//student here is redundant... maybe
int main()
{
set_evni();
something a = {20, "hassan"};
   printf("%i\n%s" , a.no, a.name); 
}
//-------------
typedef struct 
{
 int no;
 char name[20];
}student;

int main()
{
set_evni();
student z = {20, "hassan"};
   printf("%i\n%s" , z.no, z.name);
}


```
![[Pasted image 20230103105249.png]]
في السلايدات بيقول انها شغالة
ودا مش صحيح 
اغلب ال compilers مش شغالة فيها
tree 
	level > بنعدها بال ادج
	height > بالنودز
	![[Pasted image 20230103112600.png]]



---
### book mcq
![[Pasted image 20230103153407.png]]
`%i` =  format specifier
`%h` for short
ch1
![[Pasted image 20230103153732.png]]
![[Pasted image 20230103153819.png]]
![[Pasted image 20230103154401.png]]
![[Pasted image 20230103154557.png]]
![[Pasted image 20230103154623.png]]
ch2
![[Pasted image 20230103154755.png]]
![[Pasted image 20230103154834.png]]
![[Pasted image 20230103154925.png]]
![[Pasted image 20230103155325.png]]
ch3
![[Pasted image 20230103155923.png]]
ch5
![[Pasted image 20230103160524.png]]
![[Pasted image 20230103160601.png]]
ch6
![[Pasted image 20230103160954.png]]
ch7
![[Pasted image 20230103161110.png]]
ch8
![[Pasted image 20230103161237.png]]
![[Pasted image 20230103161322.png]]
لانك بتتعامل مع الاطراف
![[Pasted image 20230103161505.png]]
ch9 trees
![[Pasted image 20230103162019.png]]
![[Pasted image 20230103161725.png]]
![[Pasted image 20230103162101.png]]
![[Pasted image 20230103163008.png]]
#still_ds 
واضح السؤال فيه غلطة بالنسبالي
```text
#nodes just at the specific nth level in binary tree = 2^n
#nodes at the nth level and before = (2^[n+1] -1 ) as max
```

ch10 efficient binary tree
![[Pasted image 20230103163532.png]]
![[Pasted image 20230103163642.png]]
![[Pasted image 20230103163940.png]]
![[Pasted image 20230103164436.png]]
#still_ds 
![[Pasted image 20230103165910.png]]
![[Pasted image 20230103170153.png]]
![[Pasted image 20230103165916.png]]
![[Pasted image 20230103170201.png]]

ch13 graphs
![[Pasted image 20230103173444.png]]
3 امال ايه strongly connected ?
![[Pasted image 20230103174111.png]]
![[Pasted image 20230103173839.png]]
![[Pasted image 20230103174051.png]]
![[Pasted image 20230103173603.png]]
#still_ds 

ch12 heaps

**1]** The binary heap is  
==(a)   a complete binary tree==   	(b)   a binary tree
(c)   both a, b 	(d)   none

 

**2]** The complexity of inserting a single value in a binary tree

(a)   O(n)  		(c)   O(n log n) 
==(b)   O(log n)==		(d)   O(n2)

 

**3]** The height of a binary heap with n nodes is equal to
  
(a)   n) 		(c)  n log n
 
==(b)   log2(n) ==		(d)   n2

 

**4]** An element at position i in an array has its ==left== child stored at position 
 ==(a)   2i==  (b)   2i + 1
 
 (c)   i/2  (d)   i/2 + 1
 
 

**5]** In the worst case, how much time does it take to ==build== a binary heap of n elements? 
(a)   O(n)  (b)   O(log n)

==(c)   O(n log n)==  (d)   O(n2)

 

**6]** The height of a binomial tree Bi is
(a)   2i   	(b)   2i + 1

(c)   i/2 	==(d)   i==

 
**7]** How many nodes does a binomial tree of order 0 have?
  
(a)   0  ==(b)   1==

(c)   2  (d)   3

 

**8]** The running time of Link_Binomial_Tree() procedure is 
(a)   O(n)  (b)   O(log n)

(c)   O(n log n)  ==(d)   O(1)== 

 
**9]** In a Fibonacci heap, how much time does it take to find the ==minimum== node?
  
(a)   O(n)  (b)   O(log n)

(c)   O(n log n)  ==(d)   O(1)==

 
**10]** An application of heaps is

(a)heap sort  	(b)in some selection algos

(c)in some graph algos	==(d) all mentioned== 


 
**11]** A binomial tree Bi of height i has .. nodes.

==(a)2^i==  	(b)2

(c)i^2	(d) log(i)

 
**12]** A binomial heap H is a collection of ... trees.

(a)binary  	==(b)binomial==

(c)Apple	(d) Microsoft

 

**13]** Every tree in the binomial heap satisfies what property ?

==(a)the minimum heap property==  	(b)the maximum heap property

(c)there can be 1 / 0 binomial trees for each order including 2 order	(d) none

 

**14]** Fibonacci heaps differ from binomial heaps, as Fibonacci heaps have a more... structure, allowing 
improved... time bounds.

(a)relaxed, synchronous  	(b)relaxed, asynchronous

==(c)relaxed, asymptotic==	(d) none

 

**15]** In binary heaps, if an element is at position i in the array, then its ==right== child is at position

(a) 2i  	==(b) 2i+1==

(c) i	(d) 2^i

 

**16]**  In binary heaps, If B is a child of A, then
 key(A) ... key(B), only 
when it's in the... heap state

(a)<= , minimum  	(b) > , maximum

(c) >= , maximum	==(d) both a, c==

---

ch14 searching / sorting
![[Pasted image 20230103181117.png]]
![[Pasted image 20230103181135.png]]
![[Pasted image 20230103181253.png]]
#still_ds 
![[Pasted image 20230103181323.png]]
![[Pasted image 20230103181346.png]]
![[Pasted image 20230103181404.png]]
![[Pasted image 20230103181502.png]]
#still_ds 
![[Pasted image 20230103181533.png]]
![[Pasted image 20230103181548.png]]
#still_ds 

---
ch15 hashing and collision #still_ds 
![[Pasted image 20230103181819.png]]
![[Pasted image 20230103181902.png]]![[Pasted image 20230103181923.png]]
![[Pasted image 20230103182015.png]]


mid 17
غريبة خالص
![[Pasted image 20230103182450.png]]
#still_ds 
