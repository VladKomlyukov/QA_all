<details>
  <summary>Схема БД</summary>
  ![image_db](https://user-images.githubusercontent.com/89102886/142925743-470faf06-23dc-42c3-8c11-700c4010e08b.png)
  
</details>

1. Вывести всех работников, чьи зарплаты есть в базе, вместе с зарплатами.
```sql
SELECT employees_name, montly_salary
FROM employees
INNER JOIN employees_salary
ON employess.id = employess_salary.id
