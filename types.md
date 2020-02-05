# Types

Each variable has a type, the standard types are:
- Numbers
- Strings
- Booleans
- null/undefined
- Objects
- Symbols


We can show the type of data by using the builtin `typeof` function:
```javascript
typeof(19.99)   // number
typeof("hello") // string
typeof "ciao"   // string
```

## Numbers

Numbers don't have anything special, we have the same operators
seen in other common programming languages, we also have
shortcuts for assignements like `+=` or `-=` and so on.
We also have prefix and postfix value changes like `data++`
or `++data`.


## Strings

We have different ways to write strings, like:
```javascript
let message = "hello world"
let message2 = 'hello world'
let message3 = "hello \"world\"" //we should escape some characters for proper printing
```

We can also get variable interpolation and heredocs by using backticks \`\`.
Note that backticks also delete all newlines/tabs and multiple spaces
to a single space when we are working with some HTML tags.
```javascript
let name = "Anna"
let message = `Hello ${name}


How are you?
`
// This will show a multiline string on a js console but a single
// line string in a h1 HTML tag, like:
// Hello Anna How are you?
```

## null/undefined

The difference between null and undefined is:
- `undefined` is used by javascript when it doesn't know that variable
  (e.g., the variable does not exist);
- `null` is used by the programmer to wipe out the value from a data container;


Anyway this is a best practice, indeed, a developer could set a variable
to `undefined` but this is a bad practice, since would make life to 
other programmers harder when debugging.

So in genera, if we want to wipe out a variable, we should use `null` and
let `undefined` usage to the interpreter only.

## Objects

Let's see the basics of objects with some code snippet:
```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    // `this` is used to access properties of the object
    showInfo: function () {
        console.log(this.firstName + " " + this.lastName);
    }
    age: 33
};

// We can either use:
// the Dot Notation
person.age = 35;

// the Square Brackets Notation
person['age'] = 35

// method call
person.showInfo();

console.log(person.age); //prints 35
```

## Symbols

Symbols can be used as properties inside objects, but they are hidden.
There are times when we want to hide information about an object, so
in these cases we can use symbols.

```javascript
let mySymbol = Symbol(); // definition of a new symbol
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 33,
    [mySymbol]: 'secretinformation',
};
```

In this way we hide this information so that other users cannot access
`mySymbol`.
