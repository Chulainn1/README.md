# Intro to Async Control Flow

`Asynchronous programming` is when a unit of work is run separately from the main thread of the program and notifies the program of its completion. 

## Asynchronus Callbacks
`JavaScript leverages callbacks in order to deal with time consuming tasks.`

## setTimeout 

`setTimeout` is used to delay the execution of some code to later. We specify the code via a callback, and the delay in ms. 

### What is this used for? 

Almost all web applications (websites) in the wild like to schedule something to occur a bit later on their webpage(s) and therefore use setTimeout.

Ex: 

1. Some sites will show a notice to the user and then automatically hide it after a few seconds. That's accomplished via `setTimeout`.

2. In Gmail or other web-based email clients, a yellow "disconnected" message popus up at the top if we go offline. It usually indicates that it will retry to connect after x seconds. This countdown and its retry is implemented using setTimeout.

3. Some websites like to pop open an in-browser chat button after a few seconds. setTimeout is used to make them appear with a short delay.

4. If you use an Adblocker browser extension, you've likely seen prompts from websites asking us to disable them for that site. These don't come up right away and instead are delayed by a few seconds. The delay here would be implemented using setTimeout.

`setTimeout` is also a great way to learn about handling delays caused by heavy operations such as reading/writing files or downloading/uploading content.