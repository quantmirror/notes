<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Database Joins
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

#### What is a SQL JOIN 
A SQL Join statement is used to combine data or rows from two or more tables based on a common field between them.
Different types of Joins are:
1. **INNER JOIN**
2. **LEFT JOIN**
3. **RIGHT JOIN**
4. **FULL JOIN**

Consider the two tables below:
###### Students
<table>
    <thead>
    <tr>
        <th>STUDENT_ID</th>
        <th>NAME</th>
        <th>ADDRESS</th>
        <th>PHONE</th>
        <th>AGE</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Kabelo Masemola</td>
            <td>Randburg</td>
            <td>xxxxxxxx</td>
            <td>27</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Bongani Mondlane</td>
            <td>Midrand</td>
            <td>xxxxxxxx</td>
            <td>28</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Edmond Monyebodu</td>
            <td>Midrand</td>
            <td>xxxxxxxx</td>
            <td>28</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Kabelo  Serame</td>
            <td>Soweto</td>
            <td>xxxxxxxx</td>
            <td>30</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Kgotso Masemola</td>
            <td>Randburg</td>
            <td>xxxxxxxx</td>
            <td>18</td>
        </tr>
        <tr>
            <td>6</td>
            <td>Bhavesh Lala</td>
            <td>Midrand</td>
            <td>xxxxxxxx</td>
            <td>38</td>
        </tr>
        <tr>
            <td>7</td>
            <td>Khomotjo Masemola</td>
            <td>Midrand</td>
            <td>xxxxxxxx</td>
            <td>21</td>
        </tr>
        <tr>
            <td>8</td>
            <td>Tshepang Masemola</td>
            <td>Midrand</td>
            <td>xxxxxxxx</td>
            <td>17</td>
        </tr>
    </tbody>

</table>

###### StudentCourse
<table>
    <thead>
        <tr><th>COURSE_ID</th><th>STUDENT_ID</th></tr>
    </thead>
    <tbody>
        <tr><td>1</td><td>1</td></tr>
        <tr><td>2</td><td>2</td></tr>
        <tr><td>2</td><td>3</td></tr>
        <tr><td>3</td><td>4</td></tr>
        <tr><td>1</td><td>5</td></tr>
        <tr><td>4</td><td>9</td></tr>
        <tr><td>5</td><td>10</td></tr>
        <tr><td>4</td><td>11</td></tr>
    </tbody>
</table>


The simplest Join is **INNER JOIN**.<br>
###### INNER JOIN

**INNER JOIN** : The INNER JOIN keyword selects all rows from both the tables as long as the condition satisfies.
This keyword will create the result-set by combining all rows from both the tables where the condition satisfies i.e value 
of the common field will be same.

**syntax** 

```` sql 
SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
INNER JOIN table2
ON table1.matching_column = table2.matching_column;
````
**table1**: First table.<br>
**table2**: Second table<br>
**matching_column**: Column common to both the tables.<br>
<br>
**Note**: We can also write JOIN instead of INNER JOIN. JOIN is same as INNER JOIN.<br>

<img src="https://www.w3schools.com/sql/img_innerjoin.gif"/>

- This query will show the names and age of students enrolled in different courses.
```sql 
    SELECT StudentCourse.COURSE_ID, Student.NAME, Student.AGE FROM Student
    INNER JOIN StudentCourse
    ON Student.STUDENT_ID = StudentCourse.STUDENT_ID;
```

**output**: 
<table>
    <thead>
    <tr>
        <th>COURSE_ID</th>
        <th>NAME</th>
        <th>AGE</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Kabelo Masemola</td>
            <td>27</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Bongani Mondlane</td>
            <td>28</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Edmond Monyebodu</td>
            <td>28</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Kabelo  Serame</td>
            <td>30</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Kgotso Masemola</td>
            <td>18</td>
        </tr>
    </tbody>

</table>

###### LEFT JOIN 
**LEFT JOIN**: This join returns all the rows of the table on the left side of the join and matching rows for the table on the right side of join. 
The rows for which there is no matching row on right side, 
the result-set will contain null. LEFT JOIN is also known as LEFT OUTER JOIN.

