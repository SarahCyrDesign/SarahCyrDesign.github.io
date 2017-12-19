---
layout: post
title:      "Breaking Down the Lexical Scope and This"
date:       2017-12-19 20:05:42 +0000
permalink:  breaking_down_the_lexical_scope_and_this
---


Scope has been a difficult concept to wrap my head around when I first started to learn JavaScript and with more exposure and algorithm practice, it is becoming more clear little by little.  Let's start showing how lexical scope determines how your functions are executed:

```
var animal = "monkey";
function zoo() {
  var animal = lion;
  console.log(animal);
}

console.log(animal); //monkey
zoo(); // lion
```

In our zoo() function the scope of zoo() is nested inside the global scope hiding what gets defined inside it from the outer world. Looks like our clever monkey variable has escaped and the lion is kept inside the zoo().

Speaking of monkeys, lets gather a couple members of the Donkey Kong family and bring them into our next example:

![](https://thumbs.gfycat.com/LikelyGrippingHapuka-max-1mb.gif)

```
    const kong = 'Donkey Kong';
     
    function bonusBarrel () {
      function starBarrel () {
        console.log('Inside starBarrel()');
     
        console.log('kong is currently equal to:', kong);
      }
     
      const kong = 'Diddy Kong';
     
      starBarrel();
    }
```

So which kongs are going to shoot out of the different barrels?

```
bonusBarrel();
=> kong is currently equal to Diddy Kong
```

Since we declared starBarrel() inside bonusBarrel(), then starBarrel()'s reference to its outer scope points at bonusBarrel() instead of at the global scope. If we try to reference starBarrel() it will be undefined since it is a child of bonusBarrel().


# What is 'This?'
![](https://img.buzzfeed.com/buzzfeed-static/static/2013-10/enhanced/webdr02/14/13/anigif_enhanced-buzz-28458-1381772465-6.gif)

The first comparison I can make to JavaScript's keyword 'this' is 'self' from Ruby. In both cases, what 'this' or 'self' is referencing all depends on where it is located. A few simple guideliens to go by:

1-If 'this' is referenced directly inside a method, it equals the object that received the method call
2-Otherwise 'this' is global

```
let jackSkellington = {
  sing: function(){
    return this
  }
}
 
jackSkellington.sing() 
=> Object { sing: jackSkellington.sing() }
```


In the above example, 'this' is referening to Object of jackSkellington.

Let's try a nested function example:

```
let jackSkellington = {
  sing: function sing(){
   function playSanta(){
     return this
   }
   return playSanta()
  }
}
```
If we returned 'this' or jackSkellington.sing...
```
// window
```

When we  reference 'this' from functions and not methods it is not referenced from inside a method, it is global.

One more great example where 'this' comes in handy is through object-oriented JavaScript with Object Constructors and Prototypes!

```
function Dog(dog) {
  this.name = dog.name
  this.age = dog.age
  this.color = dog.color
  this.realColor = dog.color
  this.sound = dog.sound
}

Dog.prototype.playsInMud = function () {
  this.color = 'Dark Brown'
}

var dog = new Dog({ name: 'Fido', age: 10, color: 'Blue', sound: 'Wark' })

this.dog
=> { name: "Fido", age: 10, color: "Blue", realColor: "Blue", sound: "Wark" }

this.dog.playsInMud()

this.dog.color
=> "Dark Brown"
```

We now have access to the Dog object and it's properties while referencing 'this'!


