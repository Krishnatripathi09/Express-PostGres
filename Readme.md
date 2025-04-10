## Creating Server 
Initialized our App with __npm init -y__ and Installed Express to create the server then in __package.json__ mentioned type as module to use ES6 modules in our App.
```json
{
  "name": "express_postgres",
  "version": "1.0.0",
  "main": "app.js",
  "type": "module", // Type as Module
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node app.js",
    "dev": "nodemon app.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": "",
  "dependencies": {
    "dotenv": "^16.4.7",
    "express": "^5.1.0"
  }
}
```
Also installed the dotenv package to use __.env__ file in our project to specify the SECRET values in our Project.
and then created the __app.js__ file to create our server to listen on PORT 6000;
```javascript
import express from "express";
import "dotenv/config";

const app = express();

const PORT = process.env.PORT || 6000;

app.listen(PORT, () => {
  console.log(`Server is Running on ${PORT}`);
});
```
Next we will Install Prisam ORM in Our Project to interact with POSTGRES DataBase that we will use in Our Project.
