# لو مثلا في الجدول التاني فيه job_id  بس مش في الأول
```SQL
select id, first_name , salary , 'no job' job_id
from table1
operator
select id , first_name , {0} ,job_id
from table2;
```

من الآخر بعوض بحاجة تبقى بنفس نوع العمود الزيادة اللي موجود في الجدول

لو كنت عايز احط null بحولها الأول نفس نوع العمود
```sql
select id , first_name , salary
from table1
operator
select id , first_name , to_number(null)
from talbe2;
```

---

# ch8 using the set operators
ندمج ( نطلع ناتج واحد) جدول واجد لجملتين select
- sets operators
	- union بدون تكرار
	- union all
	- intersect بدون تكرار
	- minus بدون تكرار صwithout duplicates
syntax
```sql
select col1 , col2
from table1
set oparator
select col1 , col2
from talbe2; // لاحظ إن ال ; وحيدة
```
- الشروط
	- لازم يكون عدد الأعمدة في جملة ال select الأولى = العدد في التانية
	- لازم كل عمود  بيقابل عمود في الجدول التاني (يكونوا من نفس النوع)
	- لازم يكون كل الأعمدة الموجودة في الجملتين ليهم نفس النوع
مش لازم يكون الأعمدة ليها نفس الاسم في الجملتين عشان ديما الجدول الناتج هيكون بأسامي أعمدة الجملة الأولى
![[جدولين بينهم تشابهات.png]]

---

# Ex 1 : union
```sql
select id , first_name
from table1
union
select id, first_name
from table2;
```
بالشكل دا بترجع الصفوف في الجدول الأول + الثاني بدون تكرار لأنها اتحاد
![[الجدول الناتج من اليونيون.png]]

# Ex 2 : union all
بترجع كل الصفوف وبتكرار
وبالتالي هيرجعلي جدول فيه 7 صفوف بقا بحيث إن علي مكررة مرتين
# Ex 3 : intersect

بتجيب التقاطع بدون تكرار .. بالتالي ترجع صف بس بتاع علي .. مش هيرجع إلا اللي تشابه بشكل تام

---

# لو عايز اعمل order by 
وارتب تنازلي
```sql
select id , first_name
from table1
union
select id, first_name
from table2
order by id desc;// آخر حاجة // وكمان بترتب باللي في الجدول الأول
```


- طيب تخيل 
	- إن id في الجدول 
		- الأول كانت varchar2 
		- التاني number
			- هيطلع ايرور لأنهم مش نفس النوع .. والحل في الكاستنيج
		- إنه فيه في العمود الأول salary ومش في التاني
			- هتحط ندها في الجدول التاني 0 مثلا

---

# Ex 4: minus

هي هي بتاعة زي بتاعة الفرق في العربي
اللي موجود في الأول ومش في التاني

- ملحوظات
	- الأعمدة في ال output هي هي نفسها بأسماء الجدول الأول
	- ال output هيرجع تصاعدي باعتبار العمود الأول
		- ![[ترتيب تصاعدي.png]]
	- لو عايز تعرض تستعمل `*`
		- يبقى لازم تعملها في الاتنين وإلا تاخد ايرور![[using asterisk.png]]


