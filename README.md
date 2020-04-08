# NodeJS Training: Resources

## Contents

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
 > - winston
 > - eslint (dev dependency)
 >
 > Configure ESLint to use the `eslint:recommended` configuration.
 >
 > Create a `index.js` file which prints a `hello world` message to the console. Mark this file as the main file in your `package.json` and create a `start` script which runs `node index.js`. Check that your message is printed by running `npm start` in the terminal.
 
Further Resources:

 - [GitHub - Hello World](https://guides.github.com/activities/hello-world/)
 - [Git - CLI Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4)
