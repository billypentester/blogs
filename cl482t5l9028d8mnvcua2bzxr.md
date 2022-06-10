## Complete backend in one command

#### CLI based npm tool

public npm package that will help you to create and configure a custom backend node based CRUD application in minutes

#### Background:

It all started when I went to a web competition. They said me to create a home rental app basically a management system requires registration, user panel, admin panel, database, authentication, and much more.

It was hard to create a full-stack web application in just 4 hours. I failed to complete my project in the time frame. So, I decided to create a tool that creates a complete sample backend in just one command.

### Intro:

**Nodra JS** is a CLI tool that helps you to create a complete backend server that will handle all user operations (including registration, login, update, deletion, etc), database connectivity, schema validation, template engine, etc for a sample user CRUD.

### Features:

Nodra JS provides you wide range of features to set up a custom backend for your web application

*   Database Connectivity
*   Schema Validation
*   Ready to use API for user CRUD
*   Template Engine (hbs)
*   Authentication & Authorization
*   Static Website

### Installation:

npm install -g nodra     
nodra create-server

> npm install -g nodra

this command will install ***nodra package*** globally on your pc

> nodra create-server

this command will create a server folder and set up the whole backend ***CRUD application*** for a sample user.

### Folder Structure:

server  
├── node\_modules  
├── api  
│   └── user.js  
├── db  
│   └── conn.js  
├── middlewares  
│   └── auth.js  
├── models  
│   └── schema.js  
├── public  
│   ├── css  
│   ├── js  
│   └── images  
├── routes  
│   └── route.js  
├── temp  
│   ├── partials  
│   └── views    
├── .env  
└── package.json

#### node\_modules

Directory contains all dependencies

#### api

Folder contain all user actions like registration, update, deletion, etc.

#### db

Contains the database connection file

#### middlewares

Contain all programs that will execute before going to a specific path like auth etc.

#### models

Contains all database schemas to validate the input data.

#### public

Contains all static files like CSS, js, images files.

#### routes

Contains all main, user, and admin routes.

#### temp

Contains all partials and views of template engine like hbs, ejs, pug, etc.

#### .env

Contains all environment variables

#### package.json

Contains all package information

### Site Map:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1654843019329/53GcuZZ4T.png)

### How do I set up my app?

#### Configure Environmental variable

*   Open .env file, modify secret values or remain it default.
*   DB contains MongoDB endpoint, the PORT number used for node app, SECRET is for Auth token generation, STATIC concatenates the value with app endpoint.

#### Move Static files

*   Navigate to the Public folder, and move files to CSS, js, and images folders.
*   modify your paths in HTML files and got to the endpoint: [http://localhost:3000/public/](http://localhost:3000/public/)

#### Move Dynamic files

*   Navigate to a temp folder, move handlebars (hbs) files in the views folder
*   Move components/parts of the website in a partial folder that are frequently used.
*   Modify paths of handlebar files and link CSS, js, and image files with the template engine.

#### Set Routes

*   Go to the routes folder, route files contain the main routes of the node app.
*   You can create more routes according to need like contact us, log in, register, etc.
*   In the user panel route, give the name of the user dashboard from the template engine files.

Note: Dashboard will open after successful Authentication.

#### Manage API

*   Jump to the API folder, user.js file contains all user actions like registration, update, deletion, etc.
*   Convert all res.json to res. render to render data in template engine pages.

#### Modify Schema

*   By default, there’s a user schema to validate data but you modify it and add more schemas for different collections.

### What next ?

Well, there are multiple ways to integrate node app with different frontends but currently main are two:

*   **Using Template Engine:**

Template Engines like hbs, ejs are easy to integrate with Node for sending and receiving data in both ways. No prior knowledge is required, fast development, and easy to set up and efficient for small projects. I personally recommend hbs Template engine as it is reliable.

*   **Using React JS:**

React JS is one of the best frontend frameworks and part of MERN development. It provides you with an awesome frontend using rich CSS libraries. Prior knowledge is required, a little bit difficult to set up, best for huge projects and it takes a lot of time.

### Happy development 💙

#### Useful Links:

[**nodra**  
*CLI tool for creating complete backend of nodeJS-based applications in a single command. Latest version: 0.0.5, last…*www.npmjs.com](https://www.npmjs.com/package/nodra "https://www.npmjs.com/package/nodra")[](https://www.npmjs.com/package/nodra)

[billypentester.github.io/nodra](https://billypentester.github.io/nodra/)/

[github.com/billypentester/nodra](https://github.com/billypentester/nodra)