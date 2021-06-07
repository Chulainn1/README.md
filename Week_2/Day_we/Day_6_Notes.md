# How is JS working
## Promises 

The promise object is used for deferred and asynchronous computations. Asynchronous code is not gauarnteed to execute in a single unbroken timeline.
 * Network requests
 * events
 * threads 

Callbacks are the default JS technique for asynchronous work. However, the best way to handle asyc code is through the use of **Promises**. 

There are four states a promise can have:

1. fulfilled - action related to the promise succeeded 

2. rejected - failed 

3. pending - promise is in limbo 

4. settled - either it fulfilled or was rejected

### How and when are promises executed

```JS 
new Promise(function(resolve, reject){
  resolve('hi);
  resolve ('bye);
}); 
```

A promise can only settle once. In the second scenario above, resolve is doing nothing since it settled in the first scenario. Promises execute in the main thread meaning they are potentially blocking They are simply a technique for deciding what will happen when an async task settles. A promise is a try catch wrapper around code that will finish at an unpredictable time. 

A promise is a constructor. You pass a function to a promise with two arguments. Those arguments are `resolve` and `reject`. They are both callbacks that you use to sepcify when a promise has fulfilled because something has worked; or rejected when something went wrong. When either resolve or reject has been called, the promise has been settled, and at that point usually a `.then` or a `.catch` is then executed. Any value passed to resolve or reject will be recieved as an argument by the .then or the .catch. If nothing is passed to resolve or reject, the nect link in the chain recieves undefined. If the value that is passed is another promise, that promise will execute first. The value it resolves to will be passed to the next link in the chain. If there is a JS error in the body of the promise  .catch will get called. 

.catch is short hand for 

```JS 
.then(undefined, rejectFunc); 
```
## Clean Code
[Here](https://github.com/airbnb/javascript#types)

[objects](https://github.com/airbnb/javascript#objects)

[arrays](https://github.com/airbnb/javascript#arrays)

[strings](https://github.com/airbnb/javascript#strings)

[functions](https://github.com/airbnb/javascript#functions)

[15 steps for clean and easy to read code](https://code.tutsplus.com/tutorials/top-15-best-practices-for-writing-super-readable-code--net-8118)

## cURL 

[15 Practical Linux cURL Command Examples](https://www.thegeekstuff.com/2012/04/curl-examples/)

## Character Encoding

To refer to characters in an unambiguous way, each character is associated with a number, called a `code point`. The characters are stored in the computer as one or more `bytes`. A `character encoding` provides a key to unlock the code. It is a set of mappings between the bytes in the computer and the characters in the character set. Character encoding maps the letters you type to specific bytes in computer memory. To display the text it reads the bytes back to characters.

[More](https://www.w3.org/International/questions/qa-what-is-encoding.en#endlinks)

[video explanation](https://www.youtube.com/watch?v=MijmeoH9LT4&ab_channel=Computerphile)

[The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)


## Domain Name System

### DNS Record types
* A: most common; map a hostnames to IP address (IPv4, 32-bit address)
* NS: Name Server that is responsible for a DNS zone
* MX: Mail Exchange record specifies where email gets sent to
* CNAME: Canonical Name, an alias for another hostname
* AAAA: similar to A, but uses IPv6, 128-bit address

