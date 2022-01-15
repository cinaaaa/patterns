# Prototype Pattern
#### Share properties among many objects of the same type
The prototype pattern is a useful way to share properties among many objects of the same type. 
The prototype is an object that's native to JavaScript, and can be accessed by objects through the prototype chain.

---
```js
class Dog {
  constructor(name) {
    this.name = name;
  }

  bark() {
    return `Woof!`;
  }
}

const dog1 = new Dog("Daisy");
const dog2 = new Dog("Max");
const dog3 = new Dog("Spot");

Dog.prototype.play = () => console.log("Playing now!");

dog1.play();
```
or we can create objects like this

```js
const dog = {
  bark() {
    return `Woof!`;
  }
};

const pet1 = Object.create(dog);
```
