Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

Example:

```js
function hello() {
  var username = "Arya";
}
console.log(useranme); // output
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the function named `hello` and we can't access the variable defined inside a function from outside.

The above code will throw an error `Reference Error username is not defined`.

2. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
{
  const username = "Arya";
}
console.log(useranme); // output
```

In above code we are looking for the variable `username`. There is not variable named `username` in the global scope. The variable `username` is inside a block. we can't access the variable `username` because we can't go inside another scope we can only bubble out to look for a variable.

The above code will throw and error `ReferenceError: useranme is not defined`.

3. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  let username = "Arya";
}
console.log(useranme); // output
```

In above code we are looking for the variable `username`. There is not variable named `username` in the global scope. The variable `username` is inside a block. we can't access the variable `username` because we can't go inside another scope we can only bubble out to look for a variable.

The above code will throw and error `ReferenceError: useranme is not defined`.

4. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  var username = "Arya";
}
console.log(username); // output
```

In the above code we are looking for variable `username`. variable username is declared with `var` keyword inside `if` block and `var` is function scoped so we can use the variable `var` outside of `if` block.

output => Arya

5. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = "John";
if (true) {
  var username = "Arya";
}
console.log(useranme); // output
```

In the above code we are looking for variable `username`. There is one variable `username` in global scope which contain the value `Jhon`. Inside the block we are defining a variable with `var` keyword with the same name and we no that `var` is not block scope so it will throw an error.

output `Identifier 'username' has already been declared`

6. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = "John";
if (true) {
  let username = "Arya";
}
console.log(useranme); // output
```

In the above code we are looking for variable `username`. `username` contain value `Jhon` in global scope and inside `if` statement there is another variable called `username` which contain value `Arya` but these two variables are different because one is block scope and another is global scope. we are logging value for global scope so output will be `Jhon`.

7. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = "John";
function sayHello() {
  let username = "Arya";
}
sayHello();
console.log(useranme); // output
```

In the above code we are looking for variable `username`. `username` contain value `Jhon` in global scope and inside `function` there is another variable called `username` which contain value `Arya` but these two variables are different because one is function scope and another is global scope. when we run the program global execution context will be create and `username` will initialized with value `Jhon` and then function execution context will be create for sayHello function and inside function execution context memory other `username` variable will initialized with value `Arya` and once function execution is completed that execution context will be deleted and we have one `username` with value `jhon`.

we are logging value for global scope so output will be `Jhon`.

8. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (var i = 0; i < 10; i++) {
  console.log(i, "First"); // output
}
console.log(i, "Second"); // output
```

In the above code loop is runnig 10 times. so for first 10 value `i` value will be log. We know that `var` is function scoped but the above code there is block so we can use value of i outside of block so second output is value of `i` when it comes outside of loop.

9. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (let i = 0; i < 10; i++) {
  console.log(i, "First"); // output
}
console.log(i, "Second"); // output
```

we know that `let` is function and block scope so we can't use value of `i` outside of block so value `i` will be log when we are accessing `i` inside the loop. when we try to access the value of `i` outside of loop it will throw an error.
