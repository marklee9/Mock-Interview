# Javascript Trivia

<br/>
<br/>

What is difference between `null` and `undefined`
    
    Undefined: value of the variable is not defined.
    Null: empty or non-existent value which is used by programmers to indicate “no value”
<br/>

___

<br/>

== vs ===

    The simplest way of saying that, == will not check types 
    and === will check whether both sides are of same type. 

    So, == is tolerant. But under the hood it converts to 
    its convenient type to have both in same type and then do the comparison.

<br/>

___

<br/>

What is hoisting in Javascript?

    Hoisting is a JavaScript mechanism where variables and function declarations
    are moved to the top of their scope before code execution.

<br/>

___

<br/>

is `let`, `const`, `var` hoisted?

    Partially. Declaration is hoisted, but Expression is not hoisted.

<br/>

___

<br/>


What is the Temporal Dead Zone?

    This has to do with the topic of hoisting. 
    The temporal dead zone is the time between entering a scope where
    a variable is declared (i.e. an if statement or while loop), and 
    the actual declaration and initialization of that variable. 
    During this period, let and const variables cannot be accessed 
    (you will get a Reference Error), even though they have been hoisted.

<br/>

___

<br/>

Function Expression vs. Function Declaration.

    Function Expression is created when the execution reaches it and 
    only usable after that. `Not Hoisted`.

    Function Declaration is can be called before and after execution 
    reaches it. `Hoisted`.

<br/>

___

<br/>

What is closure in Javascript? Can you give me an example?

    In Javascript, functions are not just functions, but also closures.

    That means the function body has access to variables defined 
    outside the function.

```js
const name = "Mark";

function sayHi() {
  console.log(`Hi ${name}!`);
  // although name is defined outside of this function. It still has access to `name` variable.
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
Explanation:

    The console log is inside the anonymous function of setTimeout 
    and setTimeout is executed when current call stack is over. 

    So, the loop finishes and before setTimeout get the chance to execute.
    However, anonymous functions keep a reference to i by creating a closure.

    Since, the loop is already finished, the value i has been set to 10. 
    When setTimeout use the value of i by reference,
    it gets the value of i as 10. Hence, you see 10 ten times.

What will happen if you change `var` to `let`?

    It will print 1,2,3... after 1 second.
    Because `let` gives you the ability to declare a block scope local variable.

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

    Variables inside a function can be mutated, but will not be reassigned.

<br/>

___

<br/>

What is event loop?

    Event loop is a mechanism that constantly checks if the call stack if empty.
    When the call stack is empty then it will take the first item in the task queue and push it into the call stack.


<br/>

___

<br/>

What is namespace?

    Namespacing does for functions and classes what scope does for variables. 
    It allows you to use the same function or class name in different parts of the
    same program without causing a name collision.

    
<br/>

___

<br/>

Tell me few ways to do Prototypal Inheritance.

```js
// Will effect the performance, mutate object's prototype.
Object.setPrototypeOf(Dog.prototype, Animal.prototype)

// Better way.
Dog.prototype = Object.create(Animal.prototype);

// Old way.
function Surrogate () {};
Surrogate.prototype = Animal.prototype;
Dog.prototype = new Surrogate();
Dog.prototype.constructor = Dog; 
```
    
<br/>

___

<br/>



<br/>

___

<br/>