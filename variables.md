# Variables

We have two ways, `let` and `var`, in general
`let` is the new way of declaring variables, and we should
avoid using `var`.

Note that `let` is block scoped, while `var` is function scoped.

```javascript
let total = 149.99;
let product = 'Hikin Boots';
let discounted = true;
```

We can also declare multiple variables with:
```javascript
let price = 49.99,
    name= 'hiking boots',
    discounted = false;
```

Some rules for variable naming:
- in general the camelCase (e.g., `accountNumber`) notation is used for variables;
- private variables often start with underscore (e.g., `_accountNumber`);
- automatic generated code variables start with a dollar sign (e..g, `$accountNumber`);


# Constants

When we declare a constant we must initialize it with a value.
```javascript
const price = 40;
```



# Best Practices

## Use Variables only when there is a real need

In general, when in doubt we should create new data as constants and then
change it back as variable only if needed.
As a best practice, indeed, if a variable is not going to change, it should
be declared as a constant.

## Don't use var

In old javascript var was used in place of const and let, anyway,
nowadays avoiding var is a best practice.

The problem with var is that it makes our program behave strangely
by not giving us errors if a variable is undeclared.
For example, the following code is correct:
```javascript
console.log(price)
var price = 40 
```
And prints "undefined", while the same code with `let` will give us an error
indicating that the variable `price` does not exist.
