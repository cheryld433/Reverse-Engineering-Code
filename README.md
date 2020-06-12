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
* isAuthenticated.js: 
* config.json: 
* passport.js: 
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








