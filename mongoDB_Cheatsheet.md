Video Link -> https://www.youtube.com/watch?v=oSIv-E60NiU
CheatSheet Links -> https://www.codewithharry.com/blogpost/mongodb-cheatsheet
CheatSheet Link 1 -> https://github.com/ruanbekker/cheatsheets/blob/master/mongodb/shell/README.md

# To get started in TestDatabase

1. Type "mango" in the terminal to get started to use MongoDB

2)Type 'use TestDatabase' to use this particular database
3)Type 'db' to check that you are in the right database
4)Type 'db.Test2.find()' to see all of the documents(rows) in the Test2 collection(Table).

# 1. Database Commands

## View all databases

show dbs

## Create a new or switch databases

use Test(database Name)

## View current Database

db

## Delete Database

db.dropDatabase()

# 2. Collection Commands

## Show Collections

show collections

## Create a collection named 'comments'

db.createCollection('comments')

## Drop a collection named 'comments'

db.comments.drop()

# 3. Row(Document) Commands

## Show all Rows in a Collection OR Search in a Collection(Table)

### Lists all of the documents which are matching that condition within that particular collection.

1)db.comments.find({lang:'Python'})
2)db.comments.find({lang:'Python', name: 'John'})

### Lists all of the documents in that particular collection.

3)db.comments.find()

## Show all Rows in a Collection (Prettified)

db.comments.find().pretty()

## Find the first row matching the object

1)db.comments.findOne({name: 'Harry'})
2)db.Test2.findOne({name: 'Argha',lang: 'Java'})

## Limit the number of documents(rows) in output

db.comments.find().limit(2)

## Count the number of documents(rows) in the output

db.comments.find().count()

## Insert One Row

db.comments.insert({
'name': 'Harry',
'lang': 'JavaScript',
'member_since': 5
})

## Insert many Rows

db.comments.insertMany([{
'name': 'Harry',
'lang': 'JavaScript',
'member_since': 5
},
{'name': 'Rohan',
'lang': 'Python',
'member_since': 3
},
{'name': 'Lovish',
'lang': 'Java',
'member_since': 4
}])

# 4. Update a Document(row)

> Link -> https://docs.mongodb.com/manual/reference/operator/update-field/

### For Updating and Inserting of a single field together.

1. db.comments.update({name: 'Shubham'},  
   {'name': 'Harry',
   'lang': 'JavaScript',
   'member_since': 51
   }, {upsert: true})

### For Updating of a single field

2)db.comments.update({name: 'Shubham'},
{'name': 'Harry',
'lang': 'JavaScript',
'member_since': 51
})

# 5. Update Operator Commands

## Current Date Operator

db.Test2.update({name: 'Argha'}, {$currentDate: { Date: true}})

## Unset Operator

1)db.Test2.update({name: 'Argha',lang: 'JavaScript'}, {$unset: {age: ""}}) 
2)db.Test2.update({name: 'Argha'}, {$unset: {age: ""}})

## Mongodb Increment Operator

1)db.comments.update({name: 'Rohan'},
{$inc:{
member_since: 2
}})

2)db.Test2.update({name:'Mitchell'}, {$inc: {age: 39}})

# 6. Delete Document(row)

1)db.comments.remove({name: 'Harry'})

2)db.Test2.remove({name: 'John'})

# 7. Query Operators

## Less than(lt)/Greater than(gt)/ Less than or Eq(lte)/Greater than or Eq(gte) Operators.

1)db.comments.find({member_since: {$lt: 90}})
2)db.comments.find({member_since: {$lte: 90}})
3)db.comments.find({member_since: {$gt: 90}}) 
4)db.comments.find({member_since: {$gte: 90}})

# 8. Sorting Operations

## Sort in ascending/descending order in the Collection(table).

### Ascending or Increasing order

1)db.comments.find().sort({member_since: 1 }).pretty()
4)db.Test2.find().sort({name:1}).pretty()

### Descending or Decreasing order

2)db.comments.find().sort({member_since: -1 }).pretty()
3)db.Test2.find().sort({name:-1}).pretty()

# 9. Renaming Operations

## To rename a particular document in the collection.(Example: 'Rohan' here)

1)db.comments.update({name: 'Rohan'},  
{$rename:{
member_since: 'member'
}})
2)db.Test2.update({name:'Mitchell'}, {$rename: {lang: 'Game Character'}})
3)db.Test2.update({name:'Connor'},{$rename:{name: 'theirName'}})
4)db.Test2.update({},{$rename:{'name': 'Name'}})
6)db.Test2.updateMany({theirName: 'Mitchell'},{$rename: {"theirName": 'Name' }})

## To rename all of the documents in the collection.

5)db.Test2.updateMany({},{$rename: {"Name": "theirName" }})
