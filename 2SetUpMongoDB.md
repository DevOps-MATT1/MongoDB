# 🍃 1. Configure MongoDB
**URL:** https://cloud.mongodb.com/v2/69f433ec93eb604c3d812c8c#/overview
**MongoCompass:** mongosh "mongodb+srv://sandbox1.dzmbajo.mongodb.net/" --apiVersion 1 --username MattMongoDB
**password:** jhanuman
**username:** hanusm2123@gmail.com
**password:** jhanuman@123

<br> 
<br> 


### 🟥 1.1 Configure MongoDB - Atlas
![Install MongoDB](Image/2/2MongoDB1.png)
![Install MongoDB](Image/2/2MongoDB2.png)
![Install MongoDB](Image/2/2MongoDB3.png)
![Install MongoDB](Image/2/2MongoDB4.png)
![Install MongoDB](Image/2/2MongoDB5.png)
![Install MongoDB](Image/2/2MongoDB6.png)

<br>
<br>


### 🟧 1.2 MongoDB Shell Download
**URL:** https://www.mongodb.com/try/download/shell

![Install MongoDB](Image/2/2MongoDB7.png)
![Install MongoDB](Image/2/2MongoDB8.png)

```text
1. Download and install MongoDB Shell (Monho shell)
2. Copy the path of Mongosh (Monho shell)
3. Open Environment Variables
4. Click on Path > Edit 
5. Add path to environment variable
```

Finally run `mongosh --help` in terminal to check if it is installed successfully.

![Install MongoDB](Image/2/2MongoDB9.png)

<br>
<br>

### 🟨 1.3 MongoDB Database Tool Download

**Url:** https://www.mongodb.com/try/download/database-tools

![Install MongoDB](Image/2/2MongoDB10.png)
![Install MongoDB](Image/2/2MongoDB11.png)

```text
1. Download and install database tools (MongoDB Database Tools)
2. Copy the path of file (MongoDB Database Tools)
3. Open Environment Variables
4. Click on Path > Edit 
5. Add path to environment variable
```

Finally run `mongoexport --help` in terminal to check if it is installed successfully.

![Install MongoDB](Image/2/2MongoDB12.png)



<br>
<br>



### 🟪 1.4 MongoDB Compass Download

URL: https://downloads.mongodb.com/compass/mongodb-compass-1.49.5-win32-x64.exe

![Install MongoDB](Image/2/2MongoDB13.png)


<br>
<br>


### 🟪 1.5 Setup MongoDB Connection

>1. Open MongoDB Account:
https://account.mongodb.com/account/login?signedOut=true
>![Install MongoDB](Image/2/2MongoDB14.png)

>2. Click on Connect 
>![Install MongoDB](Image/2/2MongoDB15.png)

>3. the pop-up window will show, click on Connect with MongoDB Compass
>![Install MongoDB](Image/2/2MongoDB16.png)
>![Install MongoDB](Image/2/2MongoDB17.png)

>4. Copy the connection string and paste it to MongoDB Compass, then click on Connect
![Install MongoDB](Image/2/2MongoDB18.png)

>5. Input Database Name and Collection Name, then click on Create Database
>![Install MongoDB](Image/2/2MongoDB19.png)

<br>
<br>

### 🟦 1.6 Import Data to MongoDB

>1. Click on Collections > Create Database
![Install MongoDB](Image/2/2MongoDB20.png)

>2. Create New Collection and click on Import Data
![Install MongoDB](Image/2/2MongoDB21.png)
![Install MongoDB](Image/2/2MongoDB22.png)

<br>
<br>

---



<br>

## 2️⃣. Explore MongoDB Atlas  


### 🔴 2.1 Explore Data MongoDB 
![Install MongoDB](Image/2/2MongoDB23.png)
![Install MongoDB](Image/2/2MongoDB24.png)
![Install MongoDB](Image/2/2MongoDB25.png)
![Install MongoDB](Image/2/2MongoDB26.png)

<br>

### 🟠 2.2 Cluster in MongoDB 
![Install MongoDB](Image/2/2MongoDB27.png)
![Install MongoDB](Image/2/2MongoDB28.png)

<br>

### 🟢 2.3 Connect to MongoDB Shell
![Install MongoDB](Image/2/2MongoDB29.png)
![Install MongoDB](Image/2/2MongoDB30.png)
![Install MongoDB](Image/2/2MongoDB31.png)


<br>
<br>


---


<br>


## 3. 🧮 Installing the `Sample_mflix DB` - `mongorestore`:



![Install MongoDB](Image/9/MongoSchema32.png)
![Install MongoDB](Image/9/MongoSchema33.png)

```bash
mongorestore --uri="mongodb+srv://sandbox1.dzmbajo.mongodb.net/sample_mflix" dump/sample_mflix --username MattMongoDB --password jhanuman
```

<br>

#### ⚙️ Explanation of Each Part

- **`mongorestore`**  
  - Tool used to restore data from a BSON dump into a MongoDB database.

- **`--uri="mongodb+srv://sandbox1.dzmbajo.mongodb.net/sample_mflix"`**  
  - Connection string to your MongoDB Atlas cluster.  
  - `mongodb+srv://` → indicates a DNS seed list connection (Atlas style).  
  - `sandbox1.dzmbajo.mongodb.net` → your cluster host.  
  - `sample_mflix` → the target database name.

- **`dump/sample_mflix`**  
  - Path to the dump folder containing BSON files (created earlier with `mongodump`).  
  - This is the source data being restored.

- **`--username MattMongoDB --password jhanuman`**  
  - Credentials for authentication.  
  - `MattMongoDB` → the MongoDB user.  
  - `jhanuman` → the password for that user.  
  - These are passed directly in the command for login.


![Install MongoDB](Image/9/MongoSchema34.png)

<br>

---
