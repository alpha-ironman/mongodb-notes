# mongodb-notes

## Installation  
1) [Install Mongo DB]([url](https://www.mongodb.com/docs/manual/administration/install-community/?operating-system=windows&windows-installation-method=zip))  
2) [Install Mongosh]([url](https://www.mongodb.com/try/download/shell?msockid=13e2eccf0b8e6fe529bdfa3a0aff6e51))  
3) Then, open terminal and type _**mongosh**_, then that will be usefull to run the mongodb commands  

## Information
1) Like SQL DBs, the record size can/ cannot be same in MongoDB, Its our wish on how each record is getting stored in the table.  


## Notation
1) Collections - In MongoDB, Tables are reffered as Collections.


## Keywords
1) $eq - Equals to  
2) $ne -  Not Equals to  
3) $gt - Greater than  
4) $gte - Greater than or Equal to  
5) $lt - Less than  
6) $lte - Less than or Equal to  
7) $in - in  
8) $nin - Not in
9) $exists -  Exists
10) $and - and
11) $or - or
12) $not - not
13) $expr - Expression
14) $set - set
15) $inc - Increment
16) $rename - Rename
17) $unset - unset
18) $push - push  

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



15) db.<collection_name>.find({name:{$eq:"value"}}) -> This will return records whos name is equal to "value".  
16) db.<collection_name>.find({name:{$ne: "value"}}) -> This will return the records whose name is not equal to "value".  
17) db.<collection_name>.find({age: {$gt: value}}) -> This will return the records whose age is greater than value.  
18) db.<collection_name>.find({age: {$gte: value}}) -> This will return the records which are greater than or equal to value.  
19) db.<collection_name>.fine({name:{$in:[value1, value]}}) -> This will return the records if those values are there in name.  
20) db.<collection_name>.find({name:{$nin:[value1, value2]}}) -> This will return the records expects the vlaues in names.  
21) db.<collection_name>.find({age:{$exists: True}}) -> Leave about the value of age, but this will check wheather in a record, does age key exists or not.  
22) db.<collection_name>.find({age:{$exists: False}}) -> Will return records, who don't have the age key.  
23) db.<collection_name>.find({age:{$gte:20, $lte:40}, name: value} -> Will return the records who have age value greater than equal to 20, and less than eqaul to: 40 and whose name is value. they will do and operation.  
24) db.<collection_name>.find({$and:[{age:26},{name:value}]}) -> will perform and.  
25) db.<collection_name>.find({$or:[{name:value}, {age:40}]}) -> will perform or.
26) db.<collection_name>.find({age:{$not: {$lte:20}}}) -> will perform not.
27) db.<collection_name>.find({$expr:{$gt:[$column1, $column2]}}) -> This will return the records, where column1 is greater than column2.


28) db.<collection_name>.findOne({age:{$lte:40}}) -> This will return only one record whose age is less than or equal to 40.
29) db.<collection_name>.countDocuments({age:{$lte:40}}) -> This will return the count of records.
30) db.<collection_name>.updateOne({age:26}, {$set: {age:27}}) -> This will update th top record whose age is 26 to 27.
31) db.<collection_name>.updateOne({_id:***********},{$set:{name:value, age:30}}) -> This will update the name and age of the mentioned id.
32) db.<collection_name>.updateOne({_id:***********},{$inc: {age:3}}) -> This will increase the value of age by 3 of the mentioned id.
33) db.<collection_name>.updateOne({_id:***********},{$rename:{name:"firstname"}}) -> This will rename the column named name to "Firstname".
34) db.<collection_name>.updateOne({_id:***********},{$unset:{age:""}}) -> This will remove the age key from the record with id:****.
35) db.<collection_name>.updateOne({_id:***********},{$push:{hobbies:"swimming"}}) -> will create a new key with name hobbies to the list.  
36) db.<collection_name>.updateOne({_id:***********},{$pull:{hobbies:"bowling"}}) -> will remove the bowling from the hobbies list.
37) db.<collection_name>.updateMany({address:{$exists:true}},{$unset: true}) -> will find the records where address key exists and remove it.
38) db.<collection_name>.replaceOne({age:30},{name:"John"}) -> will find the first document with age: 30 and replace that whole document with {name:"john}.
39) db.<collection_name>.deletOne({name:"John"}) -> Deletes the record whose matches the query (name=John).
40) db.<collection_name>.deleteMany({age:{$exists:false}}) -> Deletes the record who don't have age key.  
