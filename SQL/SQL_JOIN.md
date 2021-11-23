<details>
  <summary>Схема БД</summary>
  ![Db_test_vlad](https://user-images.githubusercontent.com/89102886/143135689-2839d434-3487-411d-89f9-c014a32a1c16.png)
</details>

1. Вывести всех работников, чьи зарплаты есть в базе, вместе с зарплатами.
```sql
SELECT employees_name, montly_salary
FROM employees
INNER JOIN employees_salary ON employess.id = employees_salary.employee_id
```
2.Вывести всех работников, у которых ЗП меньше 2000.
```sql
SELECT employees_name, montly_salary
FROM employees
INNER JOIN employees_salary ON employess.id = employees_salary.employee_id
WHERE montly_salary < 2000;
```
3. Вывести все зарплатные позиции, но работник по ним не назначен. (ЗП есть, но не понятно, кто её получает.)
```sql
SELECT montly_salary, employee_name
FROM employess_salary
LEFT JOIN employess ON employees_salary.employee_id = employess.id
WHERE employee_name IS NULL;
```
4. Вывести все зарплатные позиции меньше 2000, но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```sql
SELECT montly_salary, employee_name
FROM employess_salary
LEFT JOIN employess ON employees_salary.employee_id = employess.id
WHERE montly_salary < 2000 AND employee_name IS NULL;
```
5. Найти всех работников, кому не начислена ЗП.
```sql
SELECT employee_name, montly_salary
FROM employees
LEFT JOIN employess_salary ON employees.id = employess_salary.employee_id
WHERE montly_salary IS NULL;
```
6. Вывести всех работников с названиями их должности.
```sql
SELECT employee_name, role_name
FROM employess
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id;
```
7.








