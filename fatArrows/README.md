###Fat Arrow Functions

`Fat Arrow Functions` are a new way to write functions.


####Examples


This is how you would normally declare a function in ES5.

```

// works
function fn() {
  console.log('hello');
}
fn()

```

The below is a simple example of how the above function would be written in a **fat arrow function**.

```
var fn = () => {
  console.log('hello');
}
fn() // 'hello'

```

If the function only has one line of code, you can write the whole function in one line without curly braces. 

```
var fn = () => console.log('hello');

fn(); // 'hello'

```

Also, if the function is only one line you can remove the `return` keyword to return something.

```

// shortcut for return
var fn = () => 'Hello';

var hello = fn(); // captures the value w/o return
console.log(hello) // 'Hello'

```

You can also write a function as normal and return a value.

```

// using return
var fn = () => {
  let a = 2;
  let b = 3;
  return a + b;
}

console.log(fn()); // 5


```

You can add arguments within the paranteses.

```

// passing arguments
var fn = (a, b) => {
  return a + b;
}

console.log(fn(2, 3)); // 5


```

You can also pass arguments while writing a one line function and returning their value.

```
// you can also do this on one line
var fn = (a, b) => a + b;
console.log(fn(2, 3)); // 5

```

If you only have one argument you can ommit the paranteses. This only works with one argument, not with zero on more than one.

```
var fn = a => a + 8;
console.log(fn(2)); // 10

```

You can also use the **fat arrow function** as an annonymous function.

```
//passing an anonymous function
var fn = (value, callback) => callback(10);

fn(10, (num) => {
  console.log(num + 5); // 15
});

```

Here is another example using setTimeout.

```
setTimeout( () => console.log('hello'), 2000);

```


####Fat Arrows with this

The functionality of *this* changes with **fat arrow function**. When you call functions on their own `this` will refer to the `Window` scope. But in the example of `this` within a event handler, the `this` variable will change to the element it's called on with regular functions, while functions it will remain what this was originally (Window).

Most languages work in the way of the **fat arrow function**, it doesn't change what `this` in different uses. `this` is always the same. 


```
var button = document.querySelector('button');

function fn() {
  console.log(this); 
}

fn(); // Window object

var fn2 = () => console.log(this); 

fn2(); // Window object

button.addEventListener('click', fn); // Button Object
button.addEventListener('click', fn2); // Window Object


```