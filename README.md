# Node.js Training: Resources

## Contents

 - [Working Mode](#working-mode)
 - [Online Shop](#online-shop)
 - [0. JavaScript, Git, NPM](#0-javascript-git-npm)
 - [1. Node.js](#1-nodejs)
 - [2. Express](#2-express)
 - [3. MongoDB](#3-mongodb)
 - [4. The `fs` module](#4-the-fs-module)
 - [5. Axios](#5-axios)

## Working Mode

The road-map consists of several steps. In each step, a set of theoretical concepts are explored, supported by reference documentation, book chapters, tutorials and videos. In parallel, a simple application will be built with the learned concepts: the *Online Shop* application.

After the learning material for a given step was sufficiently explored, either some new functionality will be added to this application or old functionality will be refactored.

The application will have little-to-no user interface. Developers are expected to perform developer tests with Postman once the REST APIs are implemented.

All the code written must be published on GitHub. Access the [this link](https://classroom.github.com/a/d3mb3yKU) to create your own repository. Commits must be pushed when each individual chapter is finished. In order to request a code review from the trainers, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `master` branch.

You can work using your local environment. You need to install:
 - [NodeJS 12](https://nodejs.org/en/) 
 - [VSCode](https://code.visualstudio.com/download), with the [ESLint plugin](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
 - [Postman](https://www.postman.com/)
 - [MongoDB](https://www.mongodb.com/)
 
 For doing static code quality checks, two separate mechanisms will be used:
 - The plugin for ESlint code analysis must be used to fix code issues.
 - [Codacy](https://www.codacy.com/) will be enabled and developers should check the detected issues periodically.
 
 ## Online Shop
The application will deal with the management and daily functioning of a small online shop. Business processes:
 - **Order creation**: an end customer places an order to buy several products (based on the availability of the products in the stock).
 - **Stock management**: the existing product stocks are updated automatically based on the orders placed by customers.
 - **Shop analytics**: the management must be able to view the evolution of the daily revenue for each individual location of the shop.

Throughout the application, we assume that prices are always in EUR and weights are always in KG. 

![Data Model](./diagrams/data-model.svg "Data Model")

### 0. JavaScript, Git, NPM

Goal: Getting familiar with the ecosystem around NodeJS. You can skip this chapter if you have already worked with JavaScript, Git and npm before.

Required Reading:

 - [Git Basics](https://git-scm.com/book/en/v1/Getting-Started-Git-Basics)
 - [NPM Intro](https://nodesource.com/blog/an-absolute-beginners-guide-to-using-npm/)
 - [JavaScript](https://htmldog.com/guides/javascript/beginner/)
 - [ESLint](https://eslint.org/docs/user-guide/getting-started)

Online Shop: 

 > Clone your repository. Initialize your node project using npm init.
 > 
 > Install the following packages using npm: 
 > - express
 > - mongoose
 > - lodash
 > - axios
 > - eslint (dev dependency)
 >
 > Configure ESLint to use the `eslint:recommended` configuration.
 >
 > Create a `index.js` file which prints a `hello world` message to the console. Mark this file as the main file in your `package.json` and create a `start` script which runs `node index.js`. Check that your message is printed by running `npm start` in the terminal.
 
Further Resources:

 - [GitHub - Hello World](https://guides.github.com/activities/hello-world/)
 - [Git - CLI Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4)
 
 ### 1. Node.js

Goal: Learn how to run a simple Node.js program and debug it.

Required Reading:

 - [Node.js: Getting started](https://nodejs.dev/run-nodejs-scripts-from-the-command-line)

Online Shop: 

 > Create a `index.js` file which prints a `hello world` message to the console. Mark this file as the main file in your `package.json` and create a `start` script which runs `node index.js`. Check that your message is printed by running `npm start` in the terminal.
 >
 > Debug your code:
 > - Add a new `start:debug` npm script to your package.json. This script should execute `node index.js --inspect-brk`. The `inspect-brk` switch instructs Node.js to listen on a debugging port for the debugger and to not start code execution before the debugger attaches.
 > - Start this new script in a terminal.
 > - Place a breakpoint in your code.
 > - Create a new VSCode debugging configuration (with the default `Node.js: Attach` settings) and start it.
 > - Start the debugger.
 
Further Resources:

 - [Asynchronous programming in Node.js](https://codeforgeek.com/asynchronous-programming-in-node-js/)
 - [Debugging in VSCode](https://code.visualstudio.com/docs/editor/debugging)
 
### 2. Express
 
Goal: Build RESTful APIs using the express framework.
 
Required Reading:

 - [Introduction to Express JS](https://medium.com/@jaeger.rob/introduction-to-nodes-express-js-db5617047150)
 - [Express: Routing](https://expressjs.com/en/guide/routing.html)
 - [REST API: Design Guidelines](https://medium.com/the-andela-way/rest-api-how-to-bce359ad7362)

Online Shop: 

 > Create new `routes` and `data/memory` subfolders. Use the `routes` folder for defining express routes and the `data` folder for defining data repositories (simple JavaScript objects that store / retrieve data). 
>
> The `memory` folder will contain in-memory repositories (which store the data in memory, in *static* variables).  In the next chapters we will replace them with other repository implementations. The data repositories should be async (i.e. they should return `Promises`). 
 > 
 > Create a simple API for exposing the products and product categories, supporting the following operations:
 > - Reading all categories,
 > - Reading all products in a given category (by id),
 > - Reading a given product by id,
 > - Creating a new product in a given category (by id),
 > - Updating a product by id
 > - Deleting a product by id
 >
 > These routes should use the in memory repositories for now. 
 >
 > Test these APIs using Postman.
 
Further Resources:

 - [MDN: Node.js / Express Intro](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)

### 3. MongoDB 

Goal: Using MongoDB to persist the application data instead of the in-memory repositories.

Required Reading:

 - [Introduction to Mongoose for MongoDB](https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/)

Online Shop: 

 > Replace the in-memory repository implementations with mongoose, thus storing the products and categories in Mongo DB.
 >
 > You can remove the old in-memory repositories.
 
Further Resources:

 - [MDN: Using a database](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/mongoose)
 - [Mongoose Docs](https://mongoosejs.com/docs/)

### 4. The `fs` module

Goal: Know how to use the most common file system operations in Node.js.

Required Reading:

 - [Node.js: File System APIs](https://nodejs.org/api/fs.html#fs_file_system)

Online Shop: 

 > Use the file system to store and then serve images for the products. These images should be stored in a git-ignored `tmp` folder inside your project. Create dedicated APIs for:
 > - Uploading a new image for a product (by id),
 > - Remove the image of a product,
 > - Retrieve the image of a product (by id) - here you should use Streams,
 > - List all images.
 >
 > Of course, when a product is deleted, it's corresponding image should also be deleted if it exists.
 
Further Resources:

 - [Node.js file system intro](https://www.tutorialsteacher.com/nodejs/nodejs-file-system)
 - [Mastering the Node.js core modules](https://blog.risingstack.com/mastering-the-nodejs-core-modules-file-system-fs-module/)
 
 ### 5. Axios
 
 Goal: Integrate a third party API using axios.
 
 Required Reading:
 
  - [Axios Tutorial](https://medium.com/@amchris98/axios-tutorial-7e1fe28b8b05)
  
Online Shop: 

 > Create a new REST API that handles the creation of orders. The following constraints apply:
 >
 > - You get a single JSON object as input. This object will contain the order timestamp, the delivery address and a list of products (product ID and quantity) contained in the order.
 > - You return an Order entity if the operation was successful. If not, you return an exception response.
 > - The app has to select a strategy for finding from which locations should the products be taken. The strategy should be selected based on an environment variable. The following strategies should be created: 
 >   - **Most abundant** - take each product from the location which has the largest stock for that particular product.
 >   - **Closest location** -  find the location which is the closest to the order's delivery address, take all the available needed products from that location. Until we have all the products we need, repeat the before steps (by going to the second closest location, then to the third and so on). 
 > - The app then runs the strategy, obtaining a list of objects with the following structure: location, product, quantity (= how many items of the given product are taken from the given location). If the strategy is unable to find a suitable set of locations, it should throw an exception.
 > - The stocks are be updated by subtracting the shipped goods. 
 > - Afterwards the order is persisted in the database and returned.
 > 
 > You will need to also create the underlying mongoose models and corresponding repository objects for the stocks, locations, orders, etc.
 >
 > To compute the distances for the *closest location* strategy, use axios to call the [MapQuest route matrix API](https://developer.mapquest.com/documentation/directions-api/route-matrix/post/). You will first need to [register on the MapQuest site](https://developer.mapquest.com/plan_purchase/steps/business_edition/business_edition_free/register) and obtain an API Key.
 
 Further Resources:
 
  - [Axios documentation](https://github.com/axios/axios)
