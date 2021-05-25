## What are gists? 

Simply put, a gist is a git repository for smaller bits of code that are easy to share. 

However they cannot be given a name, instead it is assigned a cryptic one. Gists cannot have multiple people contributing to it. Gists must be forked. 

A `public` gist is searchable/discoverable. `Secret` gists are `not` private but you need a specific URL to acces them.  

### Forking and Cloning gists 

1. Browse to gist
2. Fork it (top right) - forking creates your own copy of another GH users repo. This is useful as it promotes collaboration on projects
3. Copy SSH URL 
4. In terminal under the correct directory, clone the SSH URL by using this command: 
`git clone git@gist.github.com:YOUR_FORKS_ID.git NAME`
where NAME is the folder that will contain the repo. 


`Fork copies the repository on the server, and clone copies it to the local disk`

## Code Linting 

Lint, or a linter, is a tool that analyzes source code to flag programming errors, bugs, stylistic errors, and suspicious constructs.

One of the most prominent / well-adopted linting solutions is ESLint


## Git, Markdown, and the Dev Workflow

`git status` – check the status of files

`git init` – initialize new git repo

`touch` ‘filename’ – create a file using the terminal 

`git add` ‘filename’ – add file to the repository 

`git commit` -m ‘description of file’  - commit the changes

`git remote add origin` <URL> - add the URL of the new repo as a remote on your local repo 

`git push -u origin master` – push changes to GitHub

## Parsing Command Line Arguments

[Command line arguments](https://stackabuse.com/command-line-arguments-in-node-js/) are a common way of getting user input in a program.

The simplest way of retrieving arguments in Node.js is via the `process.argv` array. The first element of the `process.argv` array will always be a file system path pointing to the node executable. The second element is the name of the JavaScript file that is being executed. And the third element is the first argument that was actually passed by the user.

### sum.js
```js 
const args = process.argv.slice(2);

const sum = function(array) {
  let total = 0;
  for (let i of array) {
    total += Number(i);
  }
  console.log(total);
};

sum(args);
```

In the console I would pass in the values I would like to add and it will return the sum. For example: 

node sum.js 3 5 6 

`14`


## What is a Library? 

A "library" is a collection of pre-written code. Libraries can be private, but many are packaged up nicely, branded and made publicly available for other developers to use in their own projects.

Examples: 

* jQuery 
* Bootstrap
* Lodash

### Lotide: Our Clone of Lodash

I will build small functions to exercise my programming skills throughout these first two weeks, essentially I will build my own smaller and simpler version of this awesome Lodash.

### ES6 Template Literals 

```JS
const name = 'Leam';
console.log('Hello, ' + name + '!')// logs: Hello, Leam!;
```
VS

```JS
const name = 'Leam';
console.log(`Hello, ${name}!`); // logs: Hello, Leam!
```
The second ~`template literal`~  method is faster and uses less computer memory. 

Another example: 


```JS 
const assertEqual = function(actual, expected) {
  if (actual === expected) {
    console.log(`✅✅✅ Assertion Passed: ${actual} === ${expected}`);
  } else {
    console.log(`🛑🛑🛑 Assertion Failed: ${actual} !== ${expected}`);
  }
  
};
assertEqual("Lighthouse Labs", "Lighthouse Labs");
assertEqual("Lighthouse Labs", "Bootcamp");
assertEqual(1, 1);
assertEqual(1, 2);
```
