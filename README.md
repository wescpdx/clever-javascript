# clever-javascript

A simple collection of JavaScript snippets that I find interesting. 

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

## Concurrent Promises

```javascript
const thingsToDo = [
    fetch("http://server/api/first-endpoint/"),
    fetch("http://server/api/second-endpoint/"),
]
const returnStatus = await Promise.all(thingsToDo);
```

[Promise.all()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)

## Cast a Whole Array

```javascript
const mixedType = ["1", 5, "2.84"];
const 
```

[Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

## Console Timer

```javascript
console.time("performance-loop");
for (let i = 0; i < 10000; i++) {
    someFunction();
}
console.timeEnd("performance-loop");  // performance-loop: 1.075927734375 ms
```

[console.time()](https://developer.mozilla.org/en-US/docs/Web/API/console/time)

