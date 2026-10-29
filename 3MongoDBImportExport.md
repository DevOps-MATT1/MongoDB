# 🍃1. Import Data to MongoDB
Documentation: https://www.mongodb.com/docs/database-tools/mongodump/

---

<br>

# `JSON` vs `BSON` in MongoDB:

### A. JSON Format in MongoDB

MongoDB documents look like JSON.

Example:

```json
{
  "name": "Amit",  "age": 27,  "city": "Noida"
}
```

This is very similar to:

* JavaScript objects
* Python dictionaries

Example in Python:

```python
employee = {
    "name": "Amit",
    "age": 27,
    "city": "Noida"
}
```

### B. BSON in MongoDB

Although MongoDB appears to store JSON documents, internally MongoDB stores data in BSON.

BSON stands for:

```text
Binary JSON
```

MongoDB converts JSON-like documents into BSON internally.

Example:

```text
JSON Document  →  BSON Format  →  Stored in MongoDB
```

### C. Why BSON is Used

BSON is used because:

* It is faster to process.
* It stores data in binary form.
* It also stores:

  * Data type information
  * Length information

This helps MongoDB:

* Read data faster
* Traverse data faster
* Improve overall performance

<br> 
<br>

---

<br>



## 🔴 1.1 Difference between `JSON` and `BSON`

| Feature     | JSON                | Binary JSON          |
| ----------- | ------------------- | -------------------- |
| Format      | Text                | Binary               |
| Readability | ✅ Human-readable    | ❌ Not readable       |
| Speed       | Slower parsing      | Faster processing ⚡  |
| Storage     | Larger              | Compact              |
| Indexing    | Limited             | Efficient indexing   |
| Use case    | APIs, data exchange | Databases, analytics |


![Install MongoDB](Image/3/3Mongo1.jpg)
![Install MongoDB](Image/3/3Mongo2.jpg)
![Install MongoDB](Image/3/3Mongo3.jpg)


<br>


## 🟠 1.2 Types of Data Sources for MongoDB Import/Export 

| File Type | Direct Import | Tool           | Best For             | Process |
| --------- | ------------- | -------------- | -------------------- | -------------------- |
| JSON      | ✅ Yes         | mongoimport    | Semi-structured data | Direct Import |
| CSV       | ✅ Yes         | mongoimport    | Tabular data         | Direct Import |
| TSV       | ✅ Yes         | mongoimport    | Tabular data         | Direct Import |
| BSON      | ✅ Yes         | mongorestore   | Backup/restore       | Direct Import |
| SQL       | ❌ No          | Convert first  | RDBMS migration      | Export SQL → CSV/JSON |
| Excel     | ❌ No          | Convert to CSV | Business data        | Convert CSV → then import|


<br> 


## 🧭 1.3 Create DB and Collection in `MongoDB Compass`
![Install MongoDB](Image/3/3Mongo4.png)
![Install MongoDB](Image/3/3Mongo5.png)
![Install MongoDB](Image/3/3Mongo6.png)
![Install MongoDB](Image/3/3Mongo7.png)
![Install MongoDB](Image/3/3Mongo8.png)
![Install MongoDB](Image/3/3Mongo9.png)
![Install MongoDB](Image/3/3Mongo10.png)


<br>


## 🟡 1.4 Export Data from MongoDB

```Bash
mongoexport --uri="mongodb+srv://MattMongoDB:<password>@sandbox1.dzmbajo.mongodb.net/<DatabaseName>" --collection=<collection_name>  --out=<input_file.json>

Example:
mongoexport --uri="mongodb+srv://MattMongoDB:jhanuman@sandbox1.dzmbajo.mongodb.net/Test_DB" --collection=Sales --out=Test_DB.json
```
![Install MongoDB](Image/3/3Mongo11.png)


<br>


## 🟢 1.5 Import Data from MongoDB

```Bash

mongoimport --uri="mongodb+srv://MattMongoDB:<password>@sandbox1.dzmbajo.mongodb.net/<DatabaseName>" --collection=<collection_name> --file=<input_file.json>

Example:
mongoimport --uri="mongodb+srv://MattMongoDB:jhanuman@sandbox1.dzmbajo.mongodb.net/Test_DB" --collection=Sales --file=Test_DB.json
```
![Install MongoDB](Image/3/3Mongo12.png)


<br>


## 🔵 1.6 MongoDB Dump

```Bash
mongodump --uri="mongodb+srv://MattMongoDB:<password>@sandbox1.dzmbajo.mongodb.net/<DatabaseName>" 

Example:
mongodump --uri="mongodb+srv://MattMongoDB:jhanuman@sandbox1.dzmbajo.mongodb.net/Test_DB" 
```
![Install MongoDB](Image/3/3Mongo13.png)


<br>


## 🟣 1.7 MongoDB Dump Restore

```Bash
mongorestore --uri="mongodb+srv://MattMongoDB:<password>@sandbox1.dzmbajo.mongodb.net/<DatabaseName>" dump/<dump_directory>

Example:
mongorestore --uri="mongodb+srv://MattMongoDB:jhanuman@sandbox1.dzmbajo.mongodb.net/Test_DB" "C:\D Drive\Study Material\software\MongoDB\Image\3\dump_test_db\Test_DB\Sales.bson"
```
![Install MongoDB](Image/3/3Mongo14.png)

<br>
<br>

---
