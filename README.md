# Backend - Database - Basics - Let's MonGO

## Let's monGO

Add your answers directly into this README file.

1. Explain ObjectIDs in MongoDB; what are they?

    - ObjectIDs are given implicitely when you create a new record in MongoDB
    - they works as a unique id and every record gets a field `_id` that contains the ObjectID
    - it's a long hexidecimal id consisting of a timestamp, a random value, and an incrementing counter

2. You have a collection called "users" with a document like this: `{ _id: 1, name: "Veera" }`. What query would you use to update the name to "Princess Veera Silkenfur"?

db.users.updateOne(
    { _id: 1 }, 
    { $set: { name: "Princess Veera Silkenfur" } }
);

3. How do you make a collection?

db.<collection name>.insertOne({<key>: <value>});

or:

db.createCollection("<collection name>");

4. So the (old) mongo shell is kind of like a JavaScript REPL. What is a REPL? Which other REPL have we used?

- R - Read
- E - Evaluate
- P - Print
- L - Loop
- REPL is a simple programming environment where you give commands directly and line by line and it executes them immediately (i.e. line by line)
- the pure `node` command in the terminal opens a REPL environment
- the console tab in the Chrome Developer Tools also works as a REPL

5. So the (old) mongo shell is kind of like a JavaScript REPL. You can use things like variables, try...catch  statements and loops. Experiment with it and find at least three other JavaScript things that we have used that work in the (old) shell. If you can, try to find even more!

let d = db.foods.findOne();
let a = [d];
a.push("yay");
print(a[1]);

a.pop();
print(a.length);

- to freeform for me, I always struggle when asked to experiment without any given theme :(

6. (Research) So the old shell is pretty cool. How is the new shell better?

- syntax highlighting is improved
- command history is improved
- logging is improved


7. (Research) How can you insert multiple documents at the same time?

db.foods.insertMany(
    [
        { name: "Pineapple", rating: 90 },
        { name: "Kiwi", rating: 80 },
        { name: "Orange", rating: 75 },
        { name: "Beetroot", rating: 95 },
        { name: "Spinach", rating: 97 },
    ]
)

db.foods.find().pretty() --> gives a nicer formatting

8. (Research) You have a collection called `cats` with a documents like this: `{ name: "Veera" }, { name: "Rauli" }, { name: "BenBen" }` - How can you insert the field `cute: true` into all of them with one command?

db.cats.updateMany(
    {},  --> leave filter empty, so it will apply to all
    { $set: { cute: true }}
)

9. (Task) Start a timer for 30 minutes. Spend all that time getting to know and reading https://docs.mongodb.com/manual/introduction/ - how far did you get? What was the most cool or interesting thing you learned?

- got to the top of views, always opening other linked pages, documentation is often like falling into a wikipedia rabbit hole
- most interesting command I learned was db.getCollectionInfos()

10. Find one SQL Cheatsheet and one MongoDB Cheatsheet and add links to them here.

- SQL cheatsheets
- https://i1.wp.com/www.globalsqa.com/wp-content/uploads/2020/05/SQL-cheat-sheet-1.png?resize=1536%2C1063&ssl=1
- https://www.dataquest.io/wp-content/uploads/2021/01/dataquest-sql-cheat-sheet.pdf

- MongoDB cheatsheet
- https://www.mongodb.com/developer/quickstart/cheat-sheet/
- https://blog.codecentric.de/files/2012/12/MongoDB-CheatSheet-v1_0.pdf




🌿
