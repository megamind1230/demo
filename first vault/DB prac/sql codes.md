# 1st
```sql
select manager_id , 
nvl(manager_id , 0) , phone_number , 
nvl( phone_number, 'no number added' ) as
“nvl on varchar2” 
from employees;
```

# 2nd
```sql
decode(exp , 
valueToCheck1 , whatToPrintIfCheck1MatchedExp,
 valueToCheck2 , whatToPrintIfCheck2MatchedExp, 
 ...
 WhatToPrintIfNoneWereChecked )
```

# 3rd
```sql
case exp 
when expToCheck1 then print1 
when expToCheck2 then print2 
when expToCheck3 then print3 
..... 
else LastToPrint end
```

# 4th
```sql
case 
when exp = expToCheck1 then print1
when exp = expToCheck2 then print2
when exp = expToCheck3 then print3 
.....
else LastToPrint end
```


# 5th
```sql
select commission_pct 
from employees; 107 
select count(commission_pct) 
from employees;35
/*counts repetitions but not the null vals */
select nvl(commission_pct, 0) 
from employees; 107 
select count(nvl(commission_pct, 0)) 
from employees; 107 
select distinct(commission_pct) 
from employees; 8 
/*with a null inside */
select count(distinct(nvl(commission_pct, 0))) 
from employees; 8 
select count(distinct(commission_pct)) 
from employees; 7 
/*there was an only one null 
value ( null is ignored 'cause of count )*/
```

# 6th
```sql
select 
from 
where 
group by// may be removed sometimes 
having 
order by
/*use `having` right after group by
meanwhile `where` is for conditions on the cols*/
```

# 7th
```sql
select full_name, job_id , salary
from employees
where job_id = 
(select job_id from employees where last_name='Abel') 
and salary = 
(select salary from employees where last_name = 'Abel');
```

# 8th
```sql
/*
لازم تراعي الداتا تايب 

وهل إنه بيقبل تكرار ولا لأ

وهل هو مشتق من جدول آخر فتراعي قيم الآخر..

هل تخطيت الحجم بتاعه لما دخلت القيم ؟

 … إلخ

احنا ممكن نحط قيم شبه عشوائية فقط
للأعمدة اللي بتمثل ال 

primary key

ولكن الأعمدة المشتقة أو اللي جايه من جداول
تانية فدي لازم نراعي فيها الأصل
ومنحطش قيم جديدة عشوائية كده وخلاص
*/

```

# 9th
```sql
/*update is actually > delete + insert

commit rollback

بص علشان نفهمهم

ما بتكون قاعدة البيانات كبيرة
وعليها أكتر من واحد ليه إمكانية
الوصول إليها في نفس الوقت إيه اللي بيحصل

الأول فيه نوعين من العمليات

read { select}

write { insert / update / delete}

لما واحد بيعدل
على البيانات وقبل
ما يعمل commit / rollback

بتكون قاعدة البيانات مقفولة locked

عادي الناس يقرأوا منها البيانات القديمة
لكن ميعرفوش يعدلوا لسه

عادي اللي بيعدل يشوف التعديلات اللي 
هو بيعملها يعني النسخة الحديثة

طيب لما نعمل commit / rollback

كلنا نقدر نشوف التغييرات ..
ويظهر تاني امكانية
ان واحد يعدل بس .. وهكذا

طيب تخيل حصل تعديل على الجدول
في نفس التوقيت بالضبط

يحصل حاجة اسمها deadlock

طيب ينفع ال select تقفل الجدول ؟

لوحدها متقدرش

دا بيحصل لما
ال select ضمن جمل تعديل
علي البيانات

مثلا لما تبقى في sub-query

أو لما حاجة زي الكود دا يحصل
*/

```