**Syntax**:
```sql 
SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
LEFT JOIN table2
ON table1.matching_column = table2.matching_column;

```
**table1**: First table.<br>
**table2**: Second table<br>
**matching_column**: Column common to both the tables.<br>
**Note**:We can also use LEFT OUTER JOIN instead of LEFT JOIN, both are same.<br>
<img src="https://www.w3schools.com/sql/img_leftjoin.gif"/>


- left join example:

```sql 

SELECT StudentCourse.COURSE_ID ,Student.NAME,Student.AGE
FROM Student
LEFT JOIN StudentCourse 
ON StudentCourse.STUDENT_ID = Student.STUDENT_ID;
```

**output**:
<table>
    <thead>
    <tr>
        <th>COURSE_ID</th>
        <th>NAME</th>
        <th>AGE</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Kabelo Masemola</td>
            <td>27</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Bongani Mondlane</td>
            <td>28</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Edmond Monyebodu</td>
            <td>28</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Kabelo  Serame</td>
            <td>30</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Kgotso Masemola</td>
            <td>18</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>Bhavesh Lala</td>
            <td>38</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>Khomotjo Masemola</td>
            <td>21</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>Tshepang Masemola</td>
            <td>17</td>
        </tr>
    </tbody>

</table>


###### RIGHT JOIN

**RIGHT JOIN** :  RIGHT JOIN is similar to LEFT JOIN. This join returns all the rows of the table on the right side of the join and matching rows for the table on the left side of join.
The rows for which there is no matching row on left side,
the result-set will contain null. RIGHT JOIN is also known as RIGHT OUTER JOIN.

**syntax**: 
```sql  
    SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
RIGHT JOIN table2
ON table1.matching_column = table2.matching_column;

```
**table1**: First table.<br>
**table2**: Second table<br>
**matching_column**: Column common to both the tables<br>
**Note**: We can also use RIGHT OUTER JOIN instead of RIGHT JOIN, both are same.<br>
<img src="https://www.w3schools.com/sql/img_rightjoin.gif"/>

- right join example:

```sql
SELECT Student.NAME,StudentCourse.COURSE_ID 
FROM Student
RIGHT JOIN StudentCourse 
ON StudentCourse.STUDENT_ID = Student.STUDENT_ID;

```
**output**:
<table>
    <thead>
    <tr>
        <th>COURSE_ID</th>
        <th>NAME</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Kabelo Masemola</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Bongani Mondlane</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Edmond Monyebodu</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Kabelo  Serame</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Kgotso Masemola</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Null</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Null</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Null</td>
        </tr>
    </tbody>

</table>


###### Full JOIN

**FULL JOIN**:FULL JOIN creates the result-set by combining result of both LEFT JOIN and RIGHT JOIN. 
The result-set will contain all the rows from both the tables. The rows for which there is no matching, 
the result-set will contain NULL values

**syntax**: 
```sql  
SELECT table1.column1,table1.column2,table2.column1,....
FROM table1 
FULL JOIN table2
ON table1.matching_column = table2.matching_column;
    
```
**table1**: First table.<br>
**table2**: Second table<br>
**matching_column**: Column common to both the tables<br>
<img src="https://www.w3schools.com/sql/img_fulljoin.gif"/>

- full join example
```sql  

    SELECT Student.NAME,StudentCourse.COURSE_ID 
FROM Student
FULL JOIN StudentCourse 
ON StudentCourse.STUDENT_ID = Student.STUDENT_ID;
```

**output**:

<table>
    <thead>
    <tr>
        <th>NAME</th>
        <th>COURSE_ID</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>Kabelo Masemola</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Bongani Mondlane</td>
            <td>2</td>
        </tr>
        <tr>
            <td>Edmond Monyebodu</td>
            <td>2</td>
        </tr>
        <tr>
            <td>Kabelo  Serame</td>
            <td>3</td>
        </tr>
        <tr>
            <td>Kgotso Masemola</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Bhavesh Lala</td>  
            <td>Null</td>
        </tr>
        <tr>
            <td>Khomotjo Masemola</td>
            <td>Null</td>
        </tr>
        <tr>
            <td>Tshepang Masemola</td>
            <td>Null</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>9</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Null</td>
            <td>11</td>
        </tr>
    </tbody>

</table>




### Reading material
- <a href="https://www.w3schools.com/sql/sql_join.asp"> W3 Schools </a>
