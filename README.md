# Homework1-CSI2532
Part A

A1

a)

![a1a](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partA/a1a.png)

b)

![image a1b](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partA/a1b.png)

c)

![image a1c](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partA/a1c.png)

A2

![image a2](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partA/a2.png)

Part B

B1a)

![image of b1a](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partB/b1a.png)

B1b)

Here is the output.
![image of b1b](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partB/b1b.png)


B1c)

Added join_date in the parameter to run the function.

![iamge of b1c](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partB/b1c.png)

PartB2

a)

```sql 
  SELECT name FROM users WHERE join_date < '2020-01-01'
  ```
  
b)

```sql
  SELECT  name, COUNT(user_id)as num FROM users LEFT JOIN licenses ON users.id = licenses.user_id GROUP BY name, id having count(*) > 0 ORDER by COUNT(user_id) DESC, name ASC;
  ```
  
c)

![iamge of b2c](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partB/b2c.png)

```sql
  UPDATE softwares
  SET versions = '51', released_date = '2020-01-01'
  WHERE name = 'Sketch';
  ```
  
Part b3

a)

```sql
ALTER TABLE licenses
ADD COLUMN s_version varchar(100);
DROP TABLE licenses;
CREATE TABLE licenses (
 user_id int REFERENCES users (id),
 software_name varchar(200),
 access_code varchar(100),
 PRIMARY KEY (user_id, software_name)
);
ALTER TABLE licenses
ADD COLUMN s_version varchar(100);

INSERT INTO licenses (user_id, software_name, access_code, s_version)
VALUES 
(48,'MS Word','abcd123','2012'),
(49,'MS Word', 'def459','2012'),
(50, 'MS Word', 'hij789','2012'),
(48, 'Sketch', 'x1y2z3', '51'),
(51, 'Sketch', 'x2y3z4', '51'),
(54, 'Chrome', 'dfg299', 'v84');
```
b)

```sql
  ALTER TABLE softwares DROP CONSTRAINT softwares_pkey;
  ALTER TABLE softwares ADD PRIMARY KEY (name, version);
```

c)

d)

```sql
  INSERT INTO licenses (user_id, software_name, access_code, s_version) 
  SELECT id, 'Sketch', '1monthfree', '52' FROM users ON CONFLICT DO NOTHING;
```
