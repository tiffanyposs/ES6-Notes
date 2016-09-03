###let

`let` allows you to **block scope** within if statements, while loops, and for loops. The variable will be scoped within these statements and loops. It's just another way to to declare a variable.

This shows how `age` is available inside the if statement but not outside. 

```
  if(true) {
    let age = 28;
    console.log(age) // 28
  }

  console.log(age); // not defined, error

```

Declaring a `let` variable twice. They are scoped differently.

```
  let hello = 'hello';

  if(true) {
    let hello = 'hi';
    console.log(hello); // "hi" 
  }

  console.log(hello); // "hello"

```

Below with `var` you still had access to the `i` variable, which outside of the for loop ends up being 11

```
  for(var i = 0; i <= 10; i++) {
    console.log(i); // 0 through 10
  }

  console.log(i); // 11

```

If you use `let`, `i` is throws an error outside of the *for* loop.

```
  for(let i = 0; i <= 10; i++) {
    console.log(i); // 0 through 10
  }

console.log(i); // not defined, error

```


###const

`const` is another way to declare a variable, but it stands for *constant*. This means once you define this variable you cannot change it to a new value. This is to set variable that you intend to never change in value. Maybe an api key would be a good example of a use case. Also, it's common to put `const` variable in all uppercase. 

Below when you try to change the value of the `AGE` variable it errors because *const* only allows you to set the variable one time. 

```
  const AGE = 28;
  AGE = 29; // error, code stops running
  console.log(age);

```

You can see below though we can modify an array to a certain extent. It allows us to push additional objects into the `const` array, but it won't let us assign a new version of it in a new spot in memory. This is because we can modify the value, we just can't reassign it to a new value (new place in memory)

```
  const AGES = [27, 28, 29];
  console.log(AGES); // [27, 28, 29]

  AGES.push(30);
  console.log(AGES); // [27, 28, 29, 30]

  AGES = [30, 31, 32]; // error

```

You can also modify the original values.


```
  const ARRAY = [1, 2, 3];
  console.log(ARRAY);

  ARRAY[0] = 10;

  console.log(ARRAY);

```
It will error if you modify a number or sting value;

```
  const FIVE = 5;
  FIVE++; // error
  
  console.log(FIVE);

```


###Hoisting

Hoisting is a little different with the `let`. You must declare the variable before you define it. 


With `var` you could set a value then declare the variable later. Hoisting with `var` allows you to do that. 

```
  age = 27;
  console.log(age); // 27

  var age;

```

Below with let it would error. 

```
  age = 27;
  console.log(age); // age is not defined

  let age;

```

The below would not error because it's defined before the function is called.


```
function doStuff() {
  age = 27
}

let age;
doStuff();
console.log(age); // 27

```