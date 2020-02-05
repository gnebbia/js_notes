# Arrays

We have the whole docs about arrays on mozilla docs in the section
related to javascript global objects.

## Array Creation
```javascript
// array creation/initialization
let values = [1, 2, 3];
const values = [1, 2, 3];
```
or
```javascript
// alternative array creation/initialization
let values = Array.of(1, 2, 3);
const values = Array.of(1, 2, 3);
```

```javascript
// Check if data is an array
Array.isArray(values)
```


## Accessing Array Elements

Let's see other array related snippets of code:
```javascript
let values = [1, 2, 3];
console.log(values[0]); // prints 1
values[0] = 'ABC';
console.log(values[0]); // prints ABC
```

We can search and loop in arrays in the following ways:
```javascript
const values = [ 'a', 'b', 'c' ];
console.log(values.indexOf('c')); // 2
console.log(values.indexOf('d')); // -1 because it does not exist
```

Let's see a filter:
```javascript
const values = [ 'a', 'b', 'c' ];
const set = values.filter(function(item) {
    return item > 'b';
});
console.log(set); //c
```
Let's see how to find elements:
```javascript
const values = [ 'a', 'bbb', 'c' ];
// find function will return once it is true
const set = values.find(function(item) {
    return item.length > 1;
});
console.log(set); // bbb
```

We can execute a function for each element of an array
with `forEach`, by doing:
```javascript
const values = [ 'a', 'b', 'c' ];
// find function will return once it is true
values.forEach(function(item) {
    console.log(item);
});
// prints a b c
```




## Manipulating Arrays

We can work with arrays by:
- appending values to end of array  `push`;
- removing values from end of array `pop`;
- inserting values at the beginning of array `unshift`;
- removing values from the beginning of array `shift`;
- work in the middle of the array `slice` and `splice`;

```javascript
const values = ['a','b','c'];

values.push('d');
console.log(values); // prints a b c d


const last = values.pop()
console.log(last); //prints d

console.log(values); //prints a b c

// we can also work with the beginning of the array
const first = values.shift() //first is 'a'

// we can also unshift to insert values at the beginning of the array
const values = ['b','c'];
values.unshift('a');
console.log(values); // prints a b c
```

Notice that we can also perform these operations on multiple values,
for example:
```javascript
const values = ['a','b','c'];

values.push('d','e','f');
console.log(values); // prints a b c d e f
```

We can work with the middle of an array by using `slice` and `splice`.

```javascript
const values = ['a','b','c'];
const newValues = values.slice(1,2);
// the first element is the index from which we will start the selection
// the second argument the last index of selection (which will excluded)
console.log(newValues); //b
```

We can remove middle elements by using `splice`:
```javascript
const values = ['a','b','c'];
values.splice(1,1);
// the first element is the index from which we will start the deletion
// the second argument is how many elements we want to delete
console.log(values); // a c
```

We can also insert elements in the middle with `splice`:
```javascript
const values = ['a','b','c'];
values.splice(1,0,'myValue');
// the first element is the index from which we will start the deletion
// the second argument is how many elements we want to delete, in this
// case since it is zero, it means we will not delete but add a value
console.log(newValues); // a b myValue c
```

Or substitute elements in the middle
```javascript
const values = ['a','b','c'];
values.splice(1,1,'myValue');
// the first element is the index from which we will start the deletion
// the second argument is how many elements we want to delete, in this
// case since it is zero, it means we will make a substitution
console.log(newValues); // a myValue c
```


## Destructuring Arrays

We can perform cool assignments with array using destructure of arrays,
for example:
```javascript
let carIds = [1, 2, 5];
let [car1, car2, car3] = carIds;
// or 
let car1, remainingCar;
[car1, ... remainingCar] = carIds;
```

We can also skip elements by doing:
```javascript
[,, ... remainingCar] = carIds;
// here we skipped the first two elements, we can put how many commas we want
```

## Spread Syntax

We can use the dotdotdot notation also to expand arrays into
single values, to pass values to function:
```javascript
function startCars(car1, car2, car3){
    ...
}

let carIds = [100, 200, 300]; // if we have a string, each element is a char
startCars(...carIds);
```
