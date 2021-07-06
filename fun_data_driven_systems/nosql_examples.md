<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Popular NoSQL systems
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

1. **MongoDB**
<br>
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/09/mongo-db-logo.png" /><br>
   
MongoDB is the most widely used document-based database. It stores the documents in JSON objects.
According to the website stackshare.io, more than 3400 companies are using MongoDB in their tech stack.
   Uber, Google, eBay, Nokia, Coinbase are some of them.<br>
   
 **When to use MongoDB?** <br>
   - In case you are planning to integrate hundreds of different data sources, the document-based model of
     MongoDB will be a great fit as it will provide a single unified view of the data
   - When you are expecting a lot of reads and write operations from your application but you do not care much about some 
     of the data being lost in the server crash  
   - You can use it to store clickstream data and use it for the customer behavioral analysis<br>
    
**MongoDB reading material** <br>
   - <a href="https://www.analyticsvidhya.com/blog/2020/02/mongodb-in-python-tutorial-for-beginners-using-pymongo/?utm_source=blog&utm_medium=NoSQL_Databases">MongoDB in Python Tutorial for Beginners</a>  
   - <a href="https://www.analyticsvidhya.com/blog/2020/08/query-a-mongodb-database-using-pymongo/?utm_source=blog&utm_medium=NoSQL_Databases">Query a MongoDB Database using PyMongo!</a>  


<br>

2. **Cassandra**
<br>
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/09/279px-Cassandra_logo.svg_.png" /><br>

Cassandra is an open-source, distributed database system that was initially built by Facebook (and motivated by Google’s Big Table). It is widely available and quite scalable. 
It can handle petabytes of information and thousands of concurrent requests per second.Again, according to stackshare.io, more than 400 companies are using Cassandra in their tech stack. 
Facebook, Instagram, Netflix, Spotify, Coursera are some of them.<br>


**When to use Cassandra?**<br>
- When your use case requires more writing operations than reading ones
- In situations where you need more availability than consistency. For example, you can use it for social network websites but cannot use it for banking purposes
- You require less number of joins and aggregations in your queries to the database
- Health trackers, weather data, tracking of orders, and time series data are some good use cases where you can use Cassandra databases

**Cassandra reading material** <br>
- <a href="https://www.tutorialspoint.com/cassandra/index.htm">Getting Started with Cassandra</a>


<br>

3. **ElasticSearch** 
<br>
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/09/1280px-Elasticsearch_logo.svg_.png"/><br>
   
This is also an open-source, distributed NoSQL database system. It is highly scalable and consistent. You can also call it as an Analytics Engine.
It can easily analyze, store, and search huge volumes of data.If the full-text search is a part of your use case, ElasticSearch will be the best 
fit for your tech stack. It even allows search with fuzzy matching.More than 3000 companies are using Elasticsearch in their tech stack, including Slack, Udemy, Medium, 
and Stackoverflow.<br>


**When to use ElasticSearch?** 
- If your use case requires a full-text search, Elasticsearch will be the best fit
- If your use case involves chatbots where these bots resolve most of the queries, such as when a person types something there are high chances of spelling mistakes. 
  You can make use of the in-built fuzzy matching practices of the ElasticSearch.
- Also, ElasticSearch is useful in storing logs data and analyzing it <br>

**ElasticSearch reading material** <br>
- <a href="https://www.elastic.co/learn">ElasticSearch Tutorials and Docs </a>


<br>

4. **Amazon DynamoDB**
<br>
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/09/Amazon-DynamoDB-logo-300x150-1.png"/><br>
   
It is a key-value pair based distributed database system created by Amazon and is highly scalable. But unfortunately, it is not open-source. 
It can easily handle 10 trillion requests per day so you can see why! More than 700 companies are using DynamoDB in their tech stack including Snapchat,
Lyft, and Samsung.<br>


**When to use DynamoDB?**<br>
- In case you are looking for a database that can handle simple key-value queries but those queries are very large in number
- In case you are working with OLTP workload like online ticket booking or banking where the data needs to be highly consistent
<br>
  
**DynamoDB reading material** <br>
- <a href="https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStartedDynamoDB.html">DynamoDB getting started </a>


<br>

5. **HBase** 
<br>
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/09/Apache_HBase-Logo.wine_-300x200.png"/><br>
   

It is also an open-source highly scalable distributive database system. 
HBase was written in JAVA and runs on top of the Hadoop Distributed File System (HDFS).
More than 70 companies are using Hbase in their tech stack, such as Hike, Pinterest, and HubSp
<br>


**When to use HBase?**<br>
- You should have at least petabytes of data to be processed. If your data volume is small, then you will not get the desired results
- If your use case requires random and real-time access to the data, then HBase will be the appropriate option
- If you want to easily store real-time messages for billions of people 

<br>

**HBase reading material**
- <a href="https://medium.com/@gnakan/getting-started-with-apache-hbase-31182755331" > Getting started with HBase </a>
