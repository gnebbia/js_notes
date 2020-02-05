# Functions 


Two common ways to define functions are:
- function declaration/definition/statement `function name() { ... }`
- function expression `let fn = function name() { ... }`

Notice that it is a best practice to give the function
expression a name although we can avoid it.
This will be helpful for debugging purposes.

Notice that simple data types such as numbers, booleans, strings and so on
are by default passed by value, while objects are passed to functions
by reference.

This means that we can actually modify objects inside functions without
getting a copy and returning them.

```javascript
function increaseAge(p) {
    p.age++;
}

person = {
    age: 29,
    name: "joe"
}

increaseAge(person)
console.log(person.age) // prints 30
```

We can also have default parameters.
```javascript
let trackCar = function(carId, city="Rome") {
    return "random stuff";
}
```

Notice that functions in javascript make use of **Hoisting**, this means
that we can use them before declaring them.
So we can put their definition for example at the bottom of the file
and use them at the beginning.

Hoisting is available also for variables if we use the `var` keyword
for defining variables, but this is discouraged, and we should
always avoid hoisting for variables in javascript.

## Rest Parameters

We can have functions accepting a varying number of parameters with:
```javascript
function sendMessages(...allMsgs){
    allMsgs.forEach( id => console.log(id));
}
sendMessages("ciao","hello","how are you?');
```


Notice that rest parameters must be last if we want to mix it with other
parameters, for example:
```javascript
function sendMessages(day, ...allMsgs){
    console.log("Today is ", day);
    allMsgs.forEach( id => console.log(id));
}
sendMessages("Monday", "ciao","hello","how are you?');
```

## IIFE

IIFE (Immediately Invoked Function Expressions) are a way in javascript
to immediately call newly defined functions.
```javascript
(function (){
    console.log("Hello");
})();

// or 
let app = (function (){
    console.log("Hello");
})();

app();
```

We can also return objects:
```javascript
let app = (function (){
    console.log("Hello");
    return {};
})();

let retValue = app();
```

## Closures

An example of closure:
```javascript
let app = (function(){
    let carId = 123;
    let getId = function() {
        return carId;
    };
    return {
        getId: getId
    };
})();

console.log( app.getId() );
```

## Call, Apply and Bind

We can assign functions related to certain objects
to other objects by using call, apply and bind.
Examples:
```javascript
let o = {
    carId: 123,
    getId: function() {
        return this.carId;
    }
};

let newCar = { carId: 456 };
console.log( o.getId.call(newCar) ); //456
```

Note that call is quite limited in the sense that does not
allow to pass parameters in case of parameterized functions,
we can solve this problem by using `apply`:
```javascript
let o = {
    carId: 123,
    getId: function(prefix) {
        return prefix + this.carId;
    }
};

let newCar = { carId: 456 };
// note that the parameters are passed inside an array
console.log( o.getId.apply(newCar, ['the ID is: ']) ); // the ID is: 456
```

Bind is also similar to call and apply, but allows the creation of a new
function, for example:
```javascript
let o = {
    carId: 123,
    getId: function() {
        return carId
    }
};

let newCar = { carId: 456 };
// note that the parameters are passed inside an array
let newFn = o.getId.bind(newCar); 
console.log( newFn() ); // 456
```


## Arrow Functions

In ES6 we can declare function in a more concise way by using the
arrow function notation. Let's see some examples:
```javascript
let getId = () => 123;

//note that sometimes to mean the same thing we may see instead of `()`
// the underscore `_`, for example
// let getId = _ => 123;
console.log( getId() ); // 123
```

Let's see an example with a parameter:
```javascript
let getId = prefix => prefix + 123;
console.log( getId('ID: ') ); //ID: 123
```

If an arrow function has more than one parameter we should add
some round braces, for example:
```javascript
let getId = (prefix, suffix) => prefix + 123 + suffix;
console.log( getId('ID: ', '!') ); // ID: 123!
```

Sometimes we need a more complex function body, in this case
we can add curly braces to the body in this way:
```javascript
let getId = (prefix, suffix) => {
    prefix = prefix.toUpperCase();
    suffix = suffix.toUpperCase();
    return prefix + 123 + suffix;
} 
console.log( getId('id: ', '! end') ); // ID: 123! END
```
