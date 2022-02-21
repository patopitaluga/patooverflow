# Node / Javascript Cheatsheet

On github: https://github.com/patopitaluga/patooverflow/blob/master/node-javascript.md

Also useful:
* [Console / terminal cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/console-terminal.md)

Index:
* [Redirect](#redirect)
* [Add prefix, suffix or number to list](#add-prefix-suffix-or-number-to-list)
* [async / await](#async-await)
* [Array methods (forEach, Map, Filter and Reduce)](#array-methods)
* [Classes](#classes)
* [console log with line and file position](#console-log-with-line-and-file-position)
* [cross-platform (windows/linux/mac) folder paths](#cross-platform-folder-paths)
* [express "Hello world" starter](#express-hello-world-starter)
* [fs.writeFileSync example](#fs-writefilesync-example)
* [JSON.stringify pretty](#json-stringify-pretty)
* [List all "methods" (functions) in a class (object)](#list-all-functions-in-a-object)
* [List all properties of an object](#list-all-properties-of-an-object)
* [Replace all occurrences of a string](#replace-all-occurrences-of-a-string)
* [Vanilla minimal server](#vanilla-minimal-server)
* [Wait a couple of seconds and return a promise](#wait-a-couple-of-seconds-and-return-a-promise)
* [Truthy and Falsey: how to check if a variable "exists"](#truthy-and-falsey-how-to-check-if-a-variable-exists)

Useful tools:
copy code Chrome extension: https://chrome.google.com/webstore/detail/copy-code/ophfcfplhjmiakmfeemkpaoofhjlmkof

------
## <a name="Redirect"></a> Redirect
```
// As a mouse clicking on a link:
window.location.href = '/someurl';

// As an HTTP redirect:
window.location.replace('/someurl');
```

------
## <a name="add-prefix-suffix-or-number-to-list"></a> Add prefix, suffix or number to list
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let a = `item
item
item`
let prefix = 'z';
let suffix = 'y';
let count = true;

console.log(a.split(/\r?\n/).map((e, i) => prefix + e + suffix + ((count) ? i : '')).join('\n'));
```

------
## <a name="async-await"></a> async / await
In functions declared with "async" before the word "function", or before the "()" you can stop the running of script until the promise. In for loops will stop the loop until the promise resolves. In forEach will continue the loop with the next iteration and only prevent the code below the await of current iteration of the loop.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let wait3seconds = (n) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Some value');
    }, 3000);
  });
};

(async () => {
  let b  = await wait3seconds()
    .catch((err) => {
      console.log(err)
    });
  console.log(b);
})();

let a = async function() {
  await something();
  doSomethingLater();
}
```

------
## <a name="array-methods"></a> Array methods (forEach, Map, Filter and Reduce)
**forEach**: runs a function for every element of an array. Useful to set existing variables or run a function for every element. It's a loop structure, returns undefined: you should't be setting a variable = a forEach.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let people = [{ name: 'a' }, { name: 'b' }];
people.forEach((eachOne, index, theArray) => { // returns undefined even if you're returning inside the function
  console.log(eachOne.name);
  return 'Hi, ' + eachOne.name; // return does nothing but breaking the rest of the function.
}));
```

**Map**: returns an array with transformations of every element in other array.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let people = [{ name: 'a' }, { name: 'b' }];
let greetings = people.map((eachOne, index, theArray) => { // returns an array with each "return" as an element in the array.
  return 'Hi, ' + eachOne.name;
});
console.log(greetings);
```

**Filter**: returns an array with the elements matching the comparison.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let people = [{ name: 'a' }, { name: 'b' }];
let greetings = people.filter((eachOne, index, theArray) => { // returns an array with each item that meets its conditional statement.
  return (eachOne.name.substr(0, 1) === 'm'); // returns boolean
});
console.log(greetings);
```

**Reduce**: Returns a single value of any kind built using iterations of every element in the array. The index starts with the second place of the array to fill the "prev" value with the first. If the array has a single element returns only the element.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let people = [{ name: 'Ann' }, { name: 'Bob' }];
let initialValue = 'There\'s ' + people.length + ' people in the list: ';
let greetings = people.reduce((accumulator, currentValue, index, theArray) => { // returns a single value of any type created after looping every item in array.
  return accumulator + ((index > 0) ? ' and ' : '') + currentValue.name;
}, initialValue);
console.log(greetings);
```

------

## <a name="classes"></a> Classes
Classes were introduced in ES6/ES2015
E.g.

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
class Car {
  constructor (color, hasBumper) {
    this.color = color;
    this.hasBumper = hasBumper;
  }

  changeColor (newColor) {
    this.color = newColor;
  }
}

const alicesCar = new Car('red', true);
const bobsCar = new Car('blue', true);

bobsCar.changeColor('purple');

console.log('Alice\'s', alicesCar);
console.log('Bob\'s', bobsCar);
```
Difference between classes and objects.

------

## <a name="console-log-with-line-and-file-position"></a> console log with line and file position

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
console.trace();console.log('Hello');
```
------

## <a name="cross-platform-folder-paths"></a> path linux style in windows
Windows uses backslashes (\\) as folder separator in paths. Linux/Mac use slash "/"). To normalize paths in node to use it in any platform use path.normalize

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
console.log(path.normalize(path.join(__dirname, '/code')));
```
------

## <a name="express-hello-world-starter"></a> express "Hello world" starter

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
const path = require('path');
const express = require('express');
const app = express();
// const bodyParser = require('body-parser');

// app.use(bodyParser.urlencoded({ extended: false })); // parse application/x-www-form-urlencoded
// app.use(bodyParser.json()); // parse application/json

// app.engine('html', require('express-es6-template-engine'));
// app.set('view engine', 'html');
// app.set('views', 'views');
// app.use(express.static('public'));

// require('./routes')(app);
app.get('/', function (req, res) {
  res.send('Hello World');
  // res.sendFile(path.resolve(__dirname, './views/index.html')); // without template engine.
  // res.render('home', { locals: { foo: 'bar' }}); // with template engine.
});

app.listen((process.env.PORT || 3000), function () {
  console.log('App listening on port ' + (process.env.PORT || 3000));
});

/**
 * 404 page middleware must be set AFTER all routes, static (public) middleware AND webpack virtual files because only if any of these urls are served it must show 404 page.
 */
app.use((req, res) => {
  res.status(404).send('Content not found');
  // return res.status(404).render('page404.html', { });
});
```

------
## <a name="fs-writefilesync-example"></a>fs.writeFileSync example
Example:
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
fs.writeFileSync("output.json", JSON.stringify(content, null, 2));
```

------
## <a name="json-stringify-pretty"></a>JSON.stringify pretty
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
JSON.stringify(obj, null, 2);
```

------
## <a name="list-all-functions-in-a-object"></a>List all methods of a class
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
console.log(Object.getOwnPropertyNames(className).sort());
```
or
<details>
  <summary>ES5</summary>

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
console.log(Object.getOwnPropertyNames(Math).filter(function(p) { return typeof Math[p] === 'function'; }));
```

</details>
<details>
  <summary>ES6/ES2015</summary>

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
console.log(Object.getOwnPropertyNames(Math).filter((p) => typeof Math[p] === 'function' ));
```

</details>

------
## <a name="list-all-properties-of-an-object"></a>List all properties of an object
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
for (var propertyName in myObject) {
  // propertyName is what you want
  // you can get the value like this: myObject[propertyName]
}
```

------
## <a name="replace-all-occurrences-of-a-string"></a>Replace all occurrences of a string

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
"foo bar".replace(/foo/g, 'hi');
```

------

## <a name="vanilla-minimal-server"></a>Vanilla minimal server

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
require('http').createServer((req, res) => {
  // res.end('123');
  // res.writeHead(200, { 'Content-Type': 'image/jpg' }); // for example to serve a public file
  res.end(require('fs').readFileSync(require('path').resolve(__dirname, './index.html'), 'utf8'));
}).listen(3000, () => console.log('Listening port 3000'));
```

------
## <a name="wait-a-couple-of-seconds-and-return-a-promise"></a>Wait a couple of seconds and return a promise
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
let wait3seconds = (n) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Some value');
    }, 3000);
  });
};
```
------

## <a name="truthy-and-falsey-how-to-check-if-a-variable-exists"></a>Truthy and Falsey: how to check if a variable "exists"
<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');" class="cpy-btns"></button>
```
Boolean(undefined); // => false
Boolean(null); // => false
Boolean(false); // => false
Boolean(0); // => false
Boolean(""); // => false
Boolean(NaN); // => false

Boolean(1); // => true
Boolean([1,2,3]); // => true
Boolean(function(){}); // => true
```

.

------
Ignore the rest code. Is styling for local display of this file using https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
<style>
  .markdown-body {
    position: relative;
  }
  .cpy-btns {
    background: transparent;
    border: 0;
    cursor: pointer;
    display: block;
    font-family: monospace;
    font-size: 11px;
    margin-top: -4px;
    position: absolute;
    right: 45px;
    width: auto;
  }
  .cpy-btns::before {
    content: 'COPY'
  }
</style>
