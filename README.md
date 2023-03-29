# clever-javascript

A simple collection of JavaScript snippets that I find interesting.

# Arrays

## Cast a Whole Array

```javascript
const mixedType = ["1", 5, "2.84"];
const onlyNumbers = mixedType.map(x => parseInt(x));
```

[Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

## Get Last Array Element

```javascript
const myArray = [1, 2, 3, 4];
const lastElement = myArray.slice(-1);  // 4
```

[Array.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

## Remove Empty Array Elements

```javascript
let myArray = [1, 2, null, , 3, 4];
myArray = myArray.filter(n => n);
```

[Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Coerce Array

```javascript
const people = [
    { name: "Bob", age: 25},
    { name: "Joan", age: 33},
    { name: "Mike", age: 29},
    { name: "Candice", age: 54},
];
const allNames = Array.from(people, ({name}) => name);
// allNames = ["Bob","Joan","Mike","Candice"]
```

[Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)

# Math

## Faster Math.Floor
```javascript
~~2 === Math.floor(2);  // true
~~2.82398 === Math.floor(2.82398)  // true
```

[Bitwise NOT](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_NOT)
[Tilde or the Floor?](http://rocha.la/JavaScript-bitwise-operators-in-practice)

# Promises

## Concurrent Promises

```javascript
const thingsToDo = [
    fetch("http://server/api/first-endpoint/"),
    fetch("http://server/api/second-endpoint/"),
]
const returnStatus = await Promise.all(thingsToDo);
```

[Promise.all()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)

## Promise Polling

```javascript
const timeout = (time) => new Promise((resolve) => setTimeout(() => resolve(true), time));

while (!isReady()) {
    await timeout(1000);
}
```
[More reusable version](https://blog.openreplay.com/forever-functional-waiting-with-promises/)

# Other Stuff

## Sequential IDs with a Generator

```javascript
function* getNextId() {
    let counter = 1000;
    while (1) {
        yield counter++;
    }
}
```

[Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator)

## Replace Using a Callback

```javascript
function styleHyphenFormat(propertyName) {
  function upperToHyphenLower(match, offset, string) {
    return (offset > 0 ? "-" : "") + match.toLowerCase();
  }
  return propertyName.replace(/[A-Z]/g, upperToHyphenLower);
}
```
[String.replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

## Console Timer

```javascript
console.time("performance-loop");
for (let i = 0; i < 10000; i++) {
    someFunction();
}
console.timeEnd("performance-loop");  // performance-loop: 1.075927734375 ms
```

[console.time()](https://developer.mozilla.org/en-US/docs/Web/API/console/time)
