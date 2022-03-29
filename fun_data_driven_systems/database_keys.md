<p align="center" style="background-color:"><img src="https://raw.githubusercontent.com/quantmirror/notes/master/assets/logo.jpeg?token=GHSAT0AAAAAABSSDUBE4DOCZIWGTDVZ4AZ6YSDD4FQ"  width="400"></p>
<p align="center"><h2 style="color: #193967; text-align: center">
    Database Keys
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

### What are database keys?

A key in RDBMS is an attribute or a set of attributes that help 
to uniquely identify a tuple (or row) in a relation (or table). 
Keys are also used to establish relationships between the different
tables and columns of a relational database.
Individual values in a key are called key values.

### Why are the Keys Required?
A key is used in the definitions of various kinds of integrity constraints.
A table in a database represents a collection of records or events for a 
particular relation. Now there can be thousands and thousands of such records, 
some of which may be duplicated.

There should be a way to identify each record separately and uniquely, i.e. no duplicates.
Keys allow us to be free from this hassle.
Let us take a real-life example of the database of each student studying in an engineering college.


What attribute of the student do you think will uniquely identify each of them? 
You could refer to a student by using their name, department, year and section. 
Or, you can mention only 
the university roll number of the student, and you can get all the other details from that. 

A key could either be a combination of more than one attribute (or columns) or just a single attribute. The main motive of this is to give each record a **unique identity** .

### Types of Keys in DBMS

1. Primary Key
2. Candidate Key
3. Super Key
4. Foreign Key
5. Composite Key
6. Alternate Key
7. Unique

Let’s look at each of them separately.
<br>
#### 1. Primary Key 
A primary key is a column of a table or a set of columns that helps to identify every record present in that table uniquely.
There can be only one primary Key in a table. Also, the primary Key cannot have the same values repeating for any row. 
Every value of the primary key has to be different with no repetitions.

The **PRIMARY KEY (PK)** constraint put on a column or set of columns will not allow them to have any null values or any duplicates.
One table can have only one primary key constraint. Any value in the primary key cannot be changed by any foreign keys (explained below)
which refer to it.

#### 2. Super key
Super Key is the set of all the keys which help to identify rows in a table uniquely. 
This means that all those columns of a table than capable of identifying the other
columns of that table uniquely will all be considered super keys.

Super Key is the superset of a candidate key (explained below).
The Primary Key of a table is picked from the super key set to be made the table’s identity attribute.

#### 3. Candidate Key
Candidate keys are those attributes that uniquely identify rows of a table. The Primary Key of a table is selected from one of the candidate keys. 
So, candidate keys have the same properties as the primary keys explained above.
There can be more than one candidate keys in a table.

#### 4. Alternate Key
As stated above, a table can have multiple choices for a primary key; however, 
it can choose only one. So, all the keys which did not become the primary Key are called alternate keys.

#### 5. Foreign Key
Foreign Key is used to establish relationships between two tables. A foreign key will require each value in a column or set of columns to match the Primary Key of the referential table. 
Foreign keys help to maintain data and referential integrity.

#### 6. Composite Key
Composite Key is a set of two or more attributes that help identify each tuple in a table uniquely.
The attributes in the set may not be unique when considered separately.
However, when taken all together, they will ensure uniqueness.

#### 7. Unique Key
Unique Key is a column or set of columns that uniquely identify each record in a table. All values will have to be unique in this Key.
A unique Key differs from a primary key because it can have only one null value, whereas a primary Key cannot have any null values.

### Functional Dependencies
Now that we know a different kind of keys in DBMS, 
let’s see how to identify them when given a table from a database.
For this, we use the concept of functional dependencies.<br>

A functional dependency (FD) is a constraint between two sets of attributes.
This constraint is for any two tuples t1 and t2 in r if t1[X] = t2[X], then they have t1[Y] = t2[Y]. 
This means the value of the X component of a tuple uniquely determines the value of component Y. 


FD is denoted as X ? Y (this is read as “Y is functionally dependent on X”).
The left side is called the determinant, and the right side is called the dependent.

### Closure of a set of Attributes

A **closure** is a set of all possible FDs derived from a given set of FDs. It is also referred to as a **complete** set of FDs. 
If F is used to donate the set of FDs for relation R, then the closure of a set of FDs implied by F is denoted by **F+**.

We will now define the closure of a set of attributes concerning a given set of FDs.
It will help **identify the super Key** of the relationship and find whether an FD can be inferred from a given set of FDs or an FD is redundant. 
After finding a set of functional dependencies on a relation, the next step is to find the Super Key for that relation (table).


Then we find out the set of attributes’ closure to decide whether an attribute (or set of attributes) of any table is a key for that table or not. 
The **set of attributes** that are functionally dependent on the attribute X is called Attribute Closure of X, and it can be represented as X+.

Below are some rules needed to determine F+:

1. **Reflexivity** : If X is a superset of Y or Y is a subset of X, then X ? Y.
2. **Augmentation**: If X ? Y, then XZ ? YZ. Or If Z ⊆W, and X ? Y, then XW ? YZ.
3. **Transitivity**: If X ? Y and Y ? Z, then X ? Z.
4. **Union** : If X ? Y and X ? Z, then X ? YZ.
5. **Decomposition** : If X ? YZ, then X ? Y and X ? Z.
6. **Pseudo-Transitivity** : If X ? Y and YW ? Z, then XW ? Z.

This subject will be continued in later notes. 

### Reading material
- <a href="https://www.guru99.com/dbms-keys.html">guru99 </a>
- <a href="https://www.studytonight.com/dbms/database-key.php">study tonight </a>
- <a href="https://www.learncomputerscienceonline.com/database-keys/">www.learncomputerscienceonline.com </a>
- <a href="https://en.wikipedia.org/wiki/Primary_key">Wikipedia primary Key</a>
- <a href="https://en.wikipedia.org/wiki/Superkey">Wikipedia super Key</a>
- <a href="https://www.analyticsvidhya.com/blog/2020/07/difference-between-sql-keys-primary-key-super-key-candidate-key-foreign-key/#:~:text=What%20is%20a%20Super%20key,they%20can%20identify%20tuples%20uniquely.">analyticsvidhya super key </a>
- <a href="https://www.techopedia.com/definition/21/candidate-key#:~:text=A%20candidate%20key%20is%20a,in%20a%20relational%20database%20table.">Candidate key </a>
- <a href="https://www.analyticsvidhya.com/blog/2020/07/difference-between-sql-keys-primary-key-super-key-candidate-key-foreign-key/#:~:text=Alternate%20or%20Secondary%20keys%20in,Primary%20key%20for%20a%20table.&text=They%20can%20also%20uniquely%20identify,key%20as%20the%20Primary%20key.">Alternate Key </a>
- <a href="https://en.wikipedia.org/wiki/Foreign_key">Foreign key </a>
- <a href="https://en.wikipedia.org/wiki/Composite_key">Composite key </a>
- <a href="https://www.javatpoint.com/unique-key-in-sql#:~:text=A%20unique%20key%20is%20a,it%20cannot%20have%20duplicate%20values.">Unique key  javatpoint</a>
- <a href="https://www.sqlshack.com/commonly-used-sql-server-constraints-not-null-unique-primary-key/">Unique key  sql shack</a>

#### Visual material
- <a href="https://www.youtube.com/watch?v=p3yJZH8_bsc">Concept of Keys in DBMS - Super, Primary, Candidate, Foreign Key, etc</a>
- <a href="https://www.youtube.com/watch?v=z2hGlc-aDY0">What Are Database Keys ? | Primary Key, Foreign Key , Super Key, Candidate Key In DBMS Explained
</a>
