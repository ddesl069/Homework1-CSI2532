# Homework1-CSI2532
#Part A

#A1

#a)

![Image of A1](https://github.com/ddesl069/Homework1-CSI2532/blob/main/part1(ER)/E-R%20A1a)%20(Homework1).png)

#b)

![A1b](https://github.com/ddesl069/Homework1-CSI2532/blob/main/part1(ER)/E-R%20A1b)%20(Homework1).png)

#c)

![A1c](https://github.com/ddesl069/Homework1-CSI2532/blob/main/part1(ER)/E-R%20A1c)%20(Homework1).png)

#Part B

#B1a)

#B1b)

#Here is the output.

![image of B1b](https://github.com/ddesl069/Homework1-CSI2532/blob/main/part2/partB1.b).PNG)

#B1c)

#Added join_date in the parameter to run the function.

![image of B1c](https://github.com/ddesl069/Homework1-CSI2532/blob/main/part2/partB1.c).PNG)

#PartB2

#a)

```sql 
  SELECT name FROM users WHERE join_date < '2020-01-01'
  ```
  
#b)

```sql
  SELECT name, COUNT(user_id)as FROM users LEFT JOIN licenses on users.id = licenses.user_id
  GROUP BY name, id having count(*) >0 ORDER by COUNT(USER_id) DESC, name ASC;
  ```
  
#c)

![]()

```sql
  UPDATE softwares
  SET versions = '51', released_date = '2020-01-01'
  WHERE name = 'Sketch';
  ```
  
