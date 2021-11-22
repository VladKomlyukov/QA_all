
1. Вывести все поля и все строки.
```sql
SELECT * FROM Clients;
```
2. Вывести всех клиентов в таблице.
```sql
SELECT id, name FROM Clients;
```
3. Вывести id клиентов.
SELECT id FROM Clients;
4. Вывести только имя пользователя клиента;
SELECT user_name FROM Clients;
5. Вывести только e-mail клиента;
SELECT email FROM Clients;
6. Вывести id, имя, email и дату создания пользователей клиентов.
SELECT id, name, email, created_on FROM Clients;
7. Вывести пользователей где пароль - 12345qwerty;
SELECT * FROM Clients WHERE password = "12345qwerty";
9. Вывести пользователей которые были созданы 2021-03-26 00:00:00
SELECT * FROM Clients WHERE created_on='2021-12-31 00:00:00';
10. Вывести пользователей где в имени есть слово Vlad
SELECT * FROM Clients WHERE name LIKE "%Vlad%";
11. Вывести пользователей где в имени пользователя в конце есть 8
SELECT * FROM Clients WHERE user_name LIKE "%8":
12. Вывести пользователей где в начале имени есть буква А
SELECT * FROM Clients WHERE name LIKE "А%";
13. Вывести пользоваетлей где в начале имени есть буква А или буква Б
SELECT * FROM Clients WHERE name LIKE "%A%" OR "%Б%";
14. Вывести пользователей у которых id больше или равен 30
SELECT * FROM Clients WHERE id >= 30;
15. Вывести пользователей у которых id меньше или равен 20
SELECT * FROM Clients WHERE id <= 20;
16. Вывести пользователей у которых id больше 50, но меньше 60
SELECT * FROM Clients WHERE id>50 AND id<60;
17. Вывести пользователей у которых id между 50 и 60
SELECT * FROM Clietns WHERE id BETWEEN 50 AND 60;
18. Вывести пользователей со следующими статусами: Premium, Standart, New
SELECT * FROM Clients WHERE user_status IN ("Premium", "Standart", "New");
19. Вывести id с минимальным значением
SELECT * FROM Clients WHERE id = (SELECT MIN(id) FROM Clients);
20. Вывести id с максимальным значением
SELECT * FROM Clients WHERE id = (SELECT MAX(id) FROM Clients);
21. Вывести общее кол-во пользователей
SELECT Count(*) FROM Clietns;
22. Вывести id пользователя, имя, e-mail пользователя, дату создания. Отсортировать по порядку возрастания даты добавления пользоватлеля.
SELECT id, name, email, created_on FROM Clients ORDER BY created_on;
23. Вывести id пользователя, имя, e-mail пользователя, дату создания. Отсортировать по порядку убывания даты добавления пользоватлеля.
SELECT id, name, email, created_on FROM Clients ORDER BY created_on DESC;
