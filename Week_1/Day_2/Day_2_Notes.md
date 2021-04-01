## Minimum Values Challenge

Fork and cloned this [gist](https://gist.github.com/kvirani/93d265b877e3efc1c5cc7217cc4e8ee3). In this activity, we're going to write code that finds the smallest value in a list of numbers. We will need to use our knowledge of arrays, loops, and variables.

``` js
const min = function(numbers) {
  let len = numbers.length;
  for (let i = 0; i < len; i++) {
    for (let j = 0; j < len; j++) {
      if (numbers[j] > numbers[j + 1]) {
        let tmp = numbers[j];
        numbers[j] = numbers[j + 1];
        numbers[j + 1] = tmp;

      }
    }
  }
  return numbers[0];

};

const flightPrices = [1260, 490, 599, 1400, 820];
console.log(`The cheapest flight amongst $1260, $490, $599, $1400 and $820 costs:  $${min(flightPrices)}`);
```

I wrote a bubble sort that will sort the numbers from least to greatest and return the
number at index 0 of the array. Index 0 should be the smallest value after the sort. 


## Solving Problems With Pseudocode

We must understand the problem inorder to solve it. Ask these questions before attempting to solve the problem. 

1. What is the `input` to the problem?(can be more than 1)
2. What us the `expected output` of the program? Calculate the first few steps by hand to recognize patterns. 

It is a good idea to describe in spoken language the solution you want to implement. Pseudocode is written english, 'almost code' - that can be easily translated to JS. 

### Example of Psuedocode

Problem - Write a program that prints numbers from 100 to 200 to the console.

```
Loop from 100 to 200:
 Let num = the current step in the loop
 Print num
End loop
```

Tanslating this to JS is easy.

```js 
for (let num = 100; num <= 200; num++) {
  console.log(num)
}
```
### Can You Write it Better? 

It is important to take the time to refactor your code whether it is to improve its performance, readability or code re-use. Check for patterns to minimize duplicate code. 

## Joining Concepts Problem

```js 
const conceptList = ["gists", "types", "operators", "iteration", "problem solving"];
```

Forked and cloned this [gist](https://gist.github.com/kvirani/7f98a6a8c067e1ff8d754f2289c6a382). We are writing a small algorithm for joining the strings in conceptList together, separated by commas, such that the final output reads: 

`Today I learned about gists, types, operators, iteration, problem solving.`

We cannot use any built-in methods of JS, that means not using `Array.prototype.join`

``` js 
const joinList = function(arr) {
  let str = "";
  for (let i = 0; i < arr.length; i++) {
    const word = arr[i];
    if (i < arr.length - 1) {
      str += word.toString() + ", ";
    } else {
      str += word.toString() + "";
    }
  }
  return str;
};

// Test / Driver Code below...
const conceptList = ["gists", "types", "operators", "iteration", "problem solving"];
const concepts = joinList(conceptList);
console.log(`Today I learned about ${concepts}.`);
```
My function joinList takes in an array, iterates over it and places a comma if the current index position (i) is less than the last index (indicated by the arr.length -1) otherwise if i = arr.length -1, no comma should be added. 

## Function Best Practices

Read [Growing Functions + Functions & Side Effects](https://eloquentjavascript.net/03_functions.html#h_eVDWIAuyBK) documentation. Here is a summary. 

* Two natural ways for functions to be introduced into programs.
  * When you're writing the same code multiple times you can place it into a function (with a good name).

  * When you need some functionality that seems like it needs its own function.

* Make the names obvious so you can easily figure out what it does in the future. A good name is short and explains exactly what the function does as unambiguously as possible.

* Don't add cleverness. 

* Functions can be roughly divided into those that are called for their side effects and those that are called for their return value.

* A `pure` function is a specific kind of value-producing function that not only has no side effects but also doesn’t rely on side effects from other code—for example, it doesn’t read global bindings whose value might change. 

### Rolling Dice Problem 

Write a program that takes a single parameter from the command line, a number, and rolls that many six-sided dice.

This problem was harder for me and my solution is not the best way for it to be solved. However, I did solve it. Here is my solution: 

```js 
let num = Number(process.argv.splice(2));

const rollDice = function(num) {
  let arr = [];
  let results = '';
  for (let i = 0; i < num; i++) {
    let diceRolls = "";
    diceRolls =  Math.floor((Math.random() * 6) + 1);
    arr.push(diceRolls);
  }
  for (let i = 0; i < arr.length; i++) {
    const word = arr[i];
    if (i < arr.length - 1) {
      results += word.toString() + ", ";
    } else {
      results += word.toString() + "";
    }
  }
  return results;
};

console.log("Rolled " + num + " dice: " + rollDice(num));
```

## Fixing Buggy Code - Console Log

This assignment is a `Pig Latin Translator`. It should take a phrase from the command line and translate it to pig latin. 

`Original (buggy) Code`
```js 
var originalWords = process.argv.slice(2);
var pigLatinWords = [];

for (var i = 1; i < originalWords.length; i++) {
  pigLatinWords.push(translateToPigLatin(originalWords[i]));
}

console.log(pigLatinWords.join(' '));

function translateToPigLatin(word) {
  return word.slice(2, word.length) + word[0] + "ay";
}
```

It can be difficult to pinpoint where something is going wrong when many things are happening in the code. A common practice is to isolate and eliminate pieces that are working as expected by using a well-placed `console.log` statement. 

Break down the code into its different pieces.

1. 

```js 
var originalWords = process.argv.slice(2);
var pigLatinWords = [];

console.log("originalWords is", originalWords);
console.log("pigLatinWords is", pigLatinWords);
```
Everything works fine! 

2. 

```js 
for (var i = 1; i < originalWords.length; i++) {
  console.log(originalWords[i]);
  pigLatinWords.push(translateToPigLatin(originalWords[i]));
}
```
Looks like we've found something wrong! We expected to see all the words in originalWords in the output, but the first is missing (pig). This means we're starting our iteration with the second element.

This process is repeated for all sections of the code and the code is fixed accordingly. 

` Fixed Pig Latin Translator Code`

```js 
var originalWords = process.argv.slice(2);
var pigLatinWords = [];

//console.log("originalWords is", originalWords);
//console.log("pigLatinWords is", pigLatinWords);


for (var i = 0; i < originalWords.length; i++) {
  //console.log(translateToPigLatin(originalWords[i]))
  pigLatinWords.push(translateToPigLatin(originalWords[i]));
}

console.log(pigLatinWords.join(' '));

function translateToPigLatin(word) {
  //console.log("Word", word);
  //console.log("First letter", word[0]);
  //console.log("rest of word", word.slice(2, word.length));
  return word.slice(1, word.length) + word[0] + "ay";
}
```

### Debugging Errors Assignment 

forked and cloned this [gist](https://gist.github.com/kvirani/5ae6f3171b87acfb452bcf23e6f2dc41). Worked on fixing the two JS files to work properly. The average.js file takes an array of numbers and provides their average. The reverse.js file takes an input from the terminal and reverses it.

## Quiz - Functions, Variables, and Debugging in JavaScript 

`Type coercion` is When the operands of an operator are different types, one of them will be converted to an equivalent value of the other operand's type. An example is the comparison operator == in JavaScript. 



