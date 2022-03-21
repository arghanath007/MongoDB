Video Link -> https://www.youtube.com/watch?v=oSIv-E60NiU
CheatSheet Links -> https://www.codewithharry.com/blogpost/mongodb-cheatsheet
CheatSheet Link 1 -> https://github.com/ruanbekker/cheatsheets/blob/master/mongodb/shell/README.md

# Database Commands

## View all databases

show dbs

## Create a new or switch databases

use Test(database Name)

## View current Database

db

## Delete Database

db.dropDatabase()

# Collection Commands

## Show Collections

show collections

## Create a collection named 'comments'

db.createCollection('comments')

## Drop a collection named 'comments'

db.comments.drop()

# Row(Document) Commands

## Show all Rows in a Collection

db.comments.find()

## Show all Rows in a Collection (Prettified)

db.comments.find().pretty()

## Find the first row matching the object

db.comments.findOne({name: 'Harry'})

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

## Search in a MongoDb Database

db.comments.find({lang:'Python'})

## Limit the number of rows in output

db.comments.find().limit(2)

## Count the number of rows in the output

db.comments.find().count()

## Mongodb Increment Operator

db.comments.update({name: 'Rohan'},
{$inc:{
member_since: 2
}})

## Mongodb Rename Operator

db.comments.update({name: 'Rohan'},
{$rename:{
member_since: 'member'
}})

## Delete Row

db.comments.remove({name: 'Harry'})

## Less than/Greater than/ Less than or Eq/Greater than or Eq

1)db.comments.find({member_since: {$lt: 90}})
2)db.comments.find({member_since: {$lte: 90}})
3)db.comments.find({member_since: {$gt: 90}}) 
4)db.comments.find({member_since: {$gte: 90}})

## Search in a Database

1)db.comments.find({lang:'Python'})
2)db.comments.find({lang:'Python', name: 'John'})

## Sort in ascending/descending order in the Database.

### Ascending or Increasing order

1)db.comments.find().sort({member_since: 1 }).pretty()

### Descending or Decreasing order

2)db.comments.find().sort({member_since: -1 }).pretty()

## Find the first row matching the object.

1)db.comments.findOne({name: 'Harry'})

## Update a Document(row)

### For Updating of a single field

1. db.comments.update({name: 'Shubham'},  
   {'name': 'Harry',
   'lang': 'JavaScript',
   'member_since': 51
   }, {upsert: true})

### For Updating and Inserting of a single field together.

2)db.comments.update({name: 'Shubham'},
{'name': 'Harry',
'lang': 'JavaScript',
'member_since': 51
})

## Rename Operator

### To rename a particular document in the collection.(Example: 'Rohan' here)

1)db.comments.update({name: 'Rohan'},  
{$rename:{
member_since: 'member'
}})

### To rename all of the documents in the collection.

2)db.comments.update({$rename:{
member_since: 'member'
}})
