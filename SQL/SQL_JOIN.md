<details>
  <summary>Схема базы данных</summary>
  
  ![drawSQL-emploeesDB](https://user-images.githubusercontent.com/83915765/136953203-86a40d2f-3a8c-4e16-955c-34d0e638b6f9.png)
 </details>

1. Вывести всех работников, чьи зарплаты есть в базе, вместе с зарплатами.
```sql
SELECT employees_name, montly_salary
FROM employees
INNER JOIN employees_salary ON employess.id = employees_salary.employee_id
```
2. Вывести всех работников, у которых ЗП меньше 2000.
```sql
SELECT employees_name, montly_salary
FROM employees
INNER JOIN employees_salary ON employess.id = employees_salary.employee_id
WHERE montly_salary < 2000;
```
3. Вывести все зарплатные позиции, но работник по ним не назначен. (ЗП есть, но не понятно, кто её получает.)
```sql
SELECT montly_salary, employee_name
FROM employees_salary
LEFT JOIN employess ON employees_salary.employee_id = employees.id
WHERE employee_name IS NULL;
```
4. Вывести все зарплатные позиции меньше 2000, но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```sql
SELECT montly_salary, employee_name
FROM employees_salary
LEFT JOIN employess ON employees_salary.employee_id = employess.id
WHERE montly_salary < 2000 AND employee_name IS NULL;
```
5. Найти всех работников, кому не начислена ЗП.
```sql
SELECT employee_name, montly_salary
FROM employees
LEFT JOIN employees_salary ON employees.id = employees_salary.employee_id
WHERE montly_salary IS NULL;
```
6. Вывести всех работников с названиями их должности.
```sql
SELECT employee_name, role_name
FROM employees
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id;
```
7. Вывести имена и должность только Java разработчиков.
```sql
SELECT employee_name,role_name
FROM employees
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE roles_name LIKE '%Java developer%';
```
8. Вывести имена и должность только Python разработчиков.
```sql
SELECT empployee_name, role_name
FROM employees
INNER JOIN roles_employees ON emplyees.id - roles_employess.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE roles_name LIKE '%Python developer%';
```
9. Вывести имено и должность только QA-инженеров.
```sql
SELECT employee_name, role_name
FROM employees
INNER JOIN roles_employees ON employee.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE roles_name LIKE '%QA-engineer%';
```
10. Вывести имена и зарплаты Junior-специалистов.
```sql
SELECT employee_name, montly_salary
FROM employees_salary
INNER JOIN salary ON employees.id = employees_salary.employee_id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%Junior%';
```
11. Вывести зарплаты Java разработчиков
```sql
SELECT montly_salary
FROM employees_salary
LEFT JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employess.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%Java Developer%';
```
12. Вывести имена и зарплаты Junior Python разработчиков
```sql
SELECT montly_salary
FROM employees_salary
LEFT JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%Python Developer%';
```
13. Вывести среднюю зарплату всех Junior специалистов
```sql
SELECT AVG(montly_salary)
FROM employees_salary
INNER JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%Junior%';
```
14.Вывести сумму зарплат всех разработчиков на JavaScript
```sql
SELECT SUM(montly_salary)
FROM employees_salary
INNER JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%JavaScript Developer%';
```
15. Вывести минимальную ЗП QA инженеров
```sql
SELECT MIN(montly_salary)
FROM employees_salary
INNER JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%QA engineer%';
```
16. Вывести максимальную ЗП QA инженеров
```sql
SELECT MAX(montly_salary)
FROM employees_salary
INNER JOIN employees ON employees_salary.employee_id = employees.id
INNER JOIN roles_employees ON employees.id = roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%QA engineer%';
```
17. Вывести количество QA инженеров
```sql
SELECT COUNT(montly_salary)
FROM employees
INNER JOIN roles_employees ON employees.id - roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE role_name LIKE '%QA engineer%';
```
18. Вывести имена, должности и ЗП всех специалистов по возрастанию
```sql
SELECT employee_name, role_name, montly_salary
FROM employees
LEFT JOIN employees_salary ON employees.id = employees_salary.employees_id
INNER JOIN roles_employees ON employees.id - roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
ORDER BY montly_salary;
```
19. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов, у которых ЗП от 1700 до 2500
```sql
SELECT employee_name, role_name, montly_salary
FROM employees
LEFT JOIN employees_salary ON employees.id = employees_salary.employees_id
INNER JOIN roles_employees ON employees.id - roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE montly_salary BETWEEEN 1700 AND 2500
ORDER BY montly_salary;
```
20. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов, у которых ЗП меньше 2500
```sql
SELECT employee_name, role_name, montly_salary
FROM employees
LEFT JOIN employees_salary ON employees.id = employees_salary.employees_id
INNER JOIN roles_employees ON employees.id - roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE montly_salary < 2500
ORDER BY montly_salary;
```
21. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов, у которых ЗП равна 1100, 1500, 2000
```sql
SELECT employee_name, role_name, montly_salary
FROM employees
LEFT JOIN employees_salary ON employees.id = employees_salary.employees_id
INNER JOIN roles_employees ON employees.id - roles_employees.employee_id
INNER JOIN roles ON roles_employees.role_id = roles.id
WHERE monthly_salary IN (1100, 1500, 2000)
ORDER BY montly_salary;
```
