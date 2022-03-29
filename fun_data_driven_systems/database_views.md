<p align="center" style="background-color:"><img src="https://raw.githubusercontent.com/quantmirror/notes/master/assets/logo.jpeg?token=GHSAT0AAAAAABSSDUBE4DOCZIWGTDVZ4AZ6YSDD4FQ"  width="400"></p>
<p align="center"><h2 style="color: #193967; text-align: center">
    Database views
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

### What is a Relational Database View?
A database view is a searchable object in a database that is defined by a query. 
Though a view doesn’t store data, some refer to a views as “virtual tables,” you can query a view like you can a table.
A view can combine data from two or more table, using joins, and also just contain
a subset of information.  This makes them convenient to abstract, or hide, complicated queries.

### Read-only vs. updatable views
Database views can be defined as read-only or updatable. If the database system can determine the reverse mapping from the view schema 
to the schema of the underlying base tables, then the view is updatable. INSERT, UPDATE, and DELETE operations can be performed on updatable views.
Read-only views do not support such operations because the DBMS cannot map the changes to the underlying base tables.
A view update is done by key preservation.

Some systems support the definition of INSTEAD OF triggers on views. 
This technique allows the definition of other logic for execution in place of an insert, update, or delete operation on the views. 
Thus database systems can implement data modifications based on read-only views. However, an INSTEAD OF trigger does not change the read-only 
or updatable property of the view itself.


### reading material
- <a href="https://en.wikipedia.org/wiki/View_(SQL)"> Wikipedia</a>
- <a href="https://web.csulb.edu/colleges/coe/cecs/dbdesign/dbdesign.php?page=sql/views.php"> Views and indexes</a>
- <a href="https://www.tutorialspoint.com/sql/sql-using-views.htm"> Tutorials point</a>

### Visual material
- <a href="https://www.youtube.com/watch?v=PI8UrOAZs2U"> What is a Database View?</a>
- <a href="https://www.youtube.com/watch?v=zUj1dH4IFPI"> VIEWS IN SQL WITH EXAMPLES | WHY VIEWS ARE USED?</a>
