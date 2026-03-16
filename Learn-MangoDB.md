# Learn MongoDB

The MangoDB doesn't use rows and columns. Instead, it stores data as documents that look like JSON objects.

---

BSON:BSON stands for Binary JSON.

JSON is for humans to read (Text-based).BSON is for computers to read (Machine-based).

**Data types used in BSON**

- string
- number
- double
- boolean
- date
- array
- nested object are array

**more**

- it automatically creates Object Id : an unique 12-byte ID
- can store current date and time
- You can store small images or files directly in the document.

---

## Show All Databases

```
show dbs
```

## Show Current Database

```
db
```

## Create Or Switch Database

```
use {database name}
```

## Drop

```
db.dropDatabase()
```

it deletes the current database.

## Create Collection

```
db.createCollection('posts')
```

## Add Date

```
new Date()   // gives current date with time in UTC formate.

new Date("2025-11-5")  // custom date.
```

## Insert

```
<!-- insert one -->
db.{collection_name}.insertOne({object})

<!-- insert many -->
db.{collection_name}.insertMany([{object_1},{object_2},{object_3}])

```

## find

```
db.{collection_name}.find()
```

it gives the all data in the collection.

---

## Get All Rows Formatted

```
db.posts.find().pretty()
```

---

find individual field(key & pare value)

```
db.{collection_name}.find({key:value})
```

find individual field by by multiple filter of (key & pare value)

```
db.{collection_name}.find({key1:value1},{key2:value2})
```

Find One Row

```
db.posts.findOne({ category: 'News' })
```

## Projection

```
db.{collection_name}.find(filter,{key1:true, key2:true})

ex:
db.{collection_name}.find({},{name:true, age:true, _id:false})

```

## Sort Rows

```
# ascending
db.posts.find().sort({ title: 1 })

# descending
db.posts.find().sort({ title: -1 })
```

## Count Rows

```
db.posts.find().count()
db.posts.find({ category: 'news' }).count()
```

## Limit Rows

```
db.posts.find().limit(2).pretty()
```

## Chaining

```
db.posts.find().limit(2).sort({ title: 1 }).pretty()
```

## Update

```
db.{collection_name}.update({ title: 'Post One' },
{
  title: 'Post Two',
  body: 'New body',
  date: Date()
},
{
  upsert: true
})
```

## Update One

```
db.posts.updateOne({ name: 'react'},{$set:{name: "React"}})
```

## Update many

```
db.posts.updateMany({ name: 'react'},{$set:{name: "React"}})
```

- $set => sets the value
- $unset => unset the value
- $exists => to check a key is available or not.
  if it available it gives true , else false.

## Delete Row

```
db.posts.remove({ title: 'Post Four' })
```

## Sub-Documents

```
db.posts.update({ title: 'Post One' },
{
  $set: {
    comments: [
      {
        body: 'Comment One',
        user: 'Mary Williams',
        date: Date()
      },
      {
        body: 'Comment Two',
        user: 'Harry White',
        date: Date()
      }
    ]
  }
})
```
