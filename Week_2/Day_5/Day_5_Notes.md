# Introduction to Object Oriented Programming 

`Object Orientation` is the biggest concept in software development philosophy of the last thirty years. 

* Object-Oriented Programming is a way of writing code that encourages modularity and reduces duplication through the use of *objects*.

JavaScript pupularized *Functional Programming* but was also OO. In ES6, JavaScript brought in more OOP features. In OOP we use objects to group related variables and functions together to keep our code more organized. 

* An object is a collection of key-value pairs known as properties. 
* An object is a bundle of information, AKA a `state`.Each property and object has can represent the state of that object. 
* When functions are tied to the object, this is called a `method`. The `behaviour` of an object takes the form of metehods. 

### this 

Using `this` is important to be able to do OOP in JavaScript. When you use **this** inside a method, **this** refers to the object that the method was called on. 

## Classes

JvaScript's object system is based on another pattern known as prototypes, not classes. Classes were added to JS in ES6 and help us work with prototypes in an easier way. **JavaScript now mimics the behaviour of class-based or classical OOP languages**. Classes in JS do not add new features, just different syntax to complete tasks differently. 

### classes are blueprints

In OOP `clasess` are templates/blueprints that we use to create `instances` of objects. A class describes what the object is going to be an we can create new objects using the class. 

When you create an object using a class, it is an instance of that class. 

```JS
class Pizza {

}

let pizza1 = new Pizza();
let pizza2 = new Pizza();
```

Above, a pizza class was created. Then, we created two instances of the pizza class. They are separate objects.

### methods and properties

### Inheritance

### Super and Method Overriding

When a subclass implements a method that already exists in the superclass, it is called `method overriding`. 

OOP languages allow subclasses to have a reference on the parent class. This is usually done via the `super` keyword. 


### Getters and Setters

Two main reasons you may want to use getters and setters in you app.

1. *validating* data before assigning it to a property
2. *computing* a value on the fly instead of simply pulling it out of a property

Using a setter method instead of setting the property value directly enables you to validate the value before it gets set. 

JS classes have special `get` and `set` keywords. The get and set syntax binds an objects property to a function that will be called when that value is looked up. 


## OOP Best Practices 

### Abstraction 

Abstraction is a technique for arranging complexity of computer systems. It works by establishing a level of complexity on which a person interacts with the system, suppressing the more complex details below the current level.

### Single Responsibility Principle

The single responsibility principle states that a class should be responsible for a single part of the app's functionality, giving it only one reason to change. Or more simply, a class should only have one job


