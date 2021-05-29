# Intro to Recursion

Loops are a great language feature, and there are many opportunities to use them! 

`Recursion` is an alternative to traditional looping that allows you to do the same thing. In some languages, `for` or `while` loops do not exist and recursion is the only way of repeating code. 

`ANY` problem you can solve with a for loop, you can solve with recursion, and vice versa. 


Recursion looks like this: 

```JS
 function countEvenToTwelve(number) {
   if (number <= 12) { // Recursive Case
     console.log(number);
     // The function will call itself again and get closer to the base case
     countEvenToTwelve(number+2);
   }
   // Base case, do nothing when number > 12
 }
 countEvenToTwelve(0);
```
`A recursive function will call itself to execute code over and over again. At some point it must stop calling itself so it does not repeat forever`

In the above example, as long as `number <= 12`, the function will call itself. Once `number > 12`, the function stops. If your recursive function does not have and end point, it will crash. 

Unlike a a loop, which increments the number directly, this recursion function calls itself with a modified parameter. 

`Some things to remember:`
* We refer to `number <= 12` as a recursive case, because as long as this is true, the function will continue to call itself.

* We refer to `number > 12` as a base case. If this is true, the function will not call itself.

`A properly designed recursive function, with each recursive call, the input must gradually resolve toward the base case.`

### Another Example

```JS
const printItems = function(array) {
  for (let item of array) {
    if (Array.isArray(item)) {
      printItems(item)
    } else { 
      console.log(item);
    }
  }
};

const array1 = ["😎", "💩", "🤗", "😼", "😂"];
const array2 = ["😎", ["💩", "🤗"], "😼", "😂"];
const array3 = ["😎", [["💩", ["🤗"]], [[["😼"]], "😂"]]];
printItems(array1);
printItems(array2);
printItems(array3);
```

* The recursive case is when `item` is an array. We call the function again with that array.
* The base case is when the `item` is not an array. We just log it out.

Being able to identify when the problem you are solving is just a smaller instance of the problem you have already solved will allow you to determine when to use recursion instead of iteration. While not as commonly used as iteration, recursion is a very useful skill to have and one that developers are expected to know. It also comes up quite commonly in tech interviews.


# Object methods and 'this'

It is common in JS to have objects with properties that reference data. We can write code that references this object and its data. 

`Example:`
```JS
const person = {
  firstName: 'Bob',  // <= property containing data
  lastName:  'Smith' // <= ditto


  console.log(person.firstName);
// or ...
console.log('Hello, ' + person.firstName + ' ' + person.lastName)
}
```
Instead of string concatenation to get the persons full name we could assign a function as a value to the object. 

`Example p2:`

```JS
const person = {
  firstName: 'Bob',
  lastName:  'Smith',
  fullName: function() {
    return this.firstName + ' ' + this.lastName;
  }
}

// Nice, now I can just say:
console.log('Hello, ' + person.fullName());
// And it's much "cleaner" every time I need their full name!
```

This function simply combines both parts of the persons name. Functions that are attached to objects are called a `"method"`. Other code can invoke methods from outside the object. 

## this

However, the method needs to refer to the object that it is in. That is the most common use of `this`

For now the only importance of `this` is using it inside methods, where it points to the object where the function exists. 