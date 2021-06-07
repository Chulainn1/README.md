# Introduction to Modules

## DRY vs WET

[Don't repeat yourself!](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself#DRY_vs_WET_solutions) is a principle of software development aimed at reducing repition in software patterns. 

Violations of DRY are referred to as `WET` solutions, which stansd for `"wrtie every time"`, `"we enjoy typing"` or `"waste everyone's time"`.

### DRY Up Your Code

Each file that node runs is actually considered a separate module. 

When you run a file with
```JS 
console.log(module);
```
it returns
```JS
Module {
  id: '.',
  exports: {},
  parent: null,
  filename: '/Users/superman/codes/moduleCheck.js',
  loaded: false,
  children: [],
  paths: [ ... ] 
}
```
A key aspect of modules is `exports: {}`. A JS file must "export" the part that it wants to be "importable" on another file.

For a file to import a module from our local filesystem you use `require`:

EX 
```JS
const sayHelloTo = require('./myModule');
```
This assumes that we have a file called myModule.js in the same directory as the file that is requiring the module.

You must export code before it can be required. To export the code add: 

`module.exports = sayHelloTo;`

to the bottome of file you want to export.


# Packages and npm

A powerful feature of Node.js is its package manager, npm. `npm` allows us to install and use open-source JavaScript packages. 

`Packages` are self-contained code libraries that we can install and use in our projects. 

A `"library"` is a collection of pre-written code. Libraries can be private, but many are packaged up nicely, branded and made publicly available for other developers to use in their own projects.

### package.json

Node.js prohects have a file called [package.json](https://docs.npmjs.com/cli/v7/configuring-npm/package-json) that contain basic atributes like he project's name, description, and author. 

Ex: 

```JS
{
  "name": "project-name",
  "version": "1.0.0",
  "description": "Short project summary",
  "main": "index.js",
  "scripts": {
    "myscript": "ENV=development node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "MIT",
  "dependencies": {
    "express": "^4.13.4"
  }
}
```
The `scripts` portion allows us to run commands using an alias, for instance:

```JS
npm run myscript
```
The `dependencies` section indicates the packages that need to be installed for the project to run properly.


# Automated Testing

As a program grows larger the time it takes to manually test the program increases. Instead of manually testing we can write code that helps us test our programs. 

## The Benefits of Automated Testing
1. `it saves testing time` (by not having to perform manual tests over and over)
2. `it saves debugging time` (by catching bugs earlier)
3. `it makes it easier to program` (because we don't need to keep the entire application in our heads, just the part that we're working on... if we break something, our tests will let us know)
4. `it makes it easier to come back to a program after some time` (programmers forget things, but tests do not)
5. `it makes it easier to work together` (we wrote some widget and know how it works, but our team-mates probably don't; our tests will catch bugs introduced by others on our team, and vice versa)
6. `it acts as documentation` (readings tests is a great way to learn about how code is meant to be used)
7. `it improves the quality of our code` (writing code that is easy to test often requires us to change how our code is structured -- for the better)

### Types of Testing 
[Full read](https://codeutopia.net/blog/2015/04/11/what-are-unit-testing-integration-testing-and-functional-testing/)

1. `Unit Testing`: Unit testing is the practice of testing small pieces of code, typically individual functions, alone and isolated. If your test uses some external resource, like the network or a database, it’s not a unit test. A good set of unit tests do not only prevent bugs, but also improve your code design, and make sure you can later refactor your code without everything completely breaking apart.

2. `Integration Testing`: You should mainly use them if you need to test two separate systems – like a database and your app – work together correctly, and that calls for an integration test.

3. `Function Testing`: Functional testing is also sometimes called E2E testing, or browser testing. Functional tests should be used for testing common user interactions. If you would manually test a certain flow of your app in a browser, such as registering an account, you could make that into a functional test. The most common tool used for functional testing is `Selenium`. Running Selenium is usually done with `Selenium WebDriver`, or `Protractor`. Sometimes `PhantomJS` and `CasperJS` can be used as well, especially if you don’t need to test in real browsers.

[The Happy Path](https://effectivecio.com/2009/11/02/the-happy-path/)

## Unit Testing

There are a number of tools in JS that make it easier to understand and implement `unit testing`. 

`Behavior Driven Development` (BDD). The topic of BDD covers the entire life cycle of the app development process, from planning the project, to writing the code. BBD encourages you to specify the behavior of your app in terms of user stores which are broken down into scenarios that can be built and tested. 

To test JS code, install a tesing framework. We use the very popular `Mocha` testing framework and the `Chai` assertion library.

`Mocha is the library that allows us to run tests, and Chai contains helpful functions that we'll uses to verify our test results`

[Install Mocha and Chai](https://www.sitepoint.com/unit-test-javascript-mocha-chai/)



