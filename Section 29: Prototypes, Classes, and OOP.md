# Prototypes, Classes, and OOP

## What Are Prototypes
In JavaScript, prototypes are a fundamental part of the language's object-oriented nature. Every object has a prototype, which is another object from which it can inherit properties and methods. This prototype-based inheritance allows for the creation of objects that share behavior without duplicating code. You can access an object's prototype using the `__proto__` property or the `Object.getPrototypeOf()` method.

```javascript
const animal = {
    speak() {
        console.log('Animal speaks');
    }
};

const dog = Object.create(animal);
dog.speak(); // Outputs: Animal speaks
```

## Introduction to OOP
Object-Oriented Programming (OOP) is a programming paradigm that uses "objects" to represent data and methods. OOP promotes code reusability, encapsulation, and abstraction. In JavaScript, OOP is implemented through prototypes and classes, allowing developers to create complex applications with organized and manageable code.

## Factory Functions
A factory function is a function that returns a new object each time it is called. This approach allows for the creation of multiple instances of an object without using the `new` keyword. Factory functions can encapsulate private data and provide methods to interact with that data.

```javascript
function createCar(make, model) {
    return {
        make,
        model,
        drive() {
            console.log(`Driving a ${this.make} ${this.model}`);
        }
    };
}

const car1 = createCar('Toyota', 'Corolla');
car1.drive(); // Outputs: Driving a Toyota Corolla
```

## Constructor Functions
Constructor functions are special functions used to create objects. They are defined with a capitalized name and are called with the `new` keyword. When invoked, they create a new object and set its prototype to the constructor's prototype.

```javascript
function Car(make, model) {
    this.make = make;
    this.model = model;
    this.drive = function() {
        console.log(`Driving a ${this.make} ${this.model}`);
    };
}

const car2 = new Car('Honda', 'Civic');
car2.drive(); // Outputs: Driving a Honda Civic
```

## JavaScript Classes
JavaScript ES6 introduced the `class` syntax, which provides a clearer and more concise way to create objects and handle inheritance. Classes are syntactical sugar over JavaScript's existing prototype-based inheritance.

```javascript
class Car {
    constructor(make, model) {
        this.make = make;
        this.model = model;
    }

    drive() {
        console.log(`Driving a ${this.make} ${this.model}`);
    }
}

const car3 = new Car('Ford', 'Mustang');
car3.drive(); // Outputs: Driving a Ford Mustang
```

## More Classes Practice
Classes can also include static methods, which are called on the class itself rather than on instances. This is useful for utility functions related to the class.

```javascript
class Car {
    constructor(make, model) {
        this.make = make;
        this.model = model;
    }

    drive() {
        console.log(`Driving a ${this.make} ${this.model}`);
    }

    static honk() {
        console.log('Honk! Honk!');
    }
}

Car.honk(); // Outputs: Honk! Honk!
```

## `extends` and `super` Keywords
The `extends` keyword allows a class to inherit from another class, enabling the creation of a class hierarchy. The `super` keyword is used to call the constructor of the parent class and access its methods.

```javascript
class Vehicle {
    constructor(make) {
        this.make = make;
    }

    start() {
        console.log(`${this.make} is starting`);
    }
}

class Car extends Vehicle {
    constructor(make, model) {
        super(make); // Calls the parent class constructor
        this.model = model;
    }

    drive() {
        console.log(`Driving a ${this.make} ${this.model}`);
    }
}

const car4 = new Car('Chevrolet', 'Camaro');
car4.start(); // Outputs: Chevrolet is starting
car4.drive(); // Outputs: Driving a Chevrolet Camaro
```
