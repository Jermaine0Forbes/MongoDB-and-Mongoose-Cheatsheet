# MongoDB CheatSheet

welcome to hell


## Create Information

#### use *insert database name*
- creates a new database

#### db.insertCollectionName.insert()
- creates a collection name and insert data into it

#### db.createCollection('insert collection name')
- creates a new collection name


## Show Information

#### show dbs
- shows all the databases

#### show collections
- shows all the collections in the database

#### db
- shows the current database you are in

## Delete Information

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
