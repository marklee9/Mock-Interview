# Javascript Trivia

<br/>
<br/>

<br/>

___

<br/>

Explain event delegation.

        Event delegation is a technique involving adding event listeners to a parent element instead of adding them to the descendant elements.
        The listener will fire whenever the event is triggered on the descendant elements due to event bubbling up the DOM. The benefits of this technique are:

<br/>

___

<br/>

What is `this` in Javascript?

        The value of this is usually determined by a functions execution
        context. Execution context simply means how a function is called.


What is difference between `null` and `undefined`
    
        Undefined: value of the variable is not defined.

        Null: empty or non-existent value which is used by programmers to indicate “no value”
<br/>

___

<br/>

What does bind do?

        The bind method creates a new function that, when called, has its this keyword set to the first parameter passed into it. 
        All subsequent parameters are arguments for that bound function.
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

Tell me about coercion in JavaScript.

        In JavaScript, falsy values can be implicitly coerced to `false`, and truthy values can be coerced to to `true`.

        Strings and Numbers can also be coerced with mathematical operation.

<br/>

___

<br/>

String and Number Coercion.

        + operator can be used for both string and number, but any other
        operators are exclusively for numeric operations. When those operators are used with Strings, the Strings will be coerced into a number.


```js
1 + "2" = "12"
"" + 1 + 0 = "10"
"" - 1 + 0 = -1
"-9\n" + 5 = "-9\n5"
"-9\n" - 5 = -14
"2" * "3" = 6
4 + 5 + "px" = "9px"
"$" + 4 + 5 = "$45"
"4" - 2 = 2
```
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

What is the significance of including `use strict` at the beginning of Javascript source file.

        "use strict" is a way to voluntarily enforce stricter parsing and error handling on your JavaScript code at runtime.

        Makes debugging easier.
        Code errors that would otherwise have been ignored or would have failed silently will now generate errors or throw exceptions, 
        alerting you sooner to problems in your code and directing you more quickly to their source.

        Prevents accidental globals.
        Without strict mode, assigning a value to an undeclared variable automatically creates a global variable with that name.
        This is one of the most common errors in JavaScript. In strict mode, attempting to do so throws an error.

        Eliminates this coercion. 
        Without strict mode, a reference to a this value of null or undefined is automatically coerced to the global. 
        This can cause many head fakes and pull-out-your-hair kind of bugs. In strict mode,referencing a this value of null or undefined throws an error.

        Disallows duplicate parameter values.
        Strict mode throws an error when it detects a duplicate named argument for a function (e.g., function foo(val1, val2, val1){}),
        thereby catching what is almost certainly a bug in your code that you might otherwise have wasted lots of time tracking down.

        Makes eval() safer.
        There are some differences in the way eval() behaves in strict mode and in non-strict mode. 
        Most significantly, in strict mode, variables and functions declared inside of an eval() statement are not created in the 
        containing scope (they are created in the containing scope in non-strict mode, which can also be a common source of problems).

        Throws error on invalid usage of delete.
        The delete operator (used to remove properties from objects) cannot be used on non-configurable properties of the object. 
        Non-strict code will fail silently when an attempt is made to delete a non-configurable property, whereas strict mode will throw an error in such a case.
<br/>

___

<br/>

What is the potential pitfall of using `typeof bar === Object` to determine if the bar is an object?

        The downfall is that `null` and `array` will also return Object.

<br/>

___

<br/>


Explain how prototypal inheritance works.

        In JavaScript, objects have a special internal and hidden property called prototype.

        When we read a property from an object and it is missing, it will look its prototype and see if that property exist in the prototype.

        If it doesn't exist in prototype it will traverse through the prototypal chain
        with __proto__. __proto__ looks up the prototype of the constructor function that 
        constructed the object. It will keep traverse through the prototypal chain
        to find the property.

<br/>

___

<br/>