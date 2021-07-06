<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Extended Schema discussions
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

#### Data schema 

We previously discussed a RDBMS schema as a  logical configuration
of all or part of a relational database. The idea of a schema extends far beyond RDBMS schemas. 
we also have different schema style in RDBMS for different applications,e.g a star schema is reserved for warehousing applications.

In this section we will attempt to discuss other types of schemas before we can delve into the wild west of schemaless systems. We will discuss 6 designs:
1.The **flat model**  is for small, simple applications 
2. The **hierarchical model** is for nested data, like **XML** or **JSON**
3. The **network model** is useful in mapping and spatial data, also for depicting workflows
4. The **relational model** best reflects Object-Oriented Programming applications (this is the schema we have discussed )
5. The **star schema** is for analyzing large datasets
6. The **snowflake schema** is for analyzing large datasets

Choosing the correct database schema can ease a lot of anguish and heartache throughout
the life of a software project. An incorrect schema design can lead to terrible bottlenecks in an application 
and can be costly to refactor.For example, if you didn't realize early on that your application would rely on several table JOINs, 
your service will eventually grind to a halt when you reach a certain 
number of users and data.  To resolve this, data will likely have to move to new tables, code will have to point to those new tables,
and then those tables will have to have the proper JOINs.This means that you will need a very strong test environment (database and source code)
to test your changes in, you will need a plan to manage data integrity, and a plan for updating your database
and source code at the same time. Most importantly, once you start migrating your database to a new schema, there is almost no turning back.


### Flat model

A flat model schema is a single, two-dimensional array where elements in each column are the same type of data,
and elements in the same row relate to each other. Think of this as a single Excel spreadsheet, 
or a single database table with no relations. These are best for simple, small applications that don't 
have too much data or complex relations. For example, if you run a small business with a handful 
of employees, and you wish to store their salary information, a single, flat data model will suffice.
This model abides by the

<img src="flat-model.webp" />
