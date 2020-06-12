# Reverse-Engineering-Code

### Password Authentication 
This application allows the user to create an account, save the newly created account and log in and out of the account.

### User Story 
As a new user to this webpage I would like to create an account and save my contact information for later use.

### Packages required 
* `npm install passport`
* `npm install passort-local`
* `npm install fs`
* `npm install path`
* `npm install sequelize`
* `npm install bcrypt`
* `npm install express`
* `npm install express-session`

### Usage 


## Files Explained
-- CONFIG
 --- MIDDLEWARE   
* isAuthenticated.js: Restricts the routes the user is not allowed to visit until they are logged in. It will redirect the user to the login page until the user provides a username and password (`return res.redirect("/");`). Once logged in, it continues with the request (`return next();`).

* config.json: Transmits data between the server and the application. The files `development` object connects the application to the database (ex: mySQL workbench), the `production` object connects the application to the container based cloud (ex: Heroku).

* passport.js: Telling passport we want to login with an username/email, email and password. When the user signs in using an email, the application  will search the database (`findOne`) for a user connected to the given email. If no user is found a message will indicate the email or password was incorrect. biolerplate code (code that has to be included) serializes and deserialize the data.
-- file dependent on: `'../models'`.

### MODELS
* index.js: 

-- file dependent on: `'/../config/config.json'`.

* user.js:

### PUBLIC
### JS
* login.js:
* members.js:
* signup.js:
### STYLESHEETS
* style.css:

* login.html:
* members.html:
* signup.js:

### ROUTES
* api-routes.js:  
-- file dependent on: `'../models'` and `'../config/passport'`.
* html-routes.js: 
--file dependent on: `'../config/middleware/isAuthenticated'`, `'../public/signup.html'`, `'../public/login.html'`, `'../public/members.html'`.

* package-lock.json: 
* package.json: 

* server.js: file dependent on: `'./config/passport'`, `'./models'`, `'./routes/html-routes.js'`, `'./routes/api-routes.js'`.








