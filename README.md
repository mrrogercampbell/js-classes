# Classes
When creating a application there are times when we might need to create many objects of the same kind. For example you might need to make many users, item listings, or even Pokemon. When faced with this kind of repetitiveness it is a perfect time to create a `Class`.

## Prerequisites
* Basic JavaScript Syntax
* Objects

## Objectives
By the end of this lesson developers should be able to:

* Define what a class and an instance

## What is a Class?
A `Class` in the context of JavaScript, is a programing-code-template for creating a type of `object` that allows us to define values and predetermined functionality or `functions`.

We know basic `functions` allow us to define blocks of code that are reusable. The limitation with functions is that we normally only create them do one specific thing like add two numbers together.

Lets say we want to create a application that allows us to battle pokemon. We could write 3 functions to control our pokemon:
```js
const battle = (attack) => {
    console.log(`The Pokemon attacks with ${attack} and does 5hp of damage`)
}

const eat = (berry) => {
    console.log(`The Pokemon eats a ${berry} berry and gains 10hp!`)
}

const sayHello = (name) => {
    console.log(`${name}!, ${name}!, ${name}! `)
}

battle('pounce')
eat('Oran')
sayHello('Gengar')
```

Our code above works and its pretty clean. But lets say we have a database with over 200 Pokemon and we need to be able to have them all battle at one. Do we really want to write out all that code for each Pokemon? Heck No!

## Class Syntax
So before we jump into converting our loose functions into a `Class` we need to understand the basic syntax of writing a `Class`. Let's continue with our Pokemon example:

```js
class Pokemon {
    constructor(name){
        this.name = name
    }
}
```
### The Constructor
The `constructor` is a method that is called automatically when a class is created. It is what allows us to pass in and define some required data for each `instance` of a class that we create.

Every Pokemon needs a name!

### this? Wait.. What?
`this` is just a way for the `Class` to identify itself. When we write `this.name` we are saying `Pokemon.name`.

### An Instance
An `Instance` is each Pokemon we want to create.

Let's see this in action. Lets say I want to create two new instances of a Pokemon class.
* The `first instance` should be for a Gengar Pokemon
* The `second instance` should be for a Machop Pokemon

```js
let firstPokemonInstance = new Pokemon("Gengar")
let secondPokemonInstance = new Pokemon("Machamp")

console.log(firstPokemonInstance)
console.log(secondPokemonInstance)
```
If you run the code snippet above you will see that each variable is storing a separate `instance` of a Pokemon class.

Each `instance` of the class has in turn stored the name we passed in as an `argument` to the `constructor` when we initialize it.
  * ie: created by defining a variable to store it inside of.

### Methods
`Methods` are just functions that you store inside of a `Class`. They allow you to predefine logical that you want every `instance` of your class to be able to do.

Lets move our loose functions into the Pokemon `Class`:

```js
class Pokemon {
    constructor(name){
        this.name = name
    }

    battle = (attack) => {
        console.log(`${this.name} attacks with ${attack} and does 5hp of damage`)
}

    eat = (berry) => {
        console.log(`${this.name} eats a ${berry} berry and gains 10hp!`)
}

    sayHello = () => {
        console.log(`${this.name}!, ${this.name}!, ${this.name}! `)
}
}


let gengar = new Pokemon("Gengar")
let machamp = new Pokemon("Machamp")

console.log(gengar)
console.log(machamp)

machamp.battle("Dynamic Punch")
machamp.eat('Oran')
machamp.sayHello()

gengar.battle("Shadow Ball")
gengar.eat('Oran')
gengar.sayHello()



```





