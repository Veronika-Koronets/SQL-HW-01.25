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
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/2ed03c35-e91a-46dc-af04-cf215d5188fb)
![image](https://github.com/user-attachments/assets/20d30b8a-1512-4615-842d-0bbdf48d00e9)



## УДАЛИТЬ ТАБЛИЦУ
!!! after the request was completed it was muted
```
drop table lekarstva;
```

```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/cf18591e-65ad-44ac-b725-a93d8f7817bd)


## ИЗМЕНИТЬ СТРУКТУРУ ТАБЛИЦЫ

### 1) добавить новую колонку "seriya"
```
ALTER TABLE lekarstva add seriya char(25);
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/4892a71c-dbb3-49fe-85c7-b485a9f19a19)

### 2) удалить колонку
```
ALTER table lekarstva drop number; --удалить колонку ``number``
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/19593fc5-f586-4ee4-bffc-e7c0b39b545a)


### 3) переименовать колонку
```
alter table lekarstva rename column lek_forma to forma;
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/ad24fd4a-4e53-4a0a-b30a-66657cf01057)


### 4) изменить тип данных
!!! after the request was completed it was muted
```
alter TABLE lekarstva modify id char(25);
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/04652239-dd1d-4b9b-a092-3715a23ebca0)


### посмотреть тип данных 
! to make sure that the data type has been changed, we will run another query
```
describe lekarstva;
```
![image](https://github.com/user-attachments/assets/a64b9ba6-6598-45df-95d4-7ea6c12b0ef0)


## ДОБАВИТЬ ДАННЫЕ
1)
```
insert into lekarstva VALUES (11, 'loperamid', 'kapsuly', 'Borisov', 12, 'SW020324');
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/cc375158-9f63-4539-9349-c3442aaf8517)
![image](https://github.com/user-attachments/assets/331d00cf-f84d-4b07-9b46-05cc8fd8ffce)

2)
```
INSERT INTO lekarstva (id, forma) VALUES (12, 'ampuly'), (13, 'kapsuly');
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/cc375158-9f63-4539-9349-c3442aaf8517)
![image](https://github.com/user-attachments/assets/c8443da3-7e35-4156-b09b-6d3692057698)

## ИЗМЕНИТЬ ДАННЫЕ
1)
```
UPDATE lekarstva set forma='poroshok' where price =130;
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/4e85eb95-d995-4b27-8463-0f047fa48cd1)
![image](https://github.com/user-attachments/assets/a0ff8fb9-b826-4fde-8ed7-f7505ae1e264)

changed string where id=8

2)
```
UPDATE lekarstva set seriya='14052024' where forma='tabletky' and producer='BioPharma';
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/7eadb009-fce3-42d6-a6c5-13b984d82ee4)
![image](https://github.com/user-attachments/assets/c14c637a-d24d-4f8a-933d-003113500ad5)

changed string where id=6

## УДАЛИТЬ ДАННЫЕ
!!! after these requests were executed, they were muted

1)
```
DELETE FROM lekarstva where seriya is NULL;
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/0bcee47a-8ec0-4c48-8686-e14dc6b3ee0f)

2)
```
DELETE FROM lekarstva where price >100;
```
```
SELECT * from lekarstva;
```
![image](https://github.com/user-attachments/assets/e54f5b7c-5712-42fd-b8e9-37948c572a47)

## ВЫБОРКИ
!!! these requests were made separately, not consecutively
1) вывести колонки "name" и "forma":
```
SELECT name, forma from lekarstva;
```
![image](https://github.com/user-attachments/assets/0c45ba42-b4e6-4a50-a2b7-0d9089d84592)
![image](https://github.com/user-attachments/assets/934573a8-77a9-47b2-9e82-0ec8253a819e)

## 2) вывеcти уникальные имена проихводителей:
```
select DISTINCT producer from lekarstva;
```
![image](https://github.com/user-attachments/assets/a655bb4f-c5a7-4d2b-9288-aa943304a385)
![image](https://github.com/user-attachments/assets/a562e353-5819-411b-97dc-cb6904974602)

## 3) вывести препараты где в названии есть буква "l":
```
SELECT name from lekarstva where name like '%l%'; 
```
![image](https://github.com/user-attachments/assets/4f72b6fd-4442-415f-8f6c-4d44616df000)

## 4) вывести строки по увеличению цены:
```
SELECT * FROM lekarstva order by price;
```
![image](https://github.com/user-attachments/assets/51d893b4-c18e-4b1c-a992-b65091eca643)
![image](https://github.com/user-attachments/assets/2473fc12-3acf-4682-b684-3b110e5a1431)

## 5) вывести строки где серия не NULL:
```
SELECT * from lekarstva where seriya is NOT null;
```
![image](https://github.com/user-attachments/assets/5fe7882e-776a-4662-b95e-6fce1c06a7a7)

