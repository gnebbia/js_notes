# Objects


## Create new types of objects

In order to create new types of objects we need constructor functions
that can be called with the `new` operator.

Notice that it is a convention to call constructor function
with a starting uppercase letter. Let's see an example:
```javascript

function Car(id) {
    this.carId = id;
    this.start = function() {
        console.log('start: ' + this.carId);
    };
};

// instantiation
let car = new Car(123);

// method call
car.start();
```

## Prototypes



## Destructuring Objects

The same thing can be applied to objects:
```javascript
let car = { id: 5000, style: 'convertible' };
let { id, style } = car;
```
