# Node / Javascript Cheatsheet

Index:
* [Array methods (forEach, Map, Filter and Reduce)](#array-methods)
* [Classes](#classes)
* [console log with line and file position](#console-log-with-line-and-file-position)
* [cross-platform (windows/linux/mac) folder paths](#cross-platform-folder-paths)
* [List all "methods" (functions) in a class (object)](#list-all-functions-in-a-object)

------
## <a name="array-methods"></a> Array methods (forEach, Map, Filter and Reduce)
**forEach**: runs a function for every element of an array. Useful to set existing variables or run a function for every element. It's a loop structure, returns undefined: you should't be setting a variable = a forEach.
```
let people = [{ name: 'a' }, { name: 'b' }];
people.forEach((eachOne, index, theArray) => { // returns undefined even if you're returning inside the function
  console.log(eachOne.name);
  return 'Hi, ' + eachOne.name; // return does nothing but breaking the rest of the function.
}));
```

**Map**: returns an array with transformations of every element in other array.
```
let people = [{ name: 'a' }, { name: 'b' }];
let greetings = people.map((eachOne, index, theArray) => { // returns an array with each "return" as an element in the array.
  return 'Hi, ' + eachOne.name;
});
console.log(greetings);
```

**Filter**: returns an array with the elements matching the comparison.
```
let people = [{ name: 'a' }, { name: 'b' }];
let greetings = people.filter((eachOne, index, theArray) => { // returns an array with each return as an element in the array.
  return (eachOne.name.substr(0, 1) === 'm'); // returns boolean
});
console.log(greetings);
```

**Reduce**: Returns a single value of any kind built using iterations of every element in the array. The index starts with the second place of the array to fill the "prev" value with the first. If the array has a single element returns only the element.
```
let people = [{ name: 'a' }, { name: 'b' }];
let greetings = people.reduce((prevValue, currentValue, index, theArray) => { // returns an array with each return as an element in the array.
  console.log(index);
  return 'Hello ' + prevValue.name + ' and ' + currentValue.name;
});
console.log(greetings);
```

------

## <a name="classes"></a> Classes
Classes were introduced in ES6/ES2015
E.g.
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
```
console.trace();console.log('Hello');
```
------

## <a name="cross-platform-folder-paths"></a> path linux style in windows
Windows uses backslashes (\) as folder separator in paths. Linux/Mac use slash "/"). To normalize paths in node to use it in any platform use path.normalize
```
console.log(path.normalize(path.join(__dirname, '/code')));
```
------
## <a name="list-all-functions-in-a-object"></a>List all methods of a class

```
console.log(Object.getOwnPropertyNames(className).sort());
```
or
<details>
  <summary>ES5</summary>

```
console.log(Object.getOwnPropertyNames(Math).filter(function(p) { return typeof Math[p] === 'function'; }));
```
</details>
<details>
  <summary>ES6/ES2015</summary>

```
console.log(Object.getOwnPropertyNames(Math).filter((p) => typeof Math[p] === 'function' ));
```
</details>
