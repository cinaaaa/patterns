# Singleton Pattern
#### Share a single global instance throughout our application
#### Singletons are classes which can be instantiated once, and can be accessed globally.
-----
- a getInstance method that returns the value of the instance
- a getCount method that returns the current value of the counter variable
- an increment method that increments the value of counter by one
- a decrement method that decrements the value of counter by one
-----
### How to create
```js
let instance;
let counter = 0;

class Counter {
  constructor() {
    if (instance) {
      throw new Error("You can only create one instance!");
    }
    instance = this;
  }

  getInstance() {
    return this;
  }

  getCount() {
    return counter;
  }

  increment() {
    return ++counter;
  }

  decrement() {
    return --counter;
  }
}

const singletonCounter = Object.freeze(new Counter());
export default singletonCounter;
```
