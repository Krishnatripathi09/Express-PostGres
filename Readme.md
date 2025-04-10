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
# Prisma(ORM)
Next we will Install Prisam ORM in Our Project to interact with POSTGRES DataBase that we will use in Our Project.

__ORM__ stands for Object-Relational Mapping.
An ORM is a tool that lets us interact with our database using code (like JavaScript or TypeScript objects) instead of raw SQL queries.

So to Enable this Interaction we will Use Prisma ORM in our Project. Run __npm i prisma__ to install Prisma in Our Project.

# Mongoose
We Use mongoose to interact with NoSql DataBase which is an __ODM__ to Interact with No-Sql Data-Base :
Mongoose is an ODM (Object-Document Mapper), similar to an ORM but for MongoDB.

What's the difference between ORM and ODM?
Term	       Full Form	            Works With	              Maps Between
ORM	        Object-Relational Mapping	SQL Databases	       JS/TS Objects ↔ SQL Tables
ODM	        Object-Document Mapping	    NoSQL Databases	       JS/TS Objects ↔ MongoDB Documents

Next we will initialize our app with prisma with command 
__npx prisma__

when we run the above command it means that :
"Run the Prisma CLI that I installed locally in my project (via npm install @prisma/cli or @prisma/client) — or fetch it temporarily from the registry if not found."

Next we run the command __npx primsa init__ :
So By doing this we are telling primsa that 
"Set up the initial folder structure and files needed to start using Prisma in my project."

So when we run this command it will create a prisma folder containing schema.prisma file.

What is __schema.prisma__ file ?
This is Prisma’s core file where you define:
- Your database provider (PostgreSQL, MySQL, SQLite, etc.)
- The connection URL (from .env)
- Your data models (tables)
- Prisma-specific settings

Next In our PG-Admin we create a DataBase (Right click on DataBases and the Create and give the name you want under postgres user ) named __prismaDB__ (give any name we want ). After creating the DataBase we will configure our Connection String inside __.env__ file and we give our user name and other required things in our connection string.
```sql
DATABASE_URL="postgresql://johndoe:randompassword@localhost:5432/mydb?schema=public"
```
here In connection String we have to replace the johndoe with our database user name password with our database password port is default 
and then mydb with the database is that we have created in our pgadmin.

## Connecting to Our POST-GRES DataBase using prisma.
To connect toy our Post Gres DataBase using prisma we create a folder DB and inside that we will write our code to connect with PG DataBase.
