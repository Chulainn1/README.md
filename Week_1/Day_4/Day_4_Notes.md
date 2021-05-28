## first-class objects

This means two important things: 

1. Functions can be stored in varibales and passed around 
2. Fuctions can do everything that other objects can do (like having properties assigned to them). 

## Callback Functions

The most notable usage of having functions as values in JavaScript is a callback function.

A callback is a fuction that gets passed to another fuction, to be invoked by that fuction. 

## Anonymous Functions

Functions do not need to be named, or even assigned to a variable. These are known as anonymous functions. 

``` JS
findWaldo(["Alice", "Bob", "Waldo", "Winston"], function(index) {
  console.log("Waldo is located at:", index);
});
```

The call back function defined "inline" is not named, nor assigned to a variable. 

## Arrow Functions

Why? They are shorter, but is that necessary? They allow us to use functions in a new way. They incentivise us to make: 

* Small
* Inline
* Single purpose 

functions. 

Example: 

```JS
[1,2,3].forEach(function (num) {
  console.log('num: ', num);
});
```

VS 

```JS
[1,2,3].forEach(num => console.log('num: ', num));
```

## Higher Order Functions

Higher-Order functions are any functions which operate on other functions.

This includes callbacks. 

Built-in functions such as `forEach` and `filter` and others are "Higher-Order Functions". 

