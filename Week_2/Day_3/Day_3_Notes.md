# HTTP Introduction


`HTTP` is a protocol used to read and write "resources" (data) in a simple text-based manner.

When a client wants to communicate with a server it issues a `request`. An HTTP request has 2 (of many) important components: 

 * `PATH` - says what resource the client wants to act on.

 * `METHOD`- says what action it would like to perform. 

Four important HTTP request methods (of 9): 

* `GET`: used to "get" some data from the server

* `POST`: used to create some new data 

* `PUT`: generally used for editing existing data on the server.

* `DELETE`: used to delete some existing data


In order to request a "resorce" from an HTTP server, we need to know its a `URL`; a Uniform Resource Locator. The `path` is a part if the URL. 

http://www.example.com:80/path/to/my/file.html?key1=values1&key2=value2#SomeWhereInTheDocument

http => `Scheme`

www.example.com:80 => `Authority`

www.example.com => `Domain Name`

80 => `Port`
/path/to/my/file.

html => `Path to the file`

?key1=values1&key2=value2 => `Parameters`

#SomeWhereInTheDocument => `Anchor`

[What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)

After the server has tried to perform the requested action, it sends a response back to the client. The response contains all kinds of useful information, but we'll look at two important bits here:

* Status Code
* Body

When a server wants to relay information to a client it will use a status code. The status code is a three-digit number that the server puts in the response to let the client know whether or not the operation was successful.

The main ones to keep an eye out for are below, with a translation of what they mean:

* `200`: "Everything went great!"
* `201`: "The request has succeeded and a new resource has been created as a result."
* `404`: "Resource was not found."
* `500`: "The server had an error."

The data stored in part of the response is called the body. The body may store data in many kinds of formats, such as text and images. For our purposes, the body will often contain webpages (HTML) or data encoded in JSON


