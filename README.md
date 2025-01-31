# Georwell

This project was created as an example of "How to Create a Nodejs API" for educational porposes.

### Requirements

- [Nodejs](https://nodejs.org/)
- [VS Code](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/products/docker-engine)

### Start Server

To install all dependencies, you must run the following command:

```
$ pnpm install
```

Define the environament variables:

```env
MONGO_CONNECTION_STRING=mongodb://localhost:27017/georwell
```

To run the application:

```
$ pnpm start
```

To start server into a _docker container_:

```
$ docker build -t thrsouza/georwell .
$ docker run --name georwell -p 3000:3000 -d thrsouza/georwell
```

### Endpoints

**Authors**

- GET: _/api/authors_

```javascript
// GET http://localhost:3000/api/authors
// RESPONSE (STATUS: 200)
[
  {
    name: String,
    createAt: Date,
    id: String
  }
]
```

- GET: _/api/authors/:id_

```javascript
// GET http://localhost:3000/api/authors/:id
// RESPONSE (STATUS: 200)
{
  "name": String,
  "createAt": Date,
  "id": String
}
```

- POST: _/api/authors/_

```javascript
// POST http://localhost:3000/api/authors
// REQUEST (BODY: JSON)
{
  "name": String
}

// RESPONSE (STATUS: 201)
{
  "name": String,
  "createAt": Date,
  "id": String
}
```

- PUT: _/api/authors/:id_

```javascript
// PUT http://localhost:3000/api/authors/:id
// REQUEST (BODY: JSON)
{
  "name": String
}

// RESPONSE (STATUS: 204)
```

- DELETE: _/api/authors/:id_

```javascript
// DELETE http://localhost:3000/api/authors/:id
// RESPONSE (STATUS: 204)
```

**Books**

- GET: _/api/books_

```javascript
// GET http://localhost:3000/api/books
// RESPONSE (STATUS: 200)
[
  {
    name: String,
    year: Number,
    author: {
      name: String,
      createAt: Date,
      id: String
    },
    createAt: Date,
    id: String
  }
]
```

- GET: _/api/books/:id_

```javascript
// GET http://localhost:3000/api/books/:id
// RESPONSE (STATUS: 200)
{
 "name": String,
 "year": Number,
 "author": {
   "name": String,
   "createAt": Date,
   "id": String
 },
 "createAt": Date,
 "id": String
}
```

- POST: _/api/books/_

```javascript
// POST http://localhost:3000/api/books/:id
// REQUEST (BODY: JSON)
{
  "name": String,
  "year": Number,
  "author": String
}

 // RESPONSE (STATUS: 201)
{
  "name": String,
  "year": Number,
  "author": {
    "name": String,
    "createAt": Date,
    "id": String
  },
  "createAt": Date,
  "id": String
}
```

- PUT: _/api/books/:id_

```javascript
// PUT http://localhost:3000/api/books/:id
// REQUEST (BODY: JSON)
{
  "name": String,
  "year": Number,
  "author": String
}

// RESPONSE (STATUS: 204)
```

- DELETE: _/api/books/:id_

```javascript
// DELETE http://localhost:3000/api/books/:id
// RESPONSE (STATUS: 204)
```
