# MongoDB Setup and Common Commands Guide

## Overview

This guide covers the installation, setup, and usage of MongoDB using `mongosh` (MongoDB Shell). It includes basic commands, CRUD operations, indexing, aggregation, and administrative tasks.

## Table of Contents

1. [MongoDB Installation](#mongodb-installation)
2. [Starting MongoDB](#starting-mongodb)
3. [Using MongoDB Shell (mongosh)](#using-mongodb-shell-mongosh)
4. [Basic Commands](#basic-commands)
5. [CRUD Operations](#crud-operations)
6. [Indexing](#indexing)
7. [Aggregation](#aggregation)
8. [Administrative Commands](#administrative-commands)

## MongoDB Installation

### Step 1: Download MongoDB

- Go to the [MongoDB Download Center](https://www.mongodb.com/try/download/community).
- Select your OS and download the MongoDB Community Server.

### Step 2: Install MongoDB

- Follow the installation instructions for your OS (Windows, macOS, Linux).
- Make sure MongoDB binaries are added to your system's PATH.

## Starting MongoDB

### Step 1: Start MongoDB Service

For Windows:
```shell
net start MongoDB
```

For macOS/Linux:
```shell
brew services start mongodb/brew/mongodb-community
```

### Step 2: Start MongoDB Shell (mongosh)

To start `mongosh`, open your terminal or command prompt and type:
```shell
mongosh
```

This will connect to the default MongoDB instance (`localhost:27017`).

## Using MongoDB Shell (mongosh)

### Connect to a Specific Database

```shell
mongosh "mongodb://localhost:27017/yourDatabaseName"
```

## Basic Commands

1. **Show Databases:**
   ```shell
   show dbs
   ```

2. **Switch to a Database:**
   ```shell
   use yourDatabaseName
   ```

3. **Show Collections:**
   ```shell
   show collections
   ```

4. **Create a Collection:**
   ```javascript
   db.createCollection("collectionName")
   ```

5. **Drop a Collection:**
   ```javascript
   db.collectionName.drop()
   ```

## CRUD Operations

### Create (Insert)

- **Insert a Single Document:**
  ```javascript
  db.collectionName.insertOne({ name: "Alice", age: 25 })
  ```

- **Insert Multiple Documents:**
  ```javascript
  db.collectionName.insertMany([{ name: "Bob", age: 28 }, { name: "Charlie", age: 22 }])
  ```

### Read (Find)

- **Find All Documents:**
  ```javascript
  db.collectionName.find()
  ```

- **Find with a Query:**
  ```javascript
  db.collectionName.find({ age: { $gt: 25 } })
  ```

- **Find One Document:**
  ```javascript
  db.collectionName.findOne({ name: "Alice" })
  ```

### Update

- **Update a Single Document:**
  ```javascript
  db.collectionName.updateOne({ name: "Alice" }, { $set: { age: 26 } })
  ```

- **Update Multiple Documents:**
  ```javascript
  db.collectionName.updateMany({ age: { $lt: 30 } }, { $set: { status: "active" } })
  ```

### Delete

- **Delete a Single Document:**
  ```javascript
  db.collectionName.deleteOne({ name: "Alice" })
  ```

- **Delete Multiple Documents:**
  ```javascript
  db.collectionName.deleteMany({ age: { $gt: 25 } })
  ```

## Indexing

1. **Create an Index:**
   ```javascript
   db.collectionName.createIndex({ name: 1 })
   ```

2. **Show Indexes:**
   ```javascript
   db.collectionName.getIndexes()
   ```

3. **Drop an Index:**
   ```javascript
   db.collectionName.dropIndex("indexName")
   ```

## Aggregation

1. **Aggregate Example:**
   ```javascript
   db.collectionName.aggregate([
     { $match: { age: { $gt: 25 } } },
     { $group: { _id: "$age", count: { $sum: 1 } } }
   ])
   ```

## Administrative Commands

1. **Drop a Database:**
   ```javascript
   db.dropDatabase()
   ```

2. **Check Server Status:**
   ```javascript
   db.serverStatus()
   ```

3. **View Database Stats:**
   ```javascript
   db.stats()
   ```

## Notes

- Ensure MongoDB is running before connecting with `mongosh`.
- Replace placeholders like `yourDatabaseName` and `collectionName` with your actual database and collection names.

---Here's a complete summary and guide for setting up MongoDB, using `mongosh`, and common commands. You can use this as a README file to upload to your GitHub repository:

---

# MongoDB Setup and Common Commands Guide

## Overview

This guide covers the installation, setup, and usage of MongoDB using `mongosh` (MongoDB Shell). It includes basic commands, CRUD operations, indexing, aggregation, and administrative tasks.

## Table of Contents

1. [MongoDB Installation](#mongodb-installation)
2. [Starting MongoDB](#starting-mongodb)
3. [Using MongoDB Shell (mongosh)](#using-mongodb-shell-mongosh)
4. [Basic Commands](#basic-commands)
5. [CRUD Operations](#crud-operations)
6. [Indexing](#indexing)
7. [Aggregation](#aggregation)
8. [Administrative Commands](#administrative-commands)

## MongoDB Installation

### Step 1: Download MongoDB

- Go to the [MongoDB Download Center](https://www.mongodb.com/try/download/community).
- Select your OS and download the MongoDB Community Server.

### Step 2: Install MongoDB

- Follow the installation instructions for your OS (Windows, macOS, Linux).
- Make sure MongoDB binaries are added to your system's PATH.

## Starting MongoDB

### Step 1: Start MongoDB Service

For Windows:
```shell
net start MongoDB
```

For macOS/Linux:
```shell
brew services start mongodb/brew/mongodb-community
```

### Step 2: Start MongoDB Shell (mongosh)

To start `mongosh`, open your terminal or command prompt and type:
```shell
mongosh
```

This will connect to the default MongoDB instance (`localhost:27017`).

## Using MongoDB Shell (mongosh)

### Connect to a Specific Database

```shell
mongosh "mongodb://localhost:27017/yourDatabaseName"
```

## Basic Commands

1. **Show Databases:**
   ```shell
   show dbs
   ```

2. **Switch to a Database:**
   ```shell
   use yourDatabaseName
   ```

3. **Show Collections:**
   ```shell
   show collections
   ```

4. **Create a Collection:**
   ```javascript
   db.createCollection("collectionName")
   ```

5. **Drop a Collection:**
   ```javascript
   db.collectionName.drop()
   ```

## CRUD Operations

### Create (Insert)

- **Insert a Single Document:**
  ```javascript
  db.collectionName.insertOne({ name: "Alice", age: 25 })
  ```

- **Insert Multiple Documents:**
  ```javascript
  db.collectionName.insertMany([{ name: "Bob", age: 28 }, { name: "Charlie", age: 22 }])
  ```

### Read (Find)

- **Find All Documents:**
  ```javascript
  db.collectionName.find()
  ```

- **Find with a Query:**
  ```javascript
  db.collectionName.find({ age: { $gt: 25 } })
  ```

- **Find One Document:**
  ```javascript
  db.collectionName.findOne({ name: "Alice" })
  ```

### Update

- **Update a Single Document:**
  ```javascript
  db.collectionName.updateOne({ name: "Alice" }, { $set: { age: 26 } })
  ```

- **Update Multiple Documents:**
  ```javascript
  db.collectionName.updateMany({ age: { $lt: 30 } }, { $set: { status: "active" } })
  ```

### Delete

- **Delete a Single Document:**
  ```javascript
  db.collectionName.deleteOne({ name: "Alice" })
  ```

- **Delete Multiple Documents:**
  ```javascript
  db.collectionName.deleteMany({ age: { $gt: 25 } })
  ```

## Indexing

1. **Create an Index:**
   ```javascript
   db.collectionName.createIndex({ name: 1 })
   ```

2. **Show Indexes:**
   ```javascript
   db.collectionName.getIndexes()
   ```

3. **Drop an Index:**
   ```javascript
   db.collectionName.dropIndex("indexName")
   ```

## Aggregation

1. **Aggregate Example:**
   ```javascript
   db.collectionName.aggregate([
     { $match: { age: { $gt: 25 } } },
     { $group: { _id: "$age", count: { $sum: 1 } } }
   ])
   ```

## Administrative Commands

1. **Drop a Database:**
   ```javascript
   db.dropDatabase()
   ```

2. **Check Server Status:**
   ```javascript
   db.serverStatus()
   ```

3. **View Database Stats:**
   ```javascript
   db.stats()
   ```

## Notes

- Ensure MongoDB is running before connecting with `mongosh`.
- Replace placeholders like `yourDatabaseName` and `collectionName` with your actual database and collection names.

---