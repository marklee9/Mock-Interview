# Javascript Trivia

<br/>
<br/>

What is difference between `null` and `undefined`
    
    Undefined: value of the variable is not defined.

    Null: empty or non-existent value which is used by programmers to indicate “no value”


What is closure in Javascript? Can you give me an example?

    In Javascript, functions are not just functions, but also closures. That means the function body has access to variables defined outside the function.

```js
const name = "Mark";

function sayHi() {
  console.log(`Hi ${name}!`);
}

sayHi(); //=> Hi Mark!
```
<br/>

___

<br/>


What will happen if you run the following code.

```js
for(var i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(i);  
  }, 1000);
}

The above will not output the numbers 0 through 9, but will simply print the number 10 ten times.
```
Explanation

    The console log is inside the anonymous function of setTimeout and setTimeout is executed when current call stack is over. So, the loop finishes and before setTimeout get the chance to execute. However, anonymous functions keep a reference to i by creating a closure. Since, the loop is already finished, the value i has been set to 10. When setTimeout use the value of i by reference, it gets the value of i as 10. Hence, you see 10 ten times.

What will happen if you change `var` to `let`?

    It will print 1,2,3... after 1 second.

What if I want to print out increasing number every second?

```js
for(let i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(i);  
  }, 1000 * i);
}

```

<br/>

___

<br/>

Explain what will happen to the following code :

```js
let one = 1;
let obj1 = {value: 100};
let obj2 = {value: 200};
let obj3 = obj2;

function change(one, obj1, obj2) {
  one = 10;
  obj1 = obj2;
  console.log(obj1); //=> {value: 200}

  obj2.value = 0;
}
change(one, obj1, obj2);

console.log(one); //=> 1
console.log(obj1); //=> {value: 100}
console.log(obj2); //=> {value: 0}
console.log(obj3); //=> {value: 0}
```
    Primitive are passed by values, and objects are passed by reference.

    values inside a function can be mutated, but will not be reassigned.

<br/>

___

<br/>




    