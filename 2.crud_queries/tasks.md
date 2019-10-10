1. Create a database named `blog`.
use blog

2. Create a collection called 'articles'.
db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields
db.articles.insertMany([{title: 'HTML', description: 'hyper text mrkup language', author: {name: 'Abcd', age: 32}, tags: ['A']}, {title: 'CSS', description: 'cascading stylesheet', author: {name: 'Bcdef', age: 76}, tags: ['B']}, {title: 'js', description: 'javascript', author: {name: 'Cdefg', age: 47}, tags: ['C']}])

4. Find all the articles using `db.COLLECTION_NAME.find()`
db.articles.find()

5. Find a document using _id field.
db.articles.find({ "_id" : ObjectId("5d9e0f8295a3b3daee535e8e")})


6. Find documents using title and author's name field.
db.articles.find({title: 'HTML'})
db.articles.find({title: 'CSS'}) 
db.articles.find({title: 'js'})

7. Find document using a specific tag.
 db.articles.find({'author.name': 'Bcdef'})

8. Update title of a document using its _id field.
db.articles.update({_id: ObjectId("5d9e0f8295a3b3daee535e8e")}, {$set: {title: 'HTML'}})

9. Update a author's name using article's title.
db.articles.update({title: 'js'}, {$set: {'author.name': 'qwerty'}})

10. rename details field to description from articles collection. 
db.articles.updateMany({}, {$rename: {'details':'description'}})

11. Add additional tag in a specific document.
db.articles.update({name: "Abcd"}, {$push: {tag: "Language"}});

12. Update an article's tags using $set and without $set.
  - Write the differences here ?
  db.articles.update({name: "Bcdef"}, {tag: ["query"]});

13. Increment an auhtor's age by 5. 
db.articles.update({title: 'CSS'}, {$inc: {'author.age': 5}}) 

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.
db.COLLECTION_NAME.remove(). db.articles.remove({_id: ObjectId("5d9e0f8295a3b3daee535e8e")})

Use sample.js data for below queries.

1. Find all males who play cricket.
db.users.find({$and: [{sports: {$in: ["cricket"]}}, {gender: {$eq: "Male"}}]})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".
db.users.update({name: {$eq: "Steve Ortega"}}, {$push: {sports: "golf"}})

3. Find all users who play either 'football' or 'cricket'.
db.users.find({sports: {$all : ['football', 'cricket']}})

4. Find all users whose name includes 'ri' in their name.
db.users.find({name: {$regex: /ri/}})
