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
### 4.
```

```
### 5.
```

```
