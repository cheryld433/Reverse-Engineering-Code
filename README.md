# Reverse-Engineering-Code

### Password Authentication 
This application allows the user to create an account, save the newly created account and log in and out of the account. in this activity we are tasked with reverse engineering the files, study how the program performs certain functions, below is a 
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
### CONFIG
#### MIDDLEWARE   
* isAuthenticated.js: Restricts the routes the user is not allowed to visit until they are logged in. It will redirect the user to the login page until the user provides a username and password (`return res.redirect("/");`). Once logged in, it continues with the request (`return next();`).

* config.json: Transmits data between the server and the application. The files `development` object connects the application to the database (ex: mySQL workbench), the `production` object connects the application to the container based cloud (ex: Heroku).

* passport.js: Telling passport we want to login with an username/email, email and password. When the user signs in using an email, the application  will search the database (`findOne`) for a user connected to the given email. If no user is found a message will indicate the email or password was incorrect. biolerplate code (code that has to be included) serializes and deserialize the data.
-- file dependent on: `'../models'`.

### MODELS
* index.js: Connects to database and imports user information and associate them if needed. 
-- file dependent on: `'/../config/config.json'`.

* user.js: Creates hte user model and checks the users chosen password to see is an unhashed version is already in the database. This file requires the `Node.js` package `npm install bycryptjs`. 

### PUBLIC 
(The public files create, style and provide fuctionality for the front end.)

#### JS
* login.js: Validates the email and password provided by the user. If the password is correct it opens the member page.

* members.js: Performs a GET request to figure out if the user is logged in and update the page.

* signup.js: Validate email and password to ensure the input fields were not empty. If the email and password are properly input the sign up function begins. The signup function posts info to api/signup route. If successful the member page will open.

#### STYLESHEETS
* style.css: Provides style to each webpage.

#### 
* login.html: Layout of the login page.
* members.html: Layout of the members page.
* signup.js: Layout of the signup page.

### ROUTES
* api-routes.js:  
-- file dependent on: `'../models'` and `'../config/passport'`.
* html-routes.js: 
--file dependent on: `'../config/middleware/isAuthenticated'`, `'../public/signup.html'`, `'../public/login.html'`, `'../public/members.html'`.

* package-lock.json: 
* package.json: 

* server.js: file dependent on: `'./config/passport'`, `'./models'`, `'./routes/html-routes.js'`, `'./routes/api-routes.js'`.

### Possible changes:
One change that I would make to the appliction would be to replace the `var` with  `const` and `let` where appropriate.










