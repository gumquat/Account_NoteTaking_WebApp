# python_website
A web app that allows account creation and saving personal notes is a convenient tool for users to store and manage their personal thoughts, ideas, and reminders securely on the web. It provides a user-friendly interface where users can create an account, log in, and save their notes for future reference. In sumamary: a simple interactive website using Python, Flask, authentication, databases, and more. 

## Capabilities
* Create an account with a unique username and a protected password.
* Create delete, and save text notes that are stored locally and are viewable for later use.

NOTE for the viewer: *this project does NOT contain a CSS file*, because it uses Bootstrap css framework.
Tags called from seemingly nowhere in html files are actually being pulled from Bootstrap.

## Author
Evan Newman-Chock
github <gumquat@gmail.com>

### PREREQUISITE INSTALLS
* pip install flask
* pip install flask-login
* pip install flask-sqlalchemy
* pip install website

# **NOTES**

## **FILE(S): sign-up.html, login.html, home.html - _What Does This Code Do?_**
```
{% extends "base.html" %} {% block title %}Login{% endblock %} {% block content%} {% extends "base.html" %}: 
```
This is a template inheritance tag. It indicates that the current template (the one containing this code) extends or inherits from another template called "base.html." In other words, the current template will include all the content from "base.html" and can override specific sections using "block" tags. {% block title %}Login{% endblock %}: This is a "block" tag. It defines a block named "title" within the current template. The content inside this block will replace the content of the same block in the "base.html" template. In this case, the block contains the text "Login," which will be used as the title of the web page. {% block content %}: This is another "block" tag, defining a block named "content" within the current template. As with the title block, the content inside this block will replace the content of the corresponding block in "base.html."

## **FILE(S): base.html - _What does this HTML code do?_**
```
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"
      crossorigin="anonymous"
    />
```
In the file **base.html**, there are two external CSS files in a web page. These CSS files are commonly used libraries that provide pre-styled components and icons to enhance the appearance and functionality of the web page.

```<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous" />:```

This line includes the Bootstrap CSS library. Bootstrap is a popular front-end framework that provides a set of pre-designed styles and components, such as buttons, forms, grids, and more. It helps developers create responsive and visually appealing web pages easily.
The href attribute points to the location of the Bootstrap CSS file on the web (https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css).
The integrity attribute provides a cryptographic hash (SHA-384) to ensure the file's integrity. This is a security feature that helps protect against malicious code injection or tampering during the file's transmission.
The crossorigin attribute is set to "anonymous," indicating that the file is loaded from a different origin (a domain different from the current web page). This attribute is used when loading resources from a Content Delivery Network (CDN) to prevent any cross-origin issues.

```<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" crossorigin="anonymous" />:```

This line includes the Font Awesome CSS library. Font Awesome is a popular icon font toolkit that provides a wide range of icons that can be easily integrated into web pages.
The href attribute points to the location of the Font Awesome CSS file on the web (https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css).
The crossorigin attribute is set to "anonymous," just like in the previous link. This indicates that the file is loaded from a different origin (CDN).
By including these CSS files in the web page, the page can utilize the styles and components provided by Bootstrap and the icons provided by Font Awesome, saving the developers time and effort in styling and creating interactive elements from scratch.

## **FILE(S): base.html - _What does this HTML code do?_**
```
    <script
      src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
      integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
      integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
      integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
      crossorigin="anonymous"
    ></script>
```
The above are a series of HTML script tags, each referencing an external JavaScript file. These scripts are loading various JavaScript libraries, namely jQuery, Popper.js, and Bootstrap, into the web page.

