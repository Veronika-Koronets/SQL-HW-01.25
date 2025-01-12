## 12.01.25 Joins

### 1. Вывести название предмета и студента
```
SELECT subject.name, sic.student 
from schedule sch
join subject
on sch.subject=subject.id
join class cls
on sch.class=cls.id
join student_in_class sic
on cls.id=sic.cls
```
