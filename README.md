# Reverse-Engineering-Code

### Password Authentication 
This application allows the user to create an account, save the newly created account and log in and out of the account. In this activity we are tasked with reverse engineering the files, study how the program performs certain functions, below is a breakdown of the files included in the folder. 
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
  (Controls the flow of request-response):
 * isAuthenticated.js: Restricts the routes the user is not allowed to visit until they are logged in. It  will redirect the user to the login page until the user provides a username and password (`return res.redirect("/");`). Once logged in, it continues with the request (`return next();`).

 *   config.json: Transmits data between the server and the application. The files `development` object connects the application to the database (ex: mySQL workbench), the `production` object connects the application to the container based cloud (ex: Heroku).

 * passport.js: Telling passport we want to login with an username/email, email and password. When the user signs in using an email, the application  will search the database (`findOne`) for a user connected to the given email. If no user is found a message will indicate the email or password was incorrect. biolerplate code (code that has to be included) serializes and deserialize the data. -- file dependent on: `'../models'`.

### MODELS
(Models:  Maintian data. Model objects retrieve and store data):
   * index.js: Connects to database and imports user information and associate them if needed. -- file dependent on: `'/../config/config.json'`.

   * user.js: Creates the user model and checks the users chosen password to see is an unhashed version is already in the database. This file requires the `Node.js` package `npm install bycryptjs`. 

### PUBLIC 
(The public files create, style and provide fuctionality for the front end.):

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
(Endpoints defined in the server to help perform operations for a particular  client request):
  * api-routes.js: Contains routes for signing in, logging our and getting user specific data to be displayed on the front end. If the users credentials are valid it will send them to the members page. -- file dependent on: `'../models'` and `'../config/passport'`.

  * html-routes.js: The file will go through all the users in the database to verify the user has an account , if so they are redirectied to the signup HTML. It the user already has an account they are sent to the login HTML, after logging in the user is redirected to the member page. --file dependent on: `'../config/middleware/isAuthenticated'`, `'../public/signup.html'`, `'../public/login.html'`, `'../public/members.html'`.

* package-lock.json: Is automatically generated to lock dependencies to a specific version.
* package.json: Used for dependencies, it defines project properties, descriptions, author and license, info, scripts, etc. 

* server.js: The server is the last file to be executed. The listen function is the last function to execute. This file sets up the port, specifies the root directory for hte static files (CSS, JavaScript, and HTML) located in the `public` file and connects to the localhost.  -- file dependent on: `'./config/passport'`, `'./models'`, `'./routes/html-routes.js'`, `'./routes/api-routes.js'`.

### Possible changes:
One change that I would make to the appliction would be to replace the `var` with  `const` and `let` where appropriate.










