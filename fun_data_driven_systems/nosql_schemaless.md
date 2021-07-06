<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Schemaless systems
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

### What is Schemaless database? 
A schemaless database, like MongoDB/ElasticSearch, does not have any upfront
constraints, like sql databases do. Even when sitting on top of a data lake, each document is created with a partial schema 
to aid retrieval. Any formal schema is applied in the code of your applications; 
this layer of abstraction protects the raw data in the NoSQL database and allows for rapid transformation as your needs change.

Any data, formatted or not, can be stored in a non-tabular NoSQL type of database.
At the same time, using the right tools in the form of a schemaless database can unlock the value of all of your 
structured and unstructured data types.

### How does a schemaless database work?

In schemaless databases, information is stored in JSON-style documents which can have varying sets of fields with different data types for each field. So, a collection could look like this:

```json
       [{"name" : "Joe", "age" : 30, "interests" : "soccer" },

       { "name" : "Kate", "age" : 25 }]
```
As you can see, the data itself normally has a fairly consistent structure. With a schemaless database, there is some additional structure 
— the system namespace contains an explicit list of collections and indexes.
Collections may be implicitly or explicitly created — indexes must be explicitly declare. These terms are used loosely and fully dependent on the system
you are using.

### What are the benefits of using a schemaless database?

1. **Greater flexibility over data types** :By operating without a schema, schemaless databases can store, retrieve, and query any data type — 
   perfect for big data analytics and similar operations that are powered by unstructured data. Relational databases 
   apply rigid schema rules to data, limiting what can be stored.
   
2. **No pre-defined database schemas**:The lack of schema means that your NoSQL database can accept any data type
   — including those that you do not yet use. This future-proofs your database, allowing it to grow and change as your
   data-driven operations change and mature.
3. **No data truncation**:A schemaless database makes almost no changes to your data; each item is saved in its own document with a partial schema,
   leaving the raw information untouched. This means that every detail is always available and nothing is stripped to match the current schema. 
   This is particularly valuable if your analytics needs to change at some point in the future.
4. **Suitable for real-time analytics functions**:With the ability to process unstructured data, applications built on NoSQL databases are 
   better able to process real-time data, such as readings and measurements from IoT sensors. Schemaless databases are also ideal for use 
   with machine learning and artificial intelligence operations, helping to accelerate automated actions in your business.
5. **Enhanced scalability and flexibility**: With NoSQL, you can use whichever data model is best suited to the job. 
   Graph databases allow you to view relationships between data points, or you can use traditional wide table views with an exceptionally 
   large number of columns. You can query, report, and model information however you choose. And as your requirements grow, you can keep 
   adding nodes to increase capacity and power.
    When a record is saved to a relational database, anything (particularly metadata) that does not match the schema is truncated or removed. 
   Deleted at write, these details cannot be recovered at a later point in time.
6. **What does this look like?** :A lack of rigid schema allows for increased transparency and automation when making changes to the database
   or performing a data migration. Say you want to add GPA attributes to student objects held in your database. You simply add the attribute, 
   resave, and the GPA value has been added to the NoSQL document. If you look up an existing student and reference GPA, it will return null.
   If you roll back your code, the new GPA fields in the existing objects are unlikely to cause problems and do not need to be removed if your code 
   is well written.
