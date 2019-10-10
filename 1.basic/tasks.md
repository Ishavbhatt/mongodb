#### write commands for following mongodb opertaions

1. create a database named `sports`
// use sports


2. list all databases present in local mongod server.
// Answer here..
show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
db.cricket.insertMany([{name: 'ishav', age: 19, email: 'ishav@gmail.com', state: 'HP', auction_price: 100}, {name: 'kshytiz', age: 20, email: 'kshytiz@gmail.com', state: 'Punjab', auction_price: 600}, {name: 'rahul', age: 18, email: 'rahul@gmail.com', state: 'Bihar', auction_price: 430}])

db.football.insertMany([{name: 'prasanth', age: 20, email: 'prasanth@gmail.com', state: 'AP', auction_price: 300}, {name: 'Rakesh', age: 25, email: 'rakesh@gmail.com', state: 'Delhi', auction_price: 50}, {name: 'Avhinash', age: 28, email: 'avi@gmail.com', state: 'Orissa', auction_price: 320}])

db.TT.insertMany([{name: 'Karan', age: 43, email: 'karan@gmail.com', state: 'HP', auction_price: 80}, {name: 'Abhishek', age: 67, email: 'avhishek@gmail.com', state: 'UP', auction_price: 78}, {name: 'Parush', age: 32, email: 'parush@gmail.com', state: 'HP', auction_price: 890}])

5. list all collections in sports database.
show collections

6. rename `TT` collection to `tennis`.
db.TT.renameCollection('tennis')

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?
db.createCollection('khokho', {capped: true, max: 3, size: 2000})

8. check whether a collection is capped or not?
db.khokho.isCapped()

9. remove all documents from `football` collection.
db.football.remove({})

10. delete cricket collection completely.
db.cricket.drop()

11. rename database sports to games
db.copyDatabase('sports', 'games')

12. delete sports database.
use sports db.dropDatabase()


