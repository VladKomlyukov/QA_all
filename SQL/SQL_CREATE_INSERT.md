```sql
CREATE TABLE Clients (
id INT PRIMARY KEY,
name VARCHAR(255) NOT NULL,
surname VARCHAR(255) NOT NULL,
age INT NOT NULL DEFAULT 18
);

SELECT * FROM Clients;

INSERT INTO Clients (id, name, surname, age) VALUES (1, 'Vlad', 'Komlyukov', 26);

DELETE FROM Clients WHERE id = 1;

CREATE TABLE Order_all (
  id INT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  surname VARCHAR(255) NOT NULL,
  total_order INT NOT NULL UNIQUE
  );
  
  SELECT * FROM Order_all;
  
  INSERT INTO Order_all (id, name, surname, total_order) VALUES (2, "Ivan", "Ivanov", 15550);
  
  
CREATE TABLE Client_type (
  id INT PRIMARY KEY,
  type VARCHAR(30) NOT NULL
  );
  
  SELECT * FROM Client_type;
  
 INSERT INTO Client_type (id, type) VALUES (15, "Premium client");
  
  
CREATE TABLE Order_info (
  id INT PRIMARY KEY,
  order_id INT NOT NULL UNIQUE,
  type_id INT NOT NULL,
  FOREIGN KEY (order_id) REFERENCES Order_all (id),
  FOREIGN KEY (type_id) REFERENCES Client_type (id)
  );
  

DROP TABLE Order_info;
```
