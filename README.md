# filamentmixer


The Route is the https://somewebsite/route
The Route will call a function inside the Controller.
The Controller posts to the database.
But you need a database for this to happen
The Migration creates the database.
The Factory determines how the database row looks.
Seed is how we create test users


So to start.
Open adonis-folder > start > routes.js
Route.post('/create', "UserController.createUser")
//A route that posts to the database by hitting /create with proper request info (such as user,password) the UserController part is first created with "adonis make:controller User"
then you open adonis-folder > app > Controllers > UserController
then you create a function within the class

async createUser ({request,response}){
        response.json({
          message: `it worked`
        })
      }

request comes from the front-end(axios) or postman
response is what we send back to the front-end or postman


Creating the database
adonis install mysql

mysql -u root -p       (to open mysql)
enter password default blank
CREATE DATABASE database-name;
\q   (to quit)


Make the schema which is like an outline or model
there are two of these created by default user and token so alternatively you can use those... just dont duplicate
adonis make:migration schemaName

then we modify it to fit our need 
adonis-folder>app>database>migrations>xxxxxxxx_user.js

then we run migrations to create the table
adonis migration:run

Next step factory
