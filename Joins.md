## 12.01.25 Joins
![image](https://github.com/user-attachments/assets/c2ad2986-bfbe-4ef6-9ba4-178fd3ee68ac)

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
### 2. Вывести start_pair(timepair), name of subject(subject) и teacher(schedule)
```
select timepair.start_pair, subject.name, schedule.teacher
from schedule sch
join timepair tmp
on sch.numper_pair=tmp.id
join subject sbj
on sch.subject=sbj.id
```
### 3. Вывести name(class) и last_name(student)
```
SELECT cls.name, std.last_name
from class cls
join student_in_class sic
on cls.id=sic.class
join student std
sic.student=std.id
```
### 4. Вывести middle_name(teacher), date(schedule) и address(student)
```
SELECT tch.middle_name, sch.date, std.address
from schedule sch
join teacher tch
on sch.teacher=tch.id
join class cls
on sch.class=cls.id
join student_in_class sic
on cls.id=sic.class
join student std
on sic.student=std.id
```
### 5. Вывести first_name(student) и first_name(teacher)
```
select std.first_name, tch.first_name
from class cls
join student_in_class sic
on cls.id=sic.class
join student std
on sic.student=std.id
join schedule sch
on cls.id=sch.class
join teacher tch
on sch.teacher=tch.id
```
(отработает ли последний запрос?)

## Ниже - примеры с занятия:
### 1. Вывести учителя и фамилию ученика
```
select sch.teacher, std.last_name from schedule sch
join class cls
on sch.class=cls.id 
join student_in_class sic
on cls.id=sic.class
join student std
on sic.student=std.id
```
### 2. Вывести name из Class и first_name из teacher
(from schedule т.к. Class и teacher между собой не связаны и так будет проще)
```
select name, first_name from schedule sch
join class cls
on sch.class=cls.name
join teacher tch
on sch.teacher=tch.id
```
