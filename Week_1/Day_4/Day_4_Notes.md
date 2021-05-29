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

# Vim

Vim is a code editor thats been around since 1991. Familiarity with basic vim commands is pretty useful - if not absolutely necessary - if you have to edit a file in a remote ssh terminal.

Vim has two modes: 

1. `edit mode`: the state in which the keys you type on are actually inserted into your doc.

2. `command mode`: allows you to navigate through the doc, search and replace text, copy and paste, etc... 

By default you are placed in command mode. To switch to `edit mode` press `i` to insert text at the cursor position. Press `a` to insert after the cursor position. Get out of edit mode by pressing `Esc`. 

Use the keys `H` to move left; `K` to move up; `L` to move right; `J` to move down.


Use the keys (while in command mode):
* `Y` to copy a line fo text to the `buffer`.
* `P` pastes it to the cursor's current position. 
* `dd` will delete the whole line of text. It also "cuts" it as it is placed in the buffer. 
*  `yy` copies a whole lne of text
* `:w` to save the text. 
