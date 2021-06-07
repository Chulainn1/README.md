# JSON 

JSON is a data format that underoins may modern web services. It stands for `JavaScript Object Notation`, and it's a subset of the JavaScript language.

[JSON](https://www.json.org/json-en.html)

JSON is built on two structures: 

 * A collection of name/value pairs.
 * An ordered list of values.

 An Object encoded using JSON looks like this:
 ```JS
 {
  "name": "New York City",
  "boroughs": [
    "Manhattan",
    "Queens",
    "Brooklyn",
    "The Bronx",
    "Staten Island"],
  "population": 8491079,
  "area_codes": [212, 347, 646, 718, 917, 929],
  "position": { "lat": 40.7127, "lng": -74.0059 }
}
```
## Serialization 

Converts objects (or data structures) into a format that can be stored or transmitted between computers (typically a string of text).

### JSON.parse()

Parse a string as JSON, optionally transform the produced value and its properties, and return the value.

Returns an object

### JSON.stringify()

Return a JSON string corresponding to the specified value, optionally including only certain properties or replacing property values in a user-defined manner.

## JSON Media Type

the `Media Type` for JSON data is application/json (compared to text/html for HTML). It is set via the `Content-Type` HTTP response header.

* A media type is a two-part identifier for file formats and format contents transmitted on the Internet. 

* Check the Content-Type in the response header by running the forllowing cURL cmd. 
  * curl -i ipinfo.io

## JSON is Language Independent 

Not just used in Node / JS projects. We see it heavily used in other programming langages/ecosystems such as Python, Ruby, C#, Java, Golang, Rust, etc...

Since objects are an easy way to store key-value data, we learned about how this JavaScript Object Notation is used to store configuration/setting information in files (such as package.json) and how we can easily use two methods on the JSON object to convert between actual object and string representation of that data.

# What is an API

APIs (`Application Programming Interface`) allows systems to work together. 

APIs allow is to leverage the functionality of external services to unlock great potential. 

[What APIs are and Why They're Important](https://readwrite.com/2013/09/19/api-defined/)

[API concepts and examples](https://youtu.be/7YcW25PHnAA)

# Promises

A promise represents the eventual result of an asynchonous operation. The primary way of interaction with a promise is through its `then` method, which registers callbacks to receive either a promise's eventual value or the reason why the promise cannot be fulfilled. `Callbacks are wrapped in a promise`.

* a promise is an object
* promises do not rely on anything other than basic JS
* as of ES6, JS has promises supported natively in its code. in other words, they are built into the language. 

* error handling becomes much simpler with promises

* promises make asynchonus code easier to unit test

* `Promise.all` can be used to run multiple async operations in parallel and have a single callback to see all the results together. 

