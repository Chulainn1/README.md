# Objects

## The Six Primitive Types in JavaScript

In JavaScript all `values which are not Objects` are reffered to as `primitives`. They represent the simplest possible type of data that our software can have. 

Let's review the six types of primitives:
* undefined
* null
* boolean
* string
* number
* symbol (Introduced in ES6 and not something we need to focus on right now)

### Objects Are Not Primitives

Objects (including `arrays`, `functions`, and other types of objects) have properties. The six primitive types, plus objects, make up the seven fundamental types of JavaScript. 

## Basic Concepts
Some important things to remember about objects: 

* Contain `key-value pairs`; each key maps to a value
* Contains `keys` which are `always strings` (or symbols)
* Have unique keys; the same key cannot appear twice in an object
* Have their keys point to values which can be of any type

Objects have a literal syntax using braces {}. An empty object literal assigned to a variable would look like this: 

```js
const emptyObject = {};
```
An ovject with a single key `"size"`associated with a value `"Tiny"` creating a key-value pair: 

```js
const smallObject = {"size": "Tiny"};
```
An object's values can be of any type. THe following example shows an object with primitive values. 

```js 
const myObject = {
  a: 6,     // Number
  b: "abc", // String
  c: true,  // Boolean
  d: null,  // Null
};
```

To access a value within an obejct we use square-bracket notation.

```js
const person = {firstName: "Leam"};

const firstName = person["firstName"];
```

When accessing an object property using the square brackets (`[]`), the key `must` be quoted (as a string). Otherwise it would be considered a variable instead of a string literal. 
###### If that variable name instead points to a string, then that can be an interesting way of accessing a key.

You can use square-bracket notation to assign new values to new or existing keys: 

```js
const Leam = { name: "Leam Murphy" };
Leam["name"] = "Leam Antonious";
Leam["age"]  = 23;
Leam // shows the resulting object with both properties
```

We can nest objects within objects. The key-value pair in an object can have a value that is another object. 
```js
const person = {
  name: "Chulainn",
  address: {
    street: "310 W 95th",
    city: "Calgary",
    zipCode: 10027
  }
};

person['address']['city'];
//returns Calgary
```

When writing object literals like `{myKey: "some value" }`, the key is always interpreted as a literal string, even if its unquoted. You `MUST` use quotes for a key when the key contains `spaces, hyphens or periods`. Ex: `{ "my-hyphenated-key": "some value" }`. 

To inspect an object's keys use the method `Object.keys(...)` that returns an array of keys.

To inspect the data type of a key use the operator `instanceof` Ex:
```js 
person["name"] instanceof String
person["name"] instanceof Object
person["name"] instanceof Array
/// return boolean
```
### Objects are highly flexible data structures and the foundation to almost everything in JavaScript. 


## Iteration

JavaScript objects are not iterable the way that arrays are. We must use a `for...in` statement to traverse all the properties of this object.

```js
const planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};

for (var planet in planetMoons) {
  var numberOfMoons = planetMoons[planet];
  console.log("Planet: " + planet + ", # of Moons: "+ numberOfMoons);
}
```

## Bonus on Primitives and Objects in JS

In JS, primitives do not have properties. However, primitives has a corresponding object constructor.

And object constructor can be invoked with the word new.