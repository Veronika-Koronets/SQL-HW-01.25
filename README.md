# SQL-HW-04.01.25

## СОЗДАТЬ ТАБЛИЦУ
```
CREATE TABLE lekarstva (id int, name char(25), lek_forma char(25), producer char(25), price int, number int, primary key (id));
INSERT INTO lekarstva values
 (1, 'Paracetamol', 'tabletky', 'Pharma', 100, 50),
(2, 'Ibuprofen', 'kapsuly', 'Zdorovye', 150, 30),
(3, 'Aspirin', 'poroshok', 'Medika', 80, 20),
(4, 'Analgin', 'ampuly', 'Pharma', 120, 15),
(5, 'Tsitramon', 'tabletky', 'Zdorovye', 90, 40), 
(6, 'Nimesulid', 'tabletky', 'BioPharma', 110, 25),
(7, 'Loratаdin', 'sirup', 'MediCorp', 140, 60),
(8, 'Diphenhydramine', 'kapsuly', 'HealthFirst', 130, 35),
(9, 'Omeprazole', 'tabletky', 'GastroAid', 200, 18),
(10, 'Simvastatin', 'tabletky', 'CardioMed', 160, 22);
```
##SELECT * from lekarstva;
![image](https://github.com/user-attachments/assets/2ed03c35-e91a-46dc-af04-cf215d5188fb)
![image](https://github.com/user-attachments/assets/20d30b8a-1512-4615-842d-0bbdf48d00e9)



## УДАЛИТЬ ТАБЛИЦУ
```
drop table lekarstva;
```
```
SELECT * from lekarstva;
```

## ИЗМЕНИТЬ СТРУКТУРУ ТАБЛИЦЫ
##добавить новую колонку "seriya"
ALTER TABLE lekarstva add seriya char(25);

##удалить колонку
ALTER table lekarstva drop number;

##переименовать колонку
alter table lekarstva rename column lek_forma to forma;

##изменить тип данных
##alter TABLE lekarstva modify id char(25);

##посмотреть тип данных 
##describe lekarstva;


## ДОБАВИТЬ ДАННЫЕ
insert into lekarstva VALUES (11, 'loperamid', 'kapsuly', 'Borisov', 12, 'SW020324');
INSERT INTO lekarstva (id, forma) VALUES (12, 'ampuly'), (13, 'kapsuly');

## ИЗМЕНИТЬ ДАННЫЕ
UPDATE lekarstva set forma='poroshok' where price =130;
UPDATE lekarstva set seriya='14052024' where forma='tabletky' and producer='BioPharma';

## УДАЛИТЬ ДАННЫЕ
##DELETE FROM lekarstva where seriya is NULL;
##DELETE FROM lekarstva where price >100;

## ВЫБОРКИ
##SELECT name, forma from lekarstva;

##вывеcти уникальные имена проихводителей
##select DISTINCT producer from lekarstva;

##вывести препараты где в названии есть "l"
##SELECT name from lekarstva where name like '%l%'; 

##вывести строки по увеличению цены
##SELECT * FROM lekarstva order by price;

##вывести строки где серия не NULL
##SELECT * from lekarstva where seriya is NOT null;


