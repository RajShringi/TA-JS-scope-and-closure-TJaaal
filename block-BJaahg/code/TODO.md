## Understanding Scope and the difference between var, let and const

Watch this video before doing the exercise: https://www.youtube.com/watch?v=XgSjoHgy3Rk

1. Guess the output:

```js
let firstName = "Arya";
const lastName = "Stark";
var knownAs = "no one";

console.log(
  window.firstName, // undefined
  window.lastName, // undefined
  window.knownAs // no one
);
```

2. Guess the output:

```js
let firstName = "Arya";
const lastName = "Stark";
var knownAs = "no one";

function fullName(a, b) {
  return a + b;
}

console.log(window.fullName(firstName, lastName)); // AryaStark
```

3. Make a Execution Context Diagram for the following JS and write the output.

```js
function addOne(num) {
  return num + 1;
}
var one = addOne(0);
var two = addOne(1);
console.log(one, two); // 1 2
```

![](./img/image1.png)

4. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0);
fucntion addOne(num){
  return num + 1;
}
var two = addOne(1);
console.log(one, two); // 1 2
```

![](./img/image2.png)

5. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); // 1
function addOne(num) {
  return num + 1;
}
var two = addOne(1);
console.log(two); // 2
```

![](./img/image3.png)

6. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0); // Error addOne is not defined
const addOne = (num) => {
  return num + 1;
};
var two = addOne(1);
console.log(two);
```

![](./img/image4.png)

7. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); // Error addOne is not defined
const addOne = (num) => {
  return num + 1;
};
var two = addOne(1);
console.log(two);
```

![](./img/image5.png)

8. What will be the output of the following

```js
function isAwesome() {
  var awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); // undefined
}
isAwesome();
```

9. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (true) {
    awesome = true;
  }
  console.log(awesome); // true
}
isAwesome();
```

10. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); // undefined
}
isAwesome();
```

11. What will be the output of the following

```js
let firstName = "Arya";
const lastName = "Stark";
var knownAs = "no one";

function fullName(a, b) {
  return a + b;
}
const name = fullName(firstName, lastName);
console.log(name); // AryaStark
```

12. Guess the output of the code below with a reason.

```js
function sayHello() {
  let name = "Arya Stark";
}
sayHello();

console.log(name); // name is not defined let is function and block scope
```

13. Guess the output of the code below with a reason.

```js
if (true) {
  var name = "Arya Stark";
}
console.log(name); // Arya Stark var is function scoped not block scope
```

14. Guess the output of the code below with a reason.

```js
if (true) {
  let name = "Arya Stark";
}
console.log(name); // name is not defined let is block scope
```

15. Guess the output of the code below with a reason.

```js
for (var i = 0; i < 20; i++) {
  //
}
console.log(i); // 20 var is not block scope so we can use i outside of loop
```

16. Guess the output of the code below with a reason.

```js
for (let i = 0; i < 20; i++) {
  //
}
console.log(i); // Error let is block scope
```

17. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    var username = "John Snow";
  }
  console.log(username); // John Snow because var is not block scope and we are defining variable inside if statement inside function  we can use username inside function anywhere.
}
sample();
```

18. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    let username = "John Snow";
  }
  console.log(username); // Error let is block scope so we can't use that outside if statement.
}
sample();
```

19. Guess the output and the reason behind that.

```js
function sample() {
  var username = "Arya Stark";
  if (true) {
    var username = "John Snow";
    console.log(username); // John Snow var is not block scope and we are defining username again inside if statment which change value from Arya Stark to John Snow.
  }
  console.log(username, "second"); // John Snow, second
}
sample();
```

20. Guess the output and the reason behind that.

```js
function sample() {
  let username = "Arya Stark";
  if (true) {
    let username = "John Snow";
    console.log(username, "first"); // John Snow let is block scope there are two different username in two different scope.
  }
  console.log(username, "second"); // Arya Stark
}
sample();
```

21. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    let message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample("First", "Second", "Third");
// output using rest operator take multiple arguments and put them inside array.
// Hello I am First
// Hello I am Second
// Hello I am Third
```

22. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    const message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample("First", "Second", "Third");
// output using rest operator take multiple arguments and put them inside array.
// Hello I am First
// Hello I am Second
// Hello I am Third
```

23. Guess the output and the reason behind that.

```js
if (true) {
  const myFunc = function () {
    console.log(username, "Second");
  };
  console.log(username, "First"); // can't access username before initialization at this time username is not initialized.
  let username = "Hello World!";
  myFunc();
}
```

24. Guess the output and the reason behind that.

```js
function outer() {
  let movie = "Mad Max: Fury Road";
  function inner() {
    console.log(`I love this movie called ${movie.toUpperCase()}`);
  }
  inner();
}

outer(); // I love this movie called MAD MAX: FURY ROAD ,  inner function have closure of outer function.
```

25. Guess the output and the reason behind that.

```js
function outer() {
  let movie = "Mad Max: Fury Road";
  function inner() {
    let movie = "Before Sunrise";
    console.log(`I love this movie called ${movie.toUpperCase()}`);
  }
  inner();
}

outer(); // I love this movie called BEFORE SUNRISE, inner function first look inside it's memory if it find the variable it is going to use that if not it will look into it's closure.
```

26. Guess the output and the reason behind that.

```js
function outer() {
  let movie = "Mad Max: Fury Road";
  function inner() {
    let movie = "Before Sunrise";
    function extraInner() {
      let movie = "Gone Girl";
      console.log(`I love this movie called ${movie.toUpperCase()}`);
    }
    extraInner();
  }
  inner();
}
outer();
// output
// I love this movie called GONE GIRL extraInner function look inside it's memory and then look inside closure.
```

30. Using reduce find the final value when the initial value passed is `100`. You have to pass the output of one function into the input of next function in the array `allFunctions` starts with `addOne` ends with `half`.

```js
const addOne = (num) => {
  return num + 1;
};
const subTwo = (num) => {
  return num - 2;
};
const multiplyThree = (num) => {
  return num * 3;
};
const half = (num) => {
  return num / 2;
};

let allFunctions = [addOne, subTwo, multiplyThree, addOne, multiplyThree, half];
let result = allFunctions.reduce((acc, cur) => {
  acc = cur(acc);
  return acc;
}, 100);
console.log(result);
// Answer is: 447
```
