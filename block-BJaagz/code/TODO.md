1. Implement `forEach` array method using Array.reduce

- `forEach` accepts two parameter array and callback
- It does not return anything
- It should work exactly like array `forEach` method

```js
function forEach(arr, cb) {
  arr.reduce((acc, cur, index) => {
    cb(cur, index, arr)
    return acc;
  }, 0)
}

forEach(['Sam', 'Jon', 'Arya'], (name, i, arr) =>
  console.log(name + name, i, arr)
);
```

2. Implement `map` array method using Array.reduce

- `map` accepts two parameter array and callback
- It returns same size of array
- It should work exactly like array `map` method

```js
function map(arr, cb) {
  // Your code goes here
  return arr.reduce((acc, cur) => {
    acc.push(cb(cur))
    return acc;
  }, [])
}

map(['Sam', 'Jon', 'Arya'], (name) => name + name); // ['SamSam', 'JonJon', 'AryaArya']
```

3. Implement `filter` array method using Array.reduce

- `filter` accepts two parameter array and callback
- It returns same size or smaller array
- It should work exactly like array `filter` method

```js
function filter(arr, cb) {
  // Your code goes here
  return arr.reduce((acc, cur) => {
    if(cb(cur)) {
      acc.push(cur)
    }
    return acc;
  }, [])
}
filter(['Sam', 'Jon', 'Arya'], (name) =>
  name.startsWith('S')
); // ['Sam']
```
