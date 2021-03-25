# MongoDB & Mongoose

[<- Go Back](README.md)

## What's a database?
* A **database** is an organized collection of data
* This data can be organized by any criteria
* Using a database we can read, create, update and delete data

### Database types
* Now a day we can find different types of databases that fulfill different projects needs
* We can split the big database family into two big categories: **Relational** or **No relational or NoSQL**
* The **Relational** are known as SQL databases (as they use SQL as query language)
* NoSQL databases are **No relational**
* Each database type will have pros and cons when reading, creating, updating or deleting values
* We need to choose the right database for our job and know why we're going to use it
* In this course section we'll learn MongoDB that's a NoSQL database

### Relational Databases assets
* [What is a Relational Database?](https://www.youtube.com/watch?v=iKK3P11OCyM)
* [Khan Academy - Intro to SQL: Querying and managing data](https://www.khanacademy.org/computing/computer-programming/sql)
* [SQL for Beginners. Learn basics of SQL in 1 Hour](https://www.youtube.com/watch?v=7Vtl2WggqOg)
* [W3 Schools](https://www.w3schools.com/sql/)

### NoSQL
* NoSQL (**N**ot **O**nly **SQL**) is the given name for databases that are not relationals
* In this database family we can find different types of databases like `key/value, document oriented, grapsh or big tables`
* All this databases are prepare to horizontaly scale (this means that we can add more databases servers if we need so)
* In some cases we can even use a simple computer (not much hardware) to solve a business problem
* Martin Fowler gave a great [Introduction to NoSQL talk](https://www.youtube.com/watch?v=qI_g07C_Q5I&t=340s) where he explains all this concepts
* This talk is a must to understand this subject
* Also, you can read on [his blog](https://martinfowler.com/nosql.html) about it

## MongoDB
* MongoDB is a NoSQL document oriented database
* This database a;low us to store data in JSON format
* It has a flexible schema, this means that we can change/update our documents structure whenever we need it
* This becomes helpful as we develop and we don't have the final data structure
* MongoDB also it's prepared to horizontal scale in a easy way
* As we learned JavaScript we'll use a database engine that allows us to keep on using this language to store our data

### Install MongoDB
* To use MongoDB locally we need to download & install it
* Open the [MongoDB download section](https://docs.mongodb.com/manual/administration/install-community/) and choose your OS MongoDB version
* Make sure you choose the Community Server version
* When you're sure you got the right version just hit the Download button
* Execute the downloaded installer and follow all the wizard steps
* Uncheck (do not do) the option to install MongoDB as a service
* Install the full version
* In windows MongoDB will be installed on the following path `C:\Program Files\MongoDB\Server\3.4\.`
* In this example 3.4 is the MongoDB installed version
* This will change for newer versions
* MongoDB doesn't have any other dependencies so it can be executed from the downloaded/installed folder

### Configure MongoDB
* MongoDB needs a directory to store our data
* By default MongoDB looks for `\data\db` folder to start the server
* Create the default folder before running MongoDB

```bash
C:\> md \data\db
```

* When running the server we can use `--dbpath` parameter to specify the dbs path

```bash
"C:\Program Files\MongoDB\Server\3.4\bin\mongod.exe" --dbpath d:\test\mongodb\data
```

* To be able to access MongoDB from anywhere in the terminal we need to configure our environments variables
* [Windows 10 & 8](https://dangphongvanthanh.wordpress.com/2017/06/12/add-mongos-bin-folder-to-the-path-environment-variable)
* [Windows 7](https://groups.google.com/forum/#!topic/mongodb-user/ct-GnmstUSE)

* MongoDB site has documentation on how to install it on different OS:
  * [Windows](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)
  * [Mac](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
  * [Linux](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-linux/)

### MongoDB vides
* [MongoDB Tutorial for Beginners - 1 - Installing Mongo](https://www.youtube.com/watch?v=1uFY60CESlM)
* [MongoDB In 30 Minutes](https://www.youtube.com/watch?v=pWbMrx5rVBE)

### Start MongoDB instance
* After adding MongoDB to our path we can start a server instance
* Windows:
```bash
mongod.exe
```
* Linux/Mac:
```bash
mongod
```

* Once MongoDB starts will show us server configuration information 
* It will show the configured database `/data/db`
* Engine type `wiredTiger`
* Default MongoDB port `27017`

```bash
[initandlisten] Detected data files in /data/db created by the 'wiredTiger' storage engine, so setting the active storage engine to 'wiredTiger'
I NETWORK  [thread1] waiting for connections on port 27017
```

### MongoDB shell
* To interact with MongoDB we need the server runnig (mongod) and a **MongoDB shell**
* Start MongoDB shell running the following command:
* Windows:
```bash
mongo.exe
```
* Linux/Mac:
```bash
mongo
```

* Once MongoDB shell connects we'll see a description message:

```bash
MongoDB shell version v3.4.2
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.4.2
>
```

* MongoDB shell let us know that it's connected to `mongodb://127.0.0.1:27017`
* Also shows the shell and server version (`v3.4.2`)
* To use MongoDB we need the server and shell running
* MongoDB shell it's a JavaScript REPL like Node.js one
* This means that we can write/execute JavaScript code on it

```bash
> 2 + 2
4
```

* To start learning mongo shell we can execute the `help` command that will show all the commands that we can use
```bash
> help
	db.help()                    help on db methods
	db.mycoll.help()             help on collection methods
	sh.help()                    sharding helpers
	rs.help()                    replica set helpers
	help admin                   administrative help
	help connect                 connecting to a db help
	help keys                    key shortcuts
	help misc                    misc things to know
	help mr                      mapreduce

	show dbs                     show database names
	show collections             show collections in current database
	show users                   show users in current database
	show profile                 show most recent system.profile entries with time >= 1ms
	show logs                    show the accessible logger names
	show log [name]              prints out the last segment of log in memory, 'global' is default
	use <db_name>                set current database
	db.foo.find()                list objects in collection foo
	db.foo.find( { a : 1 } )     list objects in foo where a == 1
	it                           result of the last line evaluated; use to further iterate
	DBQuery.shellBatchSize = x   set default number of items to display on shell
	exit                         quit the mongo shell
```

* One of the commands it's `show dbs`
* This command will let show us all the local databases
```bash
> show dbs
local  0.000GB
test  0.000GB
```

* To know which database we're using we can call `db`
* `db` it's just a JavaScript variable that has the selected database
* By default MongoDB will set the initial selected database to `test`
```bash
> db
test
>
```

* MongoDB has databases
* MongoDB Databases has collections
* A collection is where we can store our documents grouped by some criteria
* This means that by using the database and the collection we'll have a namespace
```bash
database.coleccion
```

* For example we can have a `comics` database with a `superheroes` collection
* To access the `superheroes` collection we need to call 

```bash
comics.superheroes
```

* To create a new datbase we use the `use dabasename` command
* In this case we run 

```bash
use comics
switched to db comics
```

* The `use` command will create a new database if it doesn't exists or swith to the selected one
* MongoDB will create our databases and collections in a `lazzy` way
* This means that it won't really, really create it until it has some data on it
* We can still use the databases and collection while we don't have data on it but it's not persisted
* When we change databases MongoDB will change the `db` reference `switched to db comics`
* If we type db we can see the selected database

```bash
> db
comics
```

### Document create
* To create a new document we use the `insertOne` command
* This method accepts a JSON object as parameter
* This JSON object represents the document that we want to store in our database collection
* Use `db` to let MongoDB in which database we would like to store this document
* This means that we need to be sure that we `use` the right database first

```bash
> use comics
switched to db comics
> db.superheroes.insertOne({ "name": "SPIDER-MAN", "image": "spiderman.jpg" })
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055c94f9ca342c9eaaf73e")
}
```
* Once we inserted a document MongoDB will show us a result message
* `"acknowledged" : true` means that it was able to store the document
* `"insertedId" : ObjectId("59c6eae6eb2fe8bf77e9c391")` MongoDB creates a new ID for each new document
* Our document has a `_id` property with this `insertedId` value
* `ObjectId` is a data type supported by MongoDB to manage documents ids
* We can insert some other documents

```bash
> db.superheroes.insertOne({ "name": "CAPTAIN MARVEL", "image": "captainmarvel.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf73f")
}
> db.superheroes.insertOne({ "name": "HULK", "image": "hulk.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf740")
}
> db.superheroes.insertOne({ "name": "THOR", "image": "thor.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf741")
}
> db.superheroes.insertOne({ "name": "IRON MAN", "image": "ironman.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf742")
}
> db.superheroes.insertOne({ "name": "DAREDEVIL", "image": "daredevil.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf743")
}
> db.superheroes.insertOne({ "name": "BLACK WIDOW", "image": "blackwidow.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf744")
}
> db.superheroes.insertOne({ "name": "CAPTAIN AMERICA", "image": "captanamerica.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f19f9ca342c9eaaf745")
}
> db.superheroes.insertOne({ "name": "WOLVERINE", "image": "wolverine.jpg" });
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5b055f1bf9ca342c9eaaf746")
}
```

* Now MongoDB stored our database and collection
* So we can use the `comics.superheroes` collection
* Use `show collections` to know the database collections

```bash
> show collections
superheroes
```

* Also, we can check that the database has been saved too using `show dbs`

```bash
> show dbs
comics
```

* Once we have a database created we can start MongoDB shell and specify the initial selected database
* The `mongo` command accepts the initial selected database as parameter
```bash
mongo comics
> db
comics
```
* Full example:
```bash
mongo comics
MongoDB shell version v3.4.2
connecting to: mongodb://127.0.0.1:27017/comics
MongoDB server version: 3.4.2
Server has startup warnings:
2018-05-23T07:07:16.271-0500 I CONTROL  [initandlisten]
2018-05-23T07:07:16.271-0500 I CONTROL  [initandlisten] ** WARNING: Access control is not enabled for the database.
2018-05-23T07:07:16.271-0500 I CONTROL  [initandlisten] **          Read and write access to data and configuration is unrestricted.
2018-05-23T07:07:16.271-0500 I CONTROL  [initandlisten]
> db
comics
```

#### Practice
[Exercise 1](./exercises/mongo/ex_1.md)

### Read a collection
* Use `find` to show the collection documents
* If we don't pass any parameter to the find method it will return all the collection documents

```bash
> db.superheroes.find()
{ "_id" : ObjectId("5b055c94f9ca342c9eaaf73e"), "name" : "SPIDER-MAN", "image" : "spiderman.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf73f"), "name" : "CAPTAIN MARVEL", "image" : "captainmarvel.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf740"), "name" : "HULK", "image" : "hulk.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf741"), "name" : "THOR", "image" : "thor.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf742"), "name" : "IRON MAN", "image" : "ironman.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf743"), "name" : "DAREDEVIL", "image" : "daredevil.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf744"), "name" : "BLACK WIDOW", "image" : "blackwidow.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf745"), "name" : "CAPTAIN AMERICA", "image" : "captanamerica.jpg" }
{ "_id" : ObjectId("5b055f1bf9ca342c9eaaf746"), "name" : "WOLVERINE", "image" : "wolverine.jpg" }
```

* In this case we have 9 inserted documents
* Each of them have an unique `_id` property to identify it
* All documents have a name property too

### Document Query
* The `find` method accepts an object with properties criteria to query documents
* It will bring all documents if we pass an empty object as we're not using any criteria

```bash
> db.superheroes.find({})
{ "_id" : ObjectId("5b055c94f9ca342c9eaaf73e"), "name" : "SPIDER-MAN", "image" : "spiderman.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf73f"), "name" : "CAPTAIN MARVEL", "image" : "captainmarvel.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf740"), "name" : "HULK", "image" : "hulk.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf741"), "name" : "THOR", "image" : "thor.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf742"), "name" : "IRON MAN", "image" : "ironman.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf743"), "name" : "DAREDEVIL", "image" : "daredevil.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf744"), "name" : "BLACK WIDOW", "image" : "blackwidow.jpg" }
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf745"), "name" : "CAPTAIN AMERICA", "image" : "captanamerica.jpg" }
{ "_id" : ObjectId("5b055f1bf9ca342c9eaaf746"), "name" : "WOLVERINE", "image" : "wolverine.jpg" }
```

* We can also add a criteria to search by
* For example we can query documents by name

```bash
> db.superheroes.find({ "name": "WOLVERINE" })
{ "_id" : ObjectId("5b055f1bf9ca342c9eaaf746"), "name" : "WOLVERINE", "image" : "wolverine.jpg" }
```

* In this case we only have one document with WOLVERINE as name
* We can use any document property to query by

```bash
> db.superheroes.find({ "image": "captanamerica.jpg" })
{ "_id" : ObjectId("5b055f19f9ca342c9eaaf745"), "name" : "CAPTAIN AMERICA", "image" : "captanamerica.jpg" }
```

#### Practice
[Exercise 2](./exercises/mongo/ex_2.md)

## Cursor
* It looks like `find` returns documents
* But in reality it returns a `cursor`
* As we have JavaScript we can assign the find returned value to a variable
* Dado que no le pasamos parámetro esta búsqueda retorna todos los documentos que tenemos en la colección
* Using limit we can `limit` the amount of documents that we query
* In this example we'll get the first three collection documents

```bash
> const cursor = db.superheroes.find().limit(3)
```

* We can know if we can iterate over the cursor using `hasNext()`
* This method will return a boolean value
* In case it's true then we can call the next value

```bash
> cursor.hasNext()
true
```

* Al ser un cursor el restulado podemos llamar al método `next` para obtener el próximo resultado

```bash
> cursor.next()
{
	"_id" : ObjectId("5b055c94f9ca342c9eaaf73e"),
	"name" : "SPIDER-MAN",
	"image" : "spiderman.jpg"
}
> cursor.next()
{
	"_id" : ObjectId("5b055f19f9ca342c9eaaf73f"),
	"name" : "CAPTAIN MARVEL",
	"image" : "captainmarvel.jpg"
}
> cursor.next()
{
	"_id" : ObjectId("5b055f19f9ca342c9eaaf740"),
	"name" : "HULK",
	"image" : "hulk.jpg"
}
```

* In case we can call `next` three times as it's the result we got from the find calls
* Once we reach the last document hasNext() will return false and we know we can't iterate
* MongoDB will show an error if we try to iterate more documents that the cursor has

```bash
> cursor.hasNext()
false
> cursor.next()
E QUERY    [thread1] Error: error hasNext: false :
DBQuery.prototype.next@src/mongo/shell/query.js:305:1
@(shell):1:1
```

#### Practice
[Exercise 3](./exercises/mongo/ex_3.md)

## Collection drop
* To delete a collection we use the collection `drop` method

```bash
> db.superheroes.drop()
true
> show collections
>
```

* Calling collection `drop` method will delete all the collection documents

## Database drop
* We can also drop a database using the database `dropDatabase` method

```bash
show dbs
local  0.000GB
test   0.000GB
comics  0.000GB

> use comics
> db.dropDatabase()
{ "dropped" : "comics", "ok" : 1 }

> show dbs
local  0.000GB
test   0.000GB
```

* Calling `db.dropDatabase()` we tell MongoDB to delete the selected `db` database
* Once we dropped the database we can recreate using `use`

```bash
> use comics
switched to db comics
```

### Insert multiple documents
* To insert a document we use the collection method `insertOne`
* To insert many documents we use the collection method `insertMany`
* `insertMany` accpets a document collection as parameter in JSON format

```bash
> db.superheroes.insertMany([
  { "name": "SPIDER-MAN", "image": "spiderman.jpg" },
  { "name": "CAPTAIN MARVEL", "image": "captainmarvel.jpg" },
  { "name": "HULK", "image": "hulk.jpg" },
  { "name": "THOR", "image": "thor.jpg" },
  { "name": "IRON MAN", "image": "ironman.jpg" },
  { "name": "DAREDEVIL", "image": "daredevil.jpg" },
  { "name": "BLACK WIDOW", "image": "blackwidow.jpg" },
  { "name": "CAPTAIN AMERICA", "image": "captanamerica.jpg" },
  { "name": "WOLVERINE", "image": "wolverine.jpg" }
])
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5b0569b32c95847cf4135e75"),
		ObjectId("5b0569b32c95847cf4135e76"),
		ObjectId("5b0569b32c95847cf4135e77"),
		ObjectId("5b0569b32c95847cf4135e78"),
		ObjectId("5b0569b32c95847cf4135e79"),
		ObjectId("5b0569b32c95847cf4135e7a"),
		ObjectId("5b0569b32c95847cf4135e7b"),
		ObjectId("5b0569b32c95847cf4135e7c"),
		ObjectId("5b0569b32c95847cf4135e7d")
	]
}
```

* Now we can call `find` again to retrieve all documents

```bash
> db.superheroes.find()
{ "_id" : ObjectId("5b0569b32c95847cf4135e75"), "name" : "SPIDER-MAN", "image" : "spiderman.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e76"), "name" : "CAPTAIN MARVEL", "image" : "captainmarvel.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e77"), "name" : "HULK", "image" : "hulk.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e78"), "name" : "THOR", "image" : "thor.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e79"), "name" : "IRON MAN", "image" : "ironman.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e7a"), "name" : "DAREDEVIL", "image" : "daredevil.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e7b"), "name" : "BLACK WIDOW", "image" : "blackwidow.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e7c"), "name" : "CAPTAIN AMERICA", "image" : "captanamerica.jpg" }
{ "_id" : ObjectId("5b0569b32c95847cf4135e7d"), "name" : "WOLVERINE", "image" : "wolverine.jpg" }
```

* In this example we see how to drop and insert many new documents
* `insertMany` works in a similar way as `insertOne` but with a collection of documents
* We get all the inserted documents ids
* Also we can count the collections document using the collection method `count`

```bash
> db.superheroes.find().count()
9
```

#### Practice
[Exercise 4](./exercises/mongo/ex_4.md)

[Exercise 5](./exercises/mongo/ex_5.md)

### Pretty results
* Sometimes our documents are too big and it's difficult to read
* That's why MongoDB has a `pretty` pmethod to show documents result better
```bash
> db.superheroes.find().pretty()

{
	"_id" : ObjectId("5b0569b32c95847cf4135e75"),
	"name" : "SPIDER-MAN",
	"image" : "spiderman.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e76"),
	"name" : "CAPTAIN MARVEL",
	"image" : "captainmarvel.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e77"),
	"name" : "HULK",
	"image" : "hulk.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e78"),
	"name" : "THOR",
	"image" : "thor.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e79"),
	"name" : "IRON MAN",
	"image" : "ironman.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e7a"),
	"name" : "DAREDEVIL",
	"image" : "daredevil.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e7b"),
	"name" : "BLACK WIDOW",
	"image" : "blackwidow.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e7c"),
	"name" : "CAPTAIN AMERICA",
	"image" : "captanamerica.jpg"
}
{
	"_id" : ObjectId("5b0569b32c95847cf4135e7d"),
	"name" : "WOLVERINE",
	"image" : "wolverine.jpg"
}
```
#### Practice
[Exercise 6](./exercises/mongo/ex_6.md)

* We can also search documents for more than one criteria

```bash
> db.superheroes.find({"name": "WOLVERINE", "image" : "wolverine.jpg"})
{ "_id" : ObjectId("5b0569b32c95847cf4135e7d"), "name" : "WOLVERINE", "image" : "wolverine.jpg" }
```

* In this case we're searching for a document with the WOLVERINE name and wolverine.jpg as image 
* If we search using other parameters we might not get documents back

```bash
> db.superheroes.find({"name": "WOLVERINE", "image" : "captanamerica.jpg"})
```

* MongoDB is not able to retrieve any documents as we don't have any document with name WOLVERINE and image captanamerica.jpg

#### Practice
[Exercise 7](./exercises/mongo/ex_7.md)

## Update a document
* To update a document we use the collection method `updateOne`
* This method accepts an object as first parameter with the `find` criteria
* The second parameter is an object with a special operator called `$set`
* `$set` uses an object with the document property that we want to update and the corresponding value 

```bash
> db.superheroes.updateOne({ "name": "WOLVERINE"}, { $set: { "name": "LOGAN"}})
{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }

{ "_id" : ObjectId("5b0569b32c95847cf4135e7d"), "name" : "LOGAN", "image" : "wolverine.jpg" }
```

* MongoDB updates the document and inform the operation status showing the amount of updated documents that match the critearia
* As MongoDB doesn't have a rigid schema we can add any property to any document without changing the rest of the documents
* For example we could add a power property to the hulk document

```bash
> db.superheroes.updateOne({ "name": "HULK"}, { $set: { "power": 100}})
{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }
```

* Now we can query the Hulk document

```bash
> db.superheroes.find({"name": "HULK"}).pretty()
{
	"_id" : ObjectId("5b0569b32c95847cf4135e77"),
	"name" : "HULK",
	"image" : "hulk.jpg",
	"power" : 100
}
```

* Now we can see that power was added to the document with Hulk name
```bash
> b.superheroes.find().limit(1).pretty()
{
	"_id" : ObjectId("5b0569b32c95847cf4135e75"),
	"name" : "SPIDER-MAN",
	"image" : "spiderman.jpg"
}
```

* We still see that the rest of the document haven't been updated with the new property
* In this examples we have been using the name property to find our documents
* What could it happen if we have more than one document with the same name?
* The only way to make sure that we're going to update the right document is using the document id
* Remember that the documents hava a `_id` property by default and this value is created by MongoDB to be unique
* To update a document using the id we do it using `ObjectId(id)`

```bash
> db.superheroes.updateOne({"_id": ObjectId("5b0569b32c95847cf4135e77")}, { $set: { "name": "THE HULK"}})
{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }
```

* We can also search by id
```bash
> db.superheroes.find({ "_id": ObjectId("5b0569b32c95847cf4135e77")}).pretty()
{
	"_id" : ObjectId("5b0569b32c95847cf4135e77"),
	"name" : "THE HULK",
	"image" : "hulk.jpg",
	"power" : 100
}
```

* Excelent now we can use `_id` in our queries

#### Practice
[Exercise 8](./exercises/mongo/ex_8.md)

## Delete a document
* To delete a document we use `deleteOne`
* This method will delete the first document that match the query criteria
* To be sure that we don't delete the wrong document we can use `_id` too

```bash
> db.superheroes.deleteOne({ "_id": ObjectId("5b0569b32c95847cf4135e77")})
{ "acknowledged" : true, "deletedCount" : 1 }

> db.superheroes.find({ "_id": ObjectId("5b0569b32c95847cf4135e77")})
>
```

* Using `deleteOne` and `ObjectId()` we can delete a document
* We could use any criteria (example: name property) to delete a document by
* In case we need to delete many documents with the same criteria we can use the collection method `deleteMany`

```bash
> db.superheroes.deleteMany({})
{ "acknowledged" : true, "deletedCount" : 8 }
```

* As we passed an empty array we delete all the collections documents

#### Practice
[Exercise 9](./exercises/mongo/ex_9.md)

## Node.js integration
* To use MongoDB from Node.js we need to use the MongoDB official driver
```bash
npm i mongodb
```
* Once we installed Mongo we need to require MongoClient from this module

```js
const MongoClient = require('mongodb').MongoClient;
```

* Also we need to set up MongoDB url to connect with

```js
const url = 'mongodb://localhost:27017';
```

* We know that by default MongoDB uses port 27017 and we have it installed in our local environment
* `MongoClient` has a `connect` method that allows us to connect to MongoDB using Node.j
* This method accepts the MongoDB server `address (url)` and a `callback function`
* The callback function gets two parameters:
	* The first parameter is an `error` object
	* The second parameter ir a `client` object

```js
MongoClient.connect(url, function(err, client) {
  console.log("Connected successfully to server");
});
```

* We're going to use the client object to get the database
* The client object has a `db` method that accepts a string with the database name
* It returns a database object

```js
const db = client.db('comics');
```
  
* The same as using MongoDB shell we need to use a collection
* The `db` object that we got from the `client` one has a `collection` method that allow us to select the collection
* This method accepts a string with the collection name
* This method returns a collection object

```js
const collection = db.collection('superheroes');
```

* Now that we have the collection we can use the `find` method to query
* The `find` method accepts an object with the criteria to search by

```js
collection.find({})
```

* The `find` method returns a `cursor` object
* We need to find a way to transform our cursor into objects to use the documents we get back
* That's why the cursor object has a `toArray` method that will transform the result into an array of objects (documents)
* The toArray object accepts a callback
* This callback gets two parameters, first an error and second the documents that it get back

```js
collection.find({}).toArray((error, documents) => {
	console.log(documents);
})
```

* As we opened a connection to the MongoDB we need to close it if we're not using it
* The `client` object has a `close` method that will close the database connection

```js
client.close();
```

* Great now we know how the mongodb driver works
* Lets put everything together

```js
const MongoClient = require('mongodb').MongoClient;
const url = 'mongodb://localhost:27017';

MongoClient.connect(url, function(err, client) {
	const db = client.db('comics');
	const collection = db.collection('superheroes');

	collection.find({}).toArray((error, documents) => {
		console.log(documents);
		client.close();
	});
});
```

* Using express we'll need to add this code to our route handler

```js
app.get('/', (req, res) => {
	MongoClient.connect(url, function(err, client) {
		const db = client.db('comics');
		const collection = db.collection('superheroes');

		collection.find({}).toArray((error, documents) => {
			client.close();
			res.render('index', { documents: documents });
		});
	});
});
```

* Close the connection before sending the response to the client
* Now we know how to query MongoDB from Node.js and also using Express route
* But what about inserting, updating or deleting documents?
* The MongoDB driver has methods for each case
* Check the [MongoDB driver collection methods doc](http://mongodb.github.io/node-mongodb-native/3.0/api/Collection.html)
* As you can see there're a lot of things that we can do once we have a collection
* To insert documents we have two methods: `insertOne & insertMany`

```js
const doc = { "name": "CAPTAIN MARVEL", "image": "captainmarvel.jpg" };

collection.insertOne(doc, (err, result) => {
	callback(result);
});
```

* Now insert many documents using an array

```js
const documents = [
	{ "name": "CAPTAIN MARVEL", "image": "captainmarvel.jpg" },
	{ "name": "HULK", "image": "hulk.jpg" },
	{ "name": "THOR", "image": "thor.jpg" }
];

collection.insertMany(documents, (err, result) => {
	callback(result);
});
```

* Update also has two methods: `updateOne & updateMany`
* This updates methods accepts a filter object as first parameter
* Also accepts a second parameter that's a callback

```js
const filter = { name: 'HULK' };
const update = { $set: { power: 100 } };

collection.updateOne(filter, update, (err, result) => {
    callback(result);
});
```

* We can do the same with updateMany

```js
const filter = { name: 'HULK' };
const update = { $set: { power: 100 } };

collection.updateMany(doc, update, (err, result) => {
    callback(result);
});
```

* If we have more than one document with the name HULK it will update the power to 100
* Finally we can delete documents using MongoDB driver two methods: `deleteOne & deleteMany`
* As we're going to delete documents now it's a good time about MongoDB ObjectID
* MongoDB driver has a 

```js
const ObjectID = require('mongodb').ObjectID;
const filter = { _id:  ObjectID('5b07560bda15952ac0b33e6c')};

collection.deleteOne(query, function(err, result) {
    callback(result);
  });    
```

## Mongoose

* Mongoose is a MongoDB object modeling tool designed to work in an asynchronous environment. Mongoose supports both promises and callbacks.
* Installing Mongoose and MongoDB
    ```bash
    npm install mongoose
    ```
### Connecting to MongoDB

* Mongoose requires a connection to a MongoDB database. You can require() and connect to a locally hosted database with mongoose.connect(), as shown below.
  ```js
  //Import the mongoose module
  var mongoose = require('mongoose');

  //Set up default mongoose connection
  var mongoDB = 'mongodb://127.0.0.1/my_database';
  mongoose.connect(mongoDB, { useNewUrlParser: true });

  //Get the default connection
  var db = mongoose.connection;

  //Bind connection to error event (to get notification of connection errors)
  db.on('error', console.error.bind(console, 'MongoDB connection error:'));
  ```

### Defining and creating models

* Models are defined using the Schema interface.
* The Schema allows you to define the fields stored in each document along with their validation requirements and default values. 

  ```js
  const mongoose = require('mongoose');

  const superHeroSchema = new mongoose.Schema({
    name: String
  });
  ```
* A SchemaType is then a configuration object for an individual property.
* Schemas are then "compiled" into models using the `mongoose.model()` method.

  ```js
  const SuperHeroModel = mongoose.model('SuperHeroModel', superHeroSchema);
  ```
* The following are all the valid SchemaTypes in Mongoose. [Mongoose plugins](http://plugins.mongoosejs.io/) can also add custom SchemaTypes:
  * [String](https://mongoosejs.com/docs/schematypes.html#strings)
  * [Number](https://mongoosejs.com/docs/schematypes.html#numbers)
  * [Date](https://mongoosejs.com/docs/schematypes.html#dates)
  * [Buffer](https://mongoosejs.com/docs/schematypes.html#buffers)
  * [Boolean](https://mongoosejs.com/docs/schematypes.html#booleans)
  * [Mixed](https://mongoosejs.com/docs/schematypes.html#mixed)
  * [ObjectId](https://mongoosejs.com/docs/schematypes.html#objectids)
  * [Array](https://mongoosejs.com/docs/schematypes.html#arrays)
  * [Decimal128](https://mongoosejs.com/docs/api.html#mongoose_Mongoose-Decimal128)
  * [Map](https://mongoosejs.com/docs/schematypes.html#maps)
* Mongoose provides built-in and custom validators, and synchronous and asynchronous validators.
* The built-in validators include:

  * All [SchemaTypes](http://mongoosejs.com/docs/schematypes.html) have the built-in [required](http://mongoosejs.com/docs/api.html#schematype_SchemaType-required) validator. This is used to specify whether the field must be supplied in order to save a document.
  * [Numbers](http://mongoosejs.com/docs/api.html#schema-number-js) have [min](http://mongoosejs.com/docs/api.html#schema_number_SchemaNumber-min) and [max](http://mongoosejs.com/docs/api.html#schema_number_SchemaNumber-max) validators.
  * [Strings](http://mongoosejs.com/docs/api.html#schema-string-js) have:
    * [enum](http://mongoosejs.com/docs/api.html#schema_string_SchemaString-enum): specifies the set of allowed values for the field.
    * [match](http://mongoosejs.com/docs/api.html#schema_string_SchemaString-match): specifies a regular expression that the string must match.
    * [maxlength](http://mongoosejs.com/docs/api.html#schema_string_SchemaString-maxlength) and [minlength](http://mongoosejs.com/docs/api.html#schema_string_SchemaString-minlength) for the string.
  ```js
  var superHeroSchema = new Schema({
    movieCount: {
      type: Number,
      min: [0, 'Too few movies'],
      max: 12,
      required: [true, 'Why no movies?']
    },
    brand: {
      type: String,
      enum: ['Marvel', 'DC']
    }
  });
  ```
* While you can create schemas and models using any file structure you like, we highly recommend defining each model schema in its own module (file), exporting the method to create the model.

  **./models/superhero.model.js**
  ```js
  const mongoose = require('mongoose');

  const superHeroSchema = new mongoose.Schema({
    name: String
  });
  module.exports = mongoose.model('SuperHeroModel', superHeroSchema);
  ```

### Using models

#### Creating Documents

* An instance of a model is called a document. Creating them and saving to the database is easy.
  ```js
  var SuperHeroModel = require('../models/superhero.model')

  var hero = new SuperHeroModel({ name: 'WOLVERINE' });
  hero.save(function (err) {
    if (err) return handleError(err);
    // saved!
  });

  // or

  SuperHeroModel.create({ name: 'WOLVERINE' }, function (err, small) {
    if (err) return handleError(err);
    // saved!
  });

  // or, for inserting large batches of documents
  SuperHeroModel.insertMany([{ name: 'WOLVERINE' }], function(err) {

  });
  ```

#### Querying Documents

* Finding documents is easy with Mongoose, which supports the rich query syntax of MongoDB. Documents can be retreived using each models find, findById, findOne, or where static methods.
  ```js
  SuperHeroModel.find({ name: 'WOLVERINE' }).where('createdDate').gt(oneYearAgo).exec(callback);
  ```

#### Updating Documents
* Each model has its own update method for modifying documents in the database without returning them to your application. See the API docs for more detail.
  ```js
  SuperHeroModel.deleteOne({ brand: 'DC' }, function (err) {
    if (err) return handleError(err);
    // deleted at most one tank document
  });
  SuperHeroModel.updateOne({ name: 'WOLVERINE' }, { name: 'LOGAN' }, function(err, res) {
    // Updated at most one doc, `res.modifiedCount` contains the number
    // of docs that MongoDB updated
  });
  ```

#### Deleting Documents
* Models have static deleteOne() and deleteMany() functions for removing all documents matching the given filter.
  ```js
  SuperHeroModel.deleteOne({ brand: 'DC' }, function (err) {
    if (err) return handleError(err);
    // deleted at most one tank document
  });
  ```

  ## Assets
* [Node.js MongoDB API (to use node and mongod)](http://mongodb.github.io/node-mongodb-native/3.0/api/)
* [Add schema support with Mongoose](http://mongoosejs.com/)
* [Creating a REST API with Node.js, MongoDB & Mongoose](https://www.youtube.com/watch?v=0oXYLzuucwE&index=1&list=PL55RiY5tL51q4D-B63KBnygU6opNPFk_q)
