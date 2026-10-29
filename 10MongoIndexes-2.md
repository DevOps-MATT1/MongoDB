# 🍃 Indexes in MongoDB - 2


##  🚀 1. `Compound Index` in Mongo DB:



- ✏️ A compound index is an index structure that includes multiple fields within a single index. It allows for efficient querying and sorting based on multiple fields in a collection.
- ✏️ Compound indexes are particularly useful when you frequently query or sort data based on a combination of fields, as they can significantly improve query performance.
- ✏️ When creating a compound index, the order of the fields matters. The index will be most effective when queries match the prefix of the indexed fields.

**For example:** if you create a compound index on fields A and B (in that order), queries that filter or sort on field A will benefit from the index, while queries that only filter or sort on field B may not.

<br>

##### 📍Scenario 1: Sorting without Index
> It performs a collection scan, which is less efficient than using an index.
>
![Install MongoDB](Image/10/MongoIndex31.png)
![Install MongoDB](Image/10/MongoIndex32.png)

<br>

##### 📍Scenario 2: Creating a `Compond Index`
 
![Install MongoDB](Image/10/MongoIndex33.png)
![Install MongoDB](Image/10/MongoIndex34.png)


<br>

##### 📍Scenario 3: Search a `Student ID`: ( use Index )
 
![Install MongoDB](Image/10/MongoIndex35.png)
![Install MongoDB](Image/10/MongoIndex36.png)


<br>

##### 📍Scenario 4: Search a `Student record + Class ID`: ( use Index )
 
![Install MongoDB](Image/10/MongoIndex37.png)
![Install MongoDB](Image/10/MongoIndex38.png)


<br>

##### 📍Scenario 5: Search a `Class ID`: ( <span style="color:red">Didnot Use Index</span>. )
 
![Install MongoDB](Image/10/MongoIndex39.png)
![Install MongoDB](Image/10/MongoIndex40.png)


<br>

##### 📍Scenario 6: Sort a `Student ID = Descending and  ID = Ascending`: ( <span style="color:red">Didnot Use Index</span>. )
 
![Install MongoDB](Image/10/MongoIndex41.png)
![Install MongoDB](Image/10/MongoIndex42.png)


<br>

##### 📍Scenario 7: Sort a `Student ID = Ascending and  ID = Ascending`: ( <span style="color:Green"> Use Index</span>. )
 
![Install MongoDB](Image/10/MongoIndex43.png)
![Install MongoDB](Image/10/MongoIndex44.png)


<br>

##### 📍Scenario 8: Sort a `Student ID = Descending and  ID = Descending`: ( <span style="color:Green"> Use Index</span>. )
 
![Install MongoDB](Image/10/MongoIndex45.png)
![Install MongoDB](Image/10/MongoIndex46.png)



<br>

---

## 🎯 2. `Partial Index` in MongoDB:

A Partial Index creates an index for only those documents that satisfy a specified condition, instead of indexing every document in the collection.


db.trips.createIndex({"tripduration":1},{"partialFilterExpression":{"tripduration":{$gt:100}}})

![Install MongoDB](Image/10/MongoIndex29.png)

<br>

>[!Important] $lt is not using Index Scan, but using Index COLLSCAN.

**Command:**`db.collection.createIndex({field: 1}, {partialFilterExpression: {field: {$lt: 100}}})`
![Install MongoDB](Image/10/MongoIndex30.png)

<br>

---

<br>


## 🔎 3. `Hint()` in MongoDB:

- $hint()$ tells MongoDB <span style="color:red;">which index to use when executing a query.</span>
- Normally, MongoDB's query optimizer automatically chooses an index. 
- With **hint()**, you can force MongoDB to use a specific index.


**1. Create an Index on tripduration**
`db.trips.createIndex({"tripduration": 1},{"name": "ix_tripdur"})`

<br>

**2. Create a Compound Index**
`db.trips.createIndex({"tripduration": 1, "start station id": 1})`

<br>

**3. Check Execution Stats**
`db.trips.find({"tripduration": {$gt: 100},"start station id": 284}).explain("executionStats")`

<br>

**4. `Hint`**
`db.trips.find({"tripduration": {$gt: 100},"start station id": 284}).hint("ix_tripdur").explain("executionStats")`

<br>

**5. Drop Index**
- `db.trips.dropIndex("ix_tripdur")`
- `db.trips.dropIndex({"tripduration": 1, "start station id": 1})`

![Install MongoDB](Image/10/MongoIndex26.png)
![Install MongoDB](Image/10/MongoIndex27.png)

<br>

---

<br>

## 🔎 4. `Hint()` in MongoDB:

