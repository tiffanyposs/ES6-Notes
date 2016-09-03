###Fat Arrow Functions



```

// works
function fn() {
  console.log('hello');
}
fn()

```

```
// works
var fn = () => {
  console.log('hello');
}
fn() // 'hello'

```

```

// works
var fn = () => console.log('hello');

fn(); // 'hello'

```

```

// shortcut for return
var fn = () => 'Hello';

var hello = fn(); // captures the value w/o return
console.log(hello) // 'Hello'

```

```

// using return
var fn = () => {
  let a = 2;
  let b = 3;
  return a + b;
}

console.log(fn()); // 5


```

```

// passing arguments
var fn = (a, b) => {
  return a + b;
}

console.log(fn(2, 3)); // 5


```

```

// you can also do this on one line
var fn = (a, b) => a + b;
console.log(fn(2, 3)); // 5

```

```

// if you only have on argument you can remove the paranteses.
// if you have no arguments or more than one you need paranteses.
var fn = a => a + 8;
console.log(fn(2)); // 10

```

```

//passing an anonymous function
var fn = (value, callback) => callback(10);

fn(10, (num) => {
  console.log(num + 5); // 15
});


```

```


setTimeout( ()=> console.log('hello'), 2000);


```