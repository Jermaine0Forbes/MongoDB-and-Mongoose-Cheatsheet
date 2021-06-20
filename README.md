# MongoDB CheatSheet

welcome to hell

- [What are the different Schema Types][schema-types]
- [How to dump all databases][dump-all]


### Create Information

- [how to create a database][create-db]
- [how to create a collection and insert data][create-col-ins]
- [how create a collection][create-col]

### Show Information

- [show all databases][show-dbs]
- [show all collections][show-col]
- [show current database][show-db]


### Delete Information

- [delete current database][drop-db]

[drop-db]:#delete-current-database
[show-db]:#show-current-database
[show-col]:#show-all-collections
[show-dbs]:#show-all-databases
[create-col]:#how-to-create-a-collection
[create-col-ins]:#how-create-a-collection-and-insert-data
[create-db]:#how-to-create-a-database
[dump-all]:#How-to-dump-all-databases
[home]:#MongoDB-and-Mongoose-Cheatsheet
[schema-types]:#what-are-the-different-schema-types

### delete current database

<details>
<summary>
View Content
</summary>

```
db.dropDatabase()
```


</details>

[go back to table of contents][home]

### show current database

<details>
<summary>
View Content
</summary>

```
db
```


</details>

[go back to table of contents][home]


### show all collections

<details>
<summary>
View Content
</summary>

```
show collections
```


</details>

[go back to table of contents][home]

### show all databases

<details>
<summary>
View Content
</summary>

```
show dbs
```


</details>

[go back to table of contents][home]
  
### how to create a database

<details>
<summary>
View Content
</summary>

```
#### db.createCollection('insert collection name')
```


</details>

[go back to table of contents][home]

### how to create a collection and insert data

<details>
<summary>
View Content
</summary>


```
db.insertCollectionName.insert()
```


</details>

[go back to table of contents][home]

## How to dump all databases

<details>
<summary>
View Content
</summary>

:link: **Reference**

