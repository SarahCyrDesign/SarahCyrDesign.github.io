---
layout: post
title:      "Prototypes and Object Constructors"
date:       2017-12-19 11:45:28 -0500
permalink:  prototypes_and_object_constructors
---


Continueing my discoveries of the ins and outs of JavaScript, I came across a deeper understanding of prototyping. As opposed to Ruby which realies more on classes for inheritance, Javascript prototyping is a more flexible object model. As an example, I will be using my cockatiel Sunny to give birth to our new object model and add prototyping functions for reuse. 


![](https://media1.tenor.com/images/d5a89f90496149b378656cbe596a294d/tenor.gif?itemid=4581095)


An object constructor is used for initializing new objects with attributes:


```
function Bird(bird) {
  this.name = bird.name
	this.breed = bird.breed
	this.mutation = bird.mutation
	this.age = bird.age
	this.currentFeathers = bird.currentFeathers
	this.mood = bird.mood
  this.sound = bird.sound
}
```

We set up the blueprints of the attributes we want our bird object to have. Now it's time to build some functions to utilize the attributes of the object. All inheritance in JavaScript is made possible with prototypes:

```
Bird.prototype.whistle = function() {
  return `${this.sound}! ${this.sound}`
}

 => Chirp! Chirp!
 
Bird.prototype.sayName = function () {
  return `${this.name}, chirp!`
}

=>Sunny, chirp!

Bird.prototype.molt = function () {
  this.currentFeathers = '5 feathers less'
}

Bird.prototype.hasBirthday = function () {
  this.age += 1
}
```

Observe the differences between the first 2 functions and the last 2...
When we teach sunny to whistle and say name, we are only telling him to return the current sound we are assigning him in the case that we initialize a new Sunny:

```
let bird = new Bird({ name: "Sunny", breed:  "Cockatiel", mutation: "Normal Grey", age:  6, currentFeathers: "Many Feathers", mood: "happy", sound: "Chirp" })
```

Once we call bird.hasBirthday(), Sunny will increment his age by 1:

```
bird.age
=> 6

bird.hasBirthday()

bird.age
=> 7
```

And when it is time for Sunny's quarterly molting, his feathers will be updates

```
bird.currentFeathers
=> "Many feathers"

bird.molt()

bird.currentFeathers
=> "5 feathers less"
```

Now it is even more clearer to see how straightforward object inheritance is in JavaScript and the way we can teach objects to do things and update their own attributes when necessary.
