1. Convert the function below into different forms of function expression.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}

// Your code goes here
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
let percentage = (marks, total) => (marks * 100) / total;
```

2. Write Function Declaration or Function Expression next to the function.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}
// Your answer
let percentage = (marks, total) => (marks * 100) / total;
```

```js
let percentage = function percentage(marks, total) {
  return (marks * 100) / total;
};

function percentage(marks, total) {
  return (marks * 100) / total;
}
```

```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};

function percentage(marks, total) {
  return (marks * 100) / total;
}
```

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};

function percentage(marks, total) {
  return (marks * 100) / total;
}
```

```js
let percentage = (marks, total) => (marks * 100) / total;

function percentage(marks, total) {
  return (marks * 100) / total;
}
```

3. Why is a function definition an expression in JavaScript? Give one example of function expression.
   function is an object in javascript and object is an expression so we can treat function like expression.

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
```

4. Why is a function call an expression in JavaScript?  
   expression is something which return some value and a function return a some value or undefined.

5. Write VALID and INVALID next to each example below with the reason.

```js
function add(a, b) {
  return a + b;
}

let five = add(2, 3); // Answer valid
five = add; // Answer valid
five = five(10, 11); // Answer valid
five = function () {
  return "Hello";
}; // Answer valid
```

6. What is the difference between function definition and function call? Explain with an example.

```js
// function Defination - this tells what function will do.
function sum(a, b) {
  return a + b;
}

//function call - when we need to execute the function.
sum(3, 4);
```

7. What is the similarities between function definition and function call?  
   in function defination we tell what this function will do and when we need to execute that function we call it.
8. Is the code below valid or invalid. Explain with reason.

```js
function hello() {
  console.log("Hello World!");
}

hello.user = "Sam"; // valid or invalid valid
```

9. What is higher order function explain with an example.
   higher order function is a function which can take function as an argument or can return a function.

```js
function filter(arr, cb) {
  let filterArray = [];
  for (let item of arr) {
    if (cb(item)) {
      filterArray.push(item);
    }
  }
  return filterArray;
}

function MultiplyBy(num) {
  return function (num2) {
    return num * num2;
  };
}
```

10. Explain what is callback function. Why you can pass a function inside a function?
    A callback function is passed as argument to another function which then invoked inside outer function to perform some task. we can pass function inside another function because function is an expression and we can pass an expression as function arguments.
