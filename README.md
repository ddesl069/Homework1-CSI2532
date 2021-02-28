
# Homework1-CSI2532

Dante Deslauriers 300114162

Part A

A1

a)

![a1a](https://github.com/ddesl069/Homework1-CSI2532/blob/main/partA/a1a.png)

b)

![image a1b](<img width="495" alt="a1b" src="https://user-images.githubusercontent.com/64750637/109406305-ec5aa580-7945-11eb-9dc9-a06fed36148a.png">)

c)

![image a1c](<img width="482" alt="a1c" src="https://user-images.githubusercontent.com/64750637/109406311-f54b7700-7945-11eb-8ab5-878d314861e8.png">
)

A2

![image a2](<img width="488" alt="a2" src="https://user-images.githubusercontent.com/64750637/109406313-fc728500-7945-11eb-8a0b-585e8bc396da.png">
)

Part B

B1a)

![image of b1a](<img width="62" alt="b1a" src="https://user-images.githubusercontent.com/64750637/109406321-0a280a80-7946-11eb-97f5-e8b1a6be2e35.png">
)

B1b)

Here is the output.

![image of b1b](<img width="275" alt="b1b" src="https://user-images.githubusercontent.com/64750637/109406327-10b68200-7946-11eb-9255-90f32c74398a.png">
)


B1c)

Added join_date in the parameter to run the function.

![iamge of b1c](<img width="174" alt="b1c" src="https://user-images.githubusercontent.com/64750637/109406331-18762680-7946-11eb-8610-0e7d71236dda.png">
)

PartB2

a)

```sql 
  SELECT name FROM users WHERE join_date < '2020-01-01'
  ```
  
b)

```sql
  SELECT  name, COUNT(user_id)as num FROM users LEFT JOIN licenses ON users.id = licenses.user_id GROUP BY name, 
  id having count(*) > 0 ORDER by COUNT(user_id) DESC, name ASC;
  ```
  
c)

![iamge of b2c](<img width="151" alt="b2c" src="https://user-images.githubusercontent.com/64750637/109406336-23c95200-7946-11eb-95b4-0fccf13a5813.png">
)

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

```sql
  INSERT INTO licenses(user_id, software_name, access_code, s_version)
  SELECT DISTINCT user_id, 'Sketch', '1monthfree', '52' FROM licenses
  WHERE software_name = 'Sketch' AND s_version <> 52;
```
d)

```sql
  INSERT INTO licenses (user_id, software_name, access_code, s_version) 
  SELECT id, 'Sketch', '1monthfree', '52' FROM users ON CONFLICT DO NOTHING;
```
