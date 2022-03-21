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
