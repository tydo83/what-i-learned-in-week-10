# What I learned in week 9 & 10

## Nodemon
nodemon is a command-line interface utility. It watches the file system. If there is a change, it quits and runs node again.

---
## Callbacks
A callback is a function passed as an argument to another function. This technique allows a function to call another function. A callback function can run after another function has finished

---
## Async function
An async function is a function declared with the async keyword. Async functions are instances of the AsyncFunction constructor, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.
>### setTimeout 
```
setTimeout(() => alert("Hi"), 3000);
```
>### clearTimeout
```
let myVar;

function myFunction() {
  myVar = setTimeout(function(){ alert("Hello"); }, 3000);
}

function myStopFunction() {
  clearTimeout(myVar);
}
```
>### setInterval
```
setInterval(function(){ 
	console.log("Oooo Yeaaa!");
}, 2000);//run this thang every 2 seconds
```
>### clearInterval
```
let interval = setInterval(function() {
  console.log("Hello World");
}, 1000);

function stopInterval() {
	clearInterval(interval);
}
```
---
## Readline and Interface
```
//Node.js readline
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

rl.question('What do you think of Node.js? ', (answer) => {
  console.log(`Thank you for your valuable feedback: ${answer}`);
  rl.close();
```
---
## File System
> ### read data from a file 
```
const fs = require('fs');

fs.readFile('/Users/joe/test.txt', 'utf8' , (err, data) => {
  if (err) {
    console.error(err);
    return
  }
  console.log(data);
});
```
>### write date to a file 
```
// writefile.js

const fs = require('fs');

let lyrics = 'But still I\'m having memories of high speeds when the cops crashed\n' + 
             'As I laugh, pushin the gas while my Glocks blast\n' + 
             'We was young and we was dumb but we had heart';

// write to a new file named 2pac.txt
fs.writeFile('2pac.txt', lyrics, (err) => {
    // throws an error, you could also catch it here
    if (err) throw err;

    // success case, the file was saved
    console.log('Lyric saved!');
});
```
---
## Refactoring 101 
>### Change string to number
```
+strNum == Number(strNum)
```
>### Change string to number
```
str + '' == str.toString(); 
```
---
## JSON
JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web applications (e.g., sending some data from the server to the client, so it can be displayed on a web page, or vice versa).
>### The JSON.parse
* The JSON.parse() method parses a JSON string, constructing the JavaScript value or object described by the string.
```
JSON.parse(data)
```
>### JSON.stringtify
* The JSON.stringify() method converts a JavaScript object or value to a JSON string, optionally replacing values if a replacer function is specified or optionally including only the specified properties if a replacer array is specified.
```
let data = {
  name: "John Smith",
  age: 30,
  hobbies: ["Programming", "Video Games"]
};

// {name:"John Smith",age:30,hobbies:["Programming","Video Games"]}
let miny = JSON.stringify(data);

// The 4 parameter signifys 4 spaces. You can also use "\t".
/* {
```