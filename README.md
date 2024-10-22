
# MongoDB Checkpoint Solution


### Create a database called "contact"
```js
use contact
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/create%20collection.png?raw=true)

### Create a collection called "contactlist"
```js
db.createCollection("contactlist")
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/create%20collection.png?raw=true)

### Insert documents into "contactlist"
```js
db.contactlist.insertMany([
  { lastName: "Ben", firstName: "Moris", email: "ben@gmail.com", age: 26 },
  { lastName: "Kefi", firstName: "Seif", email: "kefi@gmail.com", age: 15 },
  { lastName: "Emilie", firstName: "brouge", email: "emilie.b@gmail.com", age: 40 },
  { lastName: "Alex", firstName: "brown", age: 4 },
  { lastName: "Denzel", firstName: "Washington", age: 3 }
])
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/insert%20into%20collection.png?raw=true)

### Display all of the contacts list
```js
db.contactlist.find()
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/find%20all.png?raw=true)

### Display all the information about only one person using their ID
```js
db.contactlist.findOne({ _id: ObjectId("Your ObjectId Here") })
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/find%20by%20id.png?raw=true)

### Display all the contacts with an age >18
```js
db.contactlist.find({ age: { $gt: 18 } })
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/filter%20by%20age.png?raw=true)

### Display all the contacts with an age >18 and name containing "ah"
```js
db.contactlist.find({ age: { $gt: 18 }, firstName: /ah/ })
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/filter%20by%20age%20and%20match%20firstname.png?raw=true)

### Change the contact's first name from "Kefi Seif" to "Kefi Anis"
```js
db.contactlist.updateOne(
  { lastName: "Kefi", firstName: "Seif" },
  { $set: { firstName: "Anis" } }
)
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/updating%20one.png?raw=true)

### Delete the contacts that are aged under 5
```js
db.contactlist.deleteMany({ age: { $lt: 5 } })
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/delete%20by%20age.png?raw=true)

### Display all of the contacts list (after deletion)
```js
db.contactlist.find()
```
![App Screenshot](https://github.com/DjacerMESSAADIA/mongodb-checkpoint/blob/main/screenshots/find%20all%20after%20deletion.png?raw=true)
