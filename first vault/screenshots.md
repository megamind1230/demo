```sql
select count(employee_id) "How Many", sum(salary) "Summation of salaries"
from employees
where department_id = 100;
```

output
![[Pasted image 20221220111414.png]]

```sql
select *
from employees
where first_name = 'Steven' and last_name = 'King';
```
output
![[Pasted image 20221220111521.png]]
---
```sql
select employee_id "emp_No", first_name || ' ' || last_name as "full name" 
from employees
where salary between 12000 and 15000;
```

output
![[Pasted image 20221220111627.png]]

