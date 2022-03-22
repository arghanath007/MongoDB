# MongoDB

Documentation Link -> https://docs.mongodb.com/

**'NoSQL' means 'Not Only SQL'**

SQL -> Structured Query Language(It is just a language for querying data.)

A lot of times you'll hear mongodb referred to as a 'NoSQL' database and that's not really the best way to
reference it. Some think 'NoSQL' means 'not sql' but it actually means 'not only sql'. **'Mongodb' can use 'sql sql commands' as well.** Mongodb referred to as a 'non-relational database' and again this isn't the best way to reference it **because we can store relational data in mongodb it's just stored differently than in a relational database so mongodb MongoDB can use SQL-like queries to query data.**

MongoDB is a **Document Database**. Data is stored in 'bson' format under the hood but it is represented as json. MongoDB stores data in json format. JSON is structured as objects containing key-value pairs. Although the documents that we work with will be in 'json format' but mongoDB actually stores the data on the server in 'bson format'. MongoDB Databases are flexible and by default there is no schema. We can store any type of data in any document. MongoDB is faster to query data in most operations over relational Databases.

**"mongod" is the "Mongo Daemon" is basically the database which is storing the data.**(Somewhat of a compiler)

**"mongo" is the command-line shell which is used to interact with the database or mongod.**(Somewhat of a program)

## BSON Format

It is an extension of json and it adds support for extended data types.

### JSON Format

    {
        "key": ["string", 123],
        "Key" : "value",
        "object": {"key": 123},
    }

This ways a single document can store all of the data for each record instead of splitting up the data like a relational database does.

> Data that is Accessed Together GETS STORED TOGETHER

## Relational Database

Relational Database which are structured data like spreadsheet. The data is stored in rows and columns. Each row is a record and each column is a record field. We have multiple tables connecting all of the related data together. It also required predefined schemas. Schemas define the structure or blueprint of how the data should be structured. Schemas in Relational Database are strict meaning that the field types(int, string) must be defined ahead of time.
