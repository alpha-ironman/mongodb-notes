# mongodb-notes

## Installation  
1) [Install Mongo DB]([url](https://www.mongodb.com/docs/manual/administration/install-community/?operating-system=windows&windows-installation-method=zip))  
2) [Install Mongosh]([url](https://www.mongodb.com/try/download/shell?msockid=13e2eccf0b8e6fe529bdfa3a0aff6e51))  
3) Then, open terminal and type _**mongosh**_, then that will be usefull to run the mongodb commands  

## Information
1) Like SQL DBs, the record size can/ cannot be same in MongoDB, Its our wish on how each record is getting stored in the table.  


## Notation
1) Collections - In MongoDB, Tables are reffered as Collections.
2) 

## Mongdb Commands  
1) show dbs -> Will list down the available DBs, you see admin, config, local dbs at start.  
2) use <dbname> -> this will push you to the mentioned db, if that db is not present, it will create a new db with that name. if that db is not present, and then still this function would work, but when you do show dbs, you won't see the DB, until unless you put some data into that db.  
3) show collections -> will shows the collections.  
4) db.dropDatabase() -> Will delete the DB, This command need to be ran inside the DB by getting into it.  
5) exit -> Once you are in the DB, you can get out using this command.  
6) db.<collection_name>.insertOne(<record_details>) -> If the collection not exist in the DB. it will create it. and record looks like: {name:"john",age:20, school:'dps'} and when a record is added to the collection, unique id for that record is automatically will get created.  
7) db.<collection_name>.find() -> This will list down all the records in the collection.  
8) db.<collection_name>insertMany([record1, record2, record3]) -> This will insert multiple records into DB at a once.  
9) db.<collection_name>.find().limit(2) -> This will return only top 2 records from the collection.
10) db.<collection_name>.find().sort({name:1}).limit(2) -> This will sort collection by name in ascending order (1) and give top 2 records.  
11) db.<collection_name>.find().sort({name:-1}).limit(2) -> This will sort collection by name in desending order (-1) and give top 2 records.
12) db.<collection_name>.find().skip(1).limit(2) -> This will skip the record (1) and fetches next (2) records.
13) db.<collection_name>.find({name:"john"}) -> This is similar to Where command in SQL (Where name ="John").
14) db.<collection_name>.find({"name":"john"},{name:1, age:1, _id:0}) -> This means, from the records where name="john" it will get only name and age column values(1). This is similar to SELECT command.  
