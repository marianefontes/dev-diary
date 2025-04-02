
# 📦 Mongoose – CRUD Operations

Mongoose is a Node.js library that provides a schema-based solution to model application data with MongoDB. It includes powerful methods to create, read, update, and delete documents in a collection.

---

## 🛠️ 1. CRUD Methods (Create, Read, Update, Delete)

### 🟢 Create

#### `create(doc)`
Creates and saves a new document to the collection.

```js
User.create({ name: 'Mari', email: 'mari@email.com' });
```

#### `insertMany(docs)`
Inserts multiple documents at once.

```js
Product.insertMany([
  { name: 'Notebook', price: 3000 },
  { name: 'Mouse', price: 50 }
]);
```

---

### 🔵 Read

#### `find(filter)`
Returns all documents matching the filter.

```js
User.find({ name: 'Mari' });
```

#### `findOne(filter)`
Returns the first document that matches the filter.

```js
User.findOne({ email: 'mari@email.com' });
```

#### `findById(id)`
Finds a document by its unique ID.

```js
Post.findById('605c5cfd82d8fa0f9c47f89a');
```

#### `countDocuments(filter)`
Counts documents that match the filter.

```js
User.countDocuments({ name: 'Mari' });
```

---

### 🟠 Update

#### `updateOne(filter, update)`
Updates the first document that matches the filter.

```js
User.updateOne({ email: 'mari@email.com' }, { name: 'Mariana' });
```

#### `updateMany(filter, update)`
Updates all documents that match the filter.

```js
Product.updateMany(
  { price: { $gt: 100 } },
  { $mul: { price: 0.9 } }
);
```

#### `findByIdAndUpdate(id, update)`
Updates a document by ID and returns the old document (unless `{ new: true }` is set).

```js
Order.findByIdAndUpdate(
  '605c5cfd82d8fa0f9c47f89a',
  { status: 'Shipped' }
);
```

---

### 🔴 Delete

#### `deleteOne(filter)`
Deletes the first document that matches the filter.

```js
User.deleteOne({ email: 'mari@email.com' });
```

#### `deleteMany(filter)`
Deletes all documents that match the filter.

```js
Product.deleteMany({ stock: 0 });
```

#### `findByIdAndDelete(id)`
Deletes a document by its ID and returns it.

```js
Post.findByIdAndDelete('605c5cfd82d8fa0f9c47f89a');
```