-[tutorialspoint](https://www.tutorialspoint.com/mongodb/mongodb_create_backup.htm)
  
  ```
 // In the command line enter this
  
  mongodump  --host 127.0.0.1 --port 27017 -o ./data-backups/mongodb/
  
  ```

</details>

[go back :house:][home]

## What are the different Schema Types

<details>
<summary>
View Content
</summary>

:link: **Reference**

-[mongoosejs](https://mongoosejs.com/docs/schematypes.html)
  
  |Type | Description|
  |-|-|
  |String | [Self Explanatory](https://mongoosejs.com/docs/schematypes.html#strings)|
  |Number | [Self Explanatory](https://mongoosejs.com/docs/schematypes.html#numbers)|
  |Date | [Self Explanatory](https://mongoosejs.com/docs/schematypes.html#dates)|
  |Buffer | [Not Sure](https://mongoosejs.com/docs/schematypes.html#buffers)|
  |Mixed | ["anything goes" SchemaType](https://mongoosejs.com/docs/schematypes.html#mixed)|
  |ObjectId | [is a special type typically used for unique identifiers](https://mongoosejs.com/docs/schematypes.html#objectids)|
  |Boolean | [Self Explanatory](https://mongoosejs.com/docs/schematypes.html#booleans)|
  |Array | [Self Explanatory](https://mongoosejs.com/docs/schematypes.html#arrays)|
  |Decimal128 | [Used for declaring paths in your schema that should be 128-bit decimal floating points](https://mongoosejs.com/docs/api.html#mongoose_Mongoose-Decimal128)|
  |Map | [ maps are how you create a nested document with arbitrary keys](https://mongoosejs.com/docs/schematypes.html#maps)|
  |Schema | [declares a path as another schema](https://mongoosejs.com/docs/schematypes.html#schemas)|


</details>

[go back :house:][home]


## Create Information


### how to create a database

<details>
<summary>
View Content
</summary>

```
use *insert database name*
```

</details>

[go back to table of contents][home]





#### db.dropDatabase()
- deletes the current database you are in

#### db.insertCollectionName.drop()
- deletes the specified collection

#### db.insertCollectionName.remove()
- deletes the documents in the collection

## Find Information

#### db.*insert collection name*.find()
- retrieves all the documents that are in the collection

#### db.*insert collection name*.find().pretty()
- retrieves all the documents that are in the collection and organizes the information better

#### db.*insert collection name*.findOne()
- retrieves the first document in the collection

#### db.*insert collection name*.find({ "*insert key*": "*insert value*" })
- retrieves the specific document that matches the key and value

#### db.*insert collection name*.find({ "*insert key*": { $gt : "*insert value*" }})
- retrieves the specific document that is greater than the value in the key

#### db.*insert collection name*.find({ "*insert key*": { $gte : "*insert value*" }})
- retrieves the specific document that is greater than or equal to the value in the key

#### db.*insert collection name*.find({ "*insert key*": { $lt : "*insert value*" }})
- retrieves the specific document that is less than the value in the key

#### db.*insert collection name*.find({ "*insert key*": { $lte : "*insert value*" }})
- retrieves the specific document that is less than or equal to the value in the key

#### db.*insert collection name*.find({ "*insert key*": { $ne : "*insert value*" }})
- retrieves the specific document that does not equal to the value in the key

#### db.*insert collection name*.find({ $or :[{"*insert key*":"*insert value*"},{"*insert key*":"*insert value*"}]})
- retrieves the specific documents that is specified with the $or operator

#### db.*insert collection name*.find({ "*insert key*" : "*insert value*", $or :[{"*insert key*":"*insert value*"},{"*insert key*":"*insert value*"}]})
- retrieves the document that has the first key and value, and it also has match one of the other values in the $or operator

#### db.*insert collection name*.find({ "*insert key*" : "*insert value*"},{"*insert key*":1})
- retrieves the documents based on the first object and displays the key value in the second object

#### db.*insert collection name*.find().limit(*insert number*)
- Limits the query results to the number you specified

#### db.*insert collection name*.find().skip(*insert number*)
- Skips the first number of documents that you specified

#### db.*insert collection name*.find({"*insert key*":"*insert value*","*insert key*":"*insert value*",..})
- finds the documents that match the multiple key pair values

#### db.*insert collection name*.find({"*insert key*":"*insert value*"}).sort({"*insert key*":1})
- Sorts the results of the documents in alphabetical order if the value is a string or chronological order if the value is a number. **inserting -1 will will reverse the order**

## Aggregate Information

#### db.*insert collection name*.aggregate({ $group:})

## Update Information

#### db.*insert collection name*.update({"*insert key that you want to match*":"*insert value*"},{$set :{"*insert key*":"*insert new value*"}})
- Finds the first document that matches the first brackets condition, and in the second bracket you can update a new value

#### db.*insert collection name*.update({"*insert key that you want to match*":"*insert value*"},{$set :{"*insert key*":"*insert new value*"}},{multi:true})
- Finds **multiple** documents that matches the first brackets condition, and in the second bracket you can update the new value

#### db.*insert collection name*.save({"*insert key*":"*insert value*"})
- If multiple key values exist in the collection of documents. Then the new values that you insert will update the existing document. However if they do not exist, then the object will be inserted as a new document

#### db.*insert collection name*.updateMany({},{$rename:{"*old key name*":"*new key name*"}})
- Looks through all the documents to find the old key name and change it to the new key name

## Count Information

#### db.runCommand({count:"*insert collection name*"})
- counts the number of documents in the collection name that you specify

#### db.runCommand({count:"*insert collection name*", query:{*insert key*:"*insert value*"}})
- counts the number of documents that are in the collection name that has the key value pair in query

#### db.runCommand({count:"*insert collection name*", query:{*insert key*:"*insert value*", *insert key*:"*insert value*"}})
- counts the number of documents that are in the collection name that has the key value pairs in query
