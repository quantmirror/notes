<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Database Commits
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

#### SQL COMMITS AND ROLL BACKS 

In the last section we discussed transactions, we defined it as a unit of work.
This unit of work is completed by a commit, in a ACID compliant system all transactions are atomic
meaning there is no partical completness, we use a commit to save a unit of work , if any failure occurs
we use a roll back to undo the entire transaction.


**COMMIT** and **ROLLBACK** are performed on transactions. A transaction is the smallest unit of work that is performed against a database. 
Its a sequence of instructions in a logical order. A transaction can be performed manually by a programmer or it can be triggered 
using an automated program.


**sytanx** : 

```sql  
 COMMIT:
```