__Query script__
```
<script
  src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
  integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
  crossorigin="anonymous"
></script>
```
* This script includes the jQuery library from the provided URL.
* The src attribute points to the location of the jQuery file (https://code.jquery.com/jquery-3.2.1.slim.min.js).
* The integrity attribute contains a cryptographic hash (SHA-384) to ensure the file's integrity during transmission, which is a security feature to prevent tampering or unauthorized modifications.
* The crossorigin attribute is set to "anonymous," indicating that the file is loaded from a different origin (CDN) to prevent any cross-origin issues.

__Popper.js script__
```
<script
  src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
  integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
  crossorigin="anonymous"
></script>
```
* This script includes the Popper.js library from the provided URL.
* The src attribute points to the location of the Popper.js file (https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js).
* The integrity attribute contains a cryptographic hash (SHA-384) to ensure the file's integrity during transmission.
* The crossorigin attribute is set to "anonymous," indicating that the file is loaded from a different origin (CDN).

__Bootstrap script__
```
<script
  src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
  integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
  crossorigin="anonymous"
></script>
```
* This script includes the Bootstrap JavaScript library from the provided URL.
* The src attribute points to the location of the Bootstrap file (https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js).
* The integrity attribute contains a cryptographic hash (SHA-384) to ensure the file's integrity during transmission.
* The crossorigin attribute is set to "anonymous," indicating that the file is loaded from a different origin (CDN).

By including these scripts in the web page, the page can utilize the functionalities provided by jQuery, Popper.js, and Bootstrap libraries. These libraries are commonly used in web development to add interactivity, responsiveness, and styling to the page's elements and layout.


## **FILE(S): models.py - _What do these imports do?_**
```
from . import db
from flask_login import UserMixin
from sqlalchemy.sql import func
```
The above is incorporated into a Python script for a Flask web application that utilizes Flask-SQLAlchemy and Flask-Login extensions.

```from . import db```
This line imports the db object from the current package. It suggests that the application is using Flask-SQLAlchemy to interact with a database. The db object is typically an instance of SQLAlchemy that provides the necessary functionality to define and query database models.

```from flask_login import UserMixin```
This line imports the UserMixin class from the Flask-Login extension. Flask-Login is used for user authentication and session management. The UserMixin class provides default implementations for several common user-related methods, making it easier to work with user models in Flask-Login.

```from sqlalchemy.sql import func```
This line imports the func object from SQLAlchemy. SQLAlchemy is a powerful SQL toolkit and Object-Relational Mapper (ORM) for Python. The func object provides access to SQL functions and expressions used in database queries.

* The application is using Flask-SQLAlchemy to interact with a database. The db object will be used to define models, create tables, and perform database operations.

* The application is using Flask-Login for user authentication. There will be a user model defined that inherits from the UserMixin class. This class will provide the necessary methods for Flask-Login to manage user sessions, such as is_authenticated, get_id, etc.

* The application may be using SQL functions provided by SQLAlchemy (func) to perform more advanced queries or aggregations in the database.

## **FILE(S): models.py - _DEF Sign-Up() Explanation_**
```
def sign_up():
  if request.method == 'POST':
  email = request.form.get('email')
  first_name = request.form.get('firstName')
  password1 = request.form.get('password1')
  password2 = request.form.get('password2')
```
The above variables are set to 'request.form.get' values: aka. whatever the user inputs, the variable is assigned that value.
If the input values meet these requirements...
```
if user:
  flash('Email already exists.', category='error')
elif len(email) < 4:
  flash('Email must be greater than 3 characters.', category='error')
elif len(first_name) < 2:
  flash('First name must be greater than 1 character.', category='error')
elif password1 != password2:
  flash('Passwords don\'t match.', category='error')
elif len(password1) < 7:
  flash('Password must be at least 7 characters.', category='error')
```
...then a User class object is created with those values as its information. 
```
new_user = User(email=email, first_name=first_name, password=generate_password_hash(
password1, method='sha256')) #using the data entered, create a new user (and encrypt their password)
db.session.add(new_user) #add the new_user information to the database
db.session.commit() #save changes to the database
login_user(new_user, remember=True)
flash('Account created!', category='success')
return redirect(url_for('views.home')) #redirect the user to the homepage
```
That information is inserted in to the database, the changes to the database is saved, and then the user is redirected to the home page.


## **FILE(S): auth.py - _What do these imports do?_**
```
from flask import Blueprint, render_template, request, flash, jsonify
from flask_login import login_required, current_user
from .models import Note
from . import db
import json
```
These are a Python script for the Flask web application, including several imports and defined functionalities related to notes.

```from Flask inport Blueprint```
Used to create modular components in the Flask app, such as views, routes, and templates.
* render_template: Used to render HTML templates with dynamic data.
* request: Used to access data from incoming HTTP requests.
* flash: Used for displaying flash messages (temporary messages) to users.
* jsonify: Used to convert Python objects to JSON format for API responses.

```from flask_login import login_required, current_user```
*Imports two specific functions from the Flask-Login extension. Flask-Login provides user authentication and session management functionalities. The functions are
* login_required: A decorator used to protect routes that require the user to be logged in. If a user tries to access such a route without being logged in, they will be redirected to the login page.
* current_user: A function that provides access to the currently logged-in user's information, such as username, ID, etc.

```from .models import Note```
This line imports the Note model from a file called models.py. There is a database model defined for the notes, and this import is necessary to interact with the notes stored in the database.

```from . import db```
This line imports the database object from the application package. The web application is using a database, and the database instance is initialized in the db module.

```import json```
This line imports the Python JSON module, which is used for handling JSON data.

These allow the web application to implement user authentication (using Flask-Login), handling notes (using the Note model), and providing JSON API responses. 


## **FILES(S): __init__.py _What do these imports do?_**
```
from flask import Flask
from flask_sqlalchemy import SQLAlchemy
from os import path
from flask_login import LoginManager
```
The above imports are used to set up and configure a Flask web application with some essential extensions.
```from flask import Flask```
This import is used to import the Flask class from the Flask framework. The Flask class is the core of the Flask web application and is responsible for handling requests, routing, and other aspects of web application development.

```from flask_sqlalchemy import SQLAlchemy```
This import is used to import the SQLAlchemy class from the Flask-SQLAlchemy extension. SQLAlchemy is a powerful SQL toolkit and Object-Relational Mapper (ORM) for Python. Flask-SQLAlchemy is an extension that integrates SQLAlchemy with Flask, making it easier to work with databases in a Flask application.

```from os import path```
This import is used to import the path module from the Python standard library. The path module provides functions to manipulate file and directory paths. It is likely used to work with file paths when configuring the Flask application, such as defining the database file location.

```from flask_login import LoginManager```
This import is used to import the LoginManager class from the Flask-Login extension. Flask-Login provides user authentication and session management functionalities for Flask applications. The LoginManager class manages the user sessions, handles user login and logout, and provides decorators to protect routes that require the user to be authenticated.

When these imports are used in combination, they typically set up a Flask web application with the following functionalities:

* The Flask class is used to create an instance of the web application.
* The SQLAlchemy class from Flask-SQLAlchemy is used to interact with the application's database.
* The LoginManager class from Flask-Login is used to manage user authentication and sessions.

With these core components in place, the application is ready to define models, routes, and other functionalities to create a full-fledged web application with user authentication and database support.

## **FILE(S): auth.py - _What does render-template do?_**
```return render_template("sign_up.html", user=current_user)```
The above is a Python statement that returns a response generated using a Flask function called render_template.

* render_template: This is a function provided by the Flask framework. It is used to render an HTML template and return it as an HTTP response. The function takes at least one argument, which is the name of the HTML template file to be rendered. In this case, the template file is "sign_up.html."

* "sign_up.html": This is the name of the HTML template that will be rendered. Flask will look for a file named "sign_up.html" in the templates directory of the Flask application and use its contents to generate the response.

* user=current_user: This part of the code is providing a variable named user to the template. The value of current_user is being passed to the template under the variable name user. In Flask applications, the current_user typically represents the currently logged-in user (if any) and is often provided by Flask-Login or a similar authentication system.

This code renders the "sign_up.html" template, and if the current_user variable has been defined in the application (e.g., if the user is logged in), that variable will be available within the template for further use. The rendered template will then be returned as a response to the user's request, displaying the sign-up page (assuming "sign_up.html" is a sign-up form or related content).

## **FILE(S): auth.py - _What does "methods=['GET', 'POST']" do?_**
```@auth.route('/login', methods=['GET', 'POST'])```
```@auth.route('/sign-up', methods=['GET', 'POST'])```
The methods argument is a list that defines which HTTP methods are allowed for this route. In this case, the route allows both GET and POST requests. When a user accesses the /login URL with a GET request, the login() function renders a login form using a template named login.html. When the user submits the form using a POST request, the code will handle the form data, check the credentials (in this case, just a simple hard-coded check), and either redirect the user to the homepage if the login is successful or show an error message on the login page if the login fails.
_TL;DR:_
* Get requests 'get' data by asking the server for access to information or webpages.
* Post requests ask to send some kind of data back.

## **FILE(S): auth.py - _What does "Flash('TEXT HERE', category='CATAGORY-TYPE')" do?_**
In Flask, flash is a helpful feature that allows you to display messages to the user across requests. It is used to provide feedback or notifications to users after certain actions are performed, such as successfully submitting a form, encountering an error, or completing an operation. Two commonly used 'catagories' for flash messages are: 'error', which displays a message upon failure, and 'success', which displays a message upon success. NOTE: flash messages won't appear unless they are coded to in your html. In this case, lines 43 - 59 handle the shwing of our flash messages.

## **FILE(S): models.py - _Full Explanation_**
### imports
```from . import db```
This imports the db module from the current directory. This module contains the database models for the application.

```from flask_login import UserMixin```
This imports the UserMixin class from the flask_login package. This class provides some common functionality for user authentication and authorization.

```from sqlalchemy.sql import func```
This imports the func function from the sqlalchemy.sql module. This function is used to create a now() function that returns the current date and time.

The next two (2) lines define the Note and User classes. These classes represent the two main entities in the application: notes and users.

### The Note class has the following attributes:
* id: The primary key of the note.
* data: The content of the note.
* date: The date and time the note was created.
* user_id: The ID of the user who created the note.

### The User class has the following attributes:
* id: The primary key of the user.
* email: The email address of the user.
* password: The password of the user.
* first_name: The first name of the user.
* notes: A relationship to the Note class. This relationship allows a user to have many notes.

### **CODE EXPLANATIONS:** 
* The 'db.Column' creates a column for storing data in. Think of each line of code within the Note and User classes as creating a column within an excel spreadsheet. A column for id's, a column for emails, etc.
* The 'primary_key's are used to give each newly made class numbers that can be used to differentiate it from other classes in case some of the class' information is similar.
* 'db.String(10000)' sets a character limit for notes. Notes cannot be longer than 10000 characters.
* 'db.DateTime(Timezone=True)' allows the creation of timestamps for notes when they are created. 'default=Func.now()' creates the timestamp itself at the moment a new note is made.
* The 'unique=True' makes sure that Users cannot have the same email attached to different accounts. Everyone must use a unique email!
* The 'db.ForeignKey('user.id')' and the 'db.relationship('Note')' act as a link between each User and the Notes they made. When a note is made, it gets assigned a relationship to its users ID.

Models.py is an example of using SQLAlchemy to define database models. 
These models can then be used to create, read, update, and delete data from a database.
