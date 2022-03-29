<p align="center" style="background-color:"><img src="https://raw.githubusercontent.com/quantmirror/notes/master/assets/logo.jpeg?token=GHSAT0AAAAAABSSDUBE4DOCZIWGTDVZ4AZ6YSDD4FQ"  width="400"></p>
<p align="center"><h2 style="color: #193967; text-align: center">
    Relational Data Model
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

## What is Relational Model?
Relational Model (RM) represents the database as a collection of relations.
A **relation** is a table of values. Every row in the table represents a collection of related data values.
These rows in the table denote a real-world entity or relationship.

The table name and column names are helpful to interpret the meaning of values in each row. 
The data is represented as a set of relations. In the relational model, data are stored as tables. 
However, the physical storage of the data is independent of the way the data are logically organized.

### Concepts of relational model
1. **Tables** :  In the Relational model the, relations are saved in the table format. It is stored along with its entities. A table has two properties rows and columns. Rows represent records and columns represent attributes.
2. **Attributes**: Each column in a Table. Attributes are the properties which define a relation. e.g., Student_Rollno, NAME,etc.
3. **Relation Schema** : A relation schema represents the name of the relation with its attributes. (This is generally called a **database table**)
4. **Degree** : The total number of attributes which in the relation is called the degree of the relation.
5. **Cardinality** : Total number of rows present in the Table.
6. **Column** : The column represents the set of values for a specific attribute.
7. **Relation instance** : Relation instance is a finite set of tuples in the RDBMS system. Relation instances never have duplicate tuples.
8. **Relation key** : Every row has one, two or multiple attributes, which is called relation key.
9. **Attribute domain** : Every attribute has some pre-defined value and scope which is known as attribute domain


#### Reading material
- <a href="https://en.wikipedia.org/wiki/Relational_model#:~:text=The%20relational%20model%20(RM)%20for,of%20tuples%2C%20grouped%20into%20relations.">Wikipedia </a>
- <a href="https://opentextbc.ca/dbdesign01/chapter/chapter-7-the-relational-data-model/">Open Text </a>
- <a href="https://www.geeksforgeeks.org/relational-model-in-dbms/">www.geeksforgeeks.org/ </a>

#### Visual material
- <a href="https://www.youtube.com/watch?v=P8n_rwPzdBc" title="relational model in dbms">relational model in dbms</a>
- <a href="https://www.youtube.com/watch?v=kyGVhx5LwXw" title="relational model in dbms">Database Lesson #2 of 8 - The Relational Model</a>

