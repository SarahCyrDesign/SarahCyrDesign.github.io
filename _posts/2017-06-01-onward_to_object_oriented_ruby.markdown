---
layout: post
title:  Onward to Object Oriented Ruby!
date:   2017-06-01 15:28:29 +0000
---

![](https://media1.giphy.com/media/LHZyixOnHwDDy/giphy.gif)


Huzzah! This month I have completed the Procedural Ruby lessons and labs with a new profound understanding of the Iteration method. I have a feeling I will be needing to use it more and more as my coding journey moves forward.

**Next stop, Object Oriented Ruby!**

At this point in the program it is time to think in abstract terms and metaphors when it comes to OO Ruby. A "class", for instance, is a blueprint that has the instructions for creating new objects. Objects can be named anything you want, but in order to reflect the method you are working in, it is better to name after real world objects for now for the sake of readability. 


```
class Dog
end

fido = Dog.new
#<Dog:0x10fa31b68>
```


We can create new objects or "Instantiate", therefore creating an instance of an object (fido). Each object is unique! We can also create instance methods to teach our objects new things!


```
class Dog
def bark
  puts "Woof!"
	  end
	end 
	
	fido = Dog.new
	#<Dog:0x10fa31b68>
	
	fido.bark
	#"Woof!"
```


Instance variables are accessible in any instance method and are recognized by the "@" before it. This way, we don't need to pass arguments as other local variables need to.

Instance classes can also have properties and the "getter" and "setter" methods define what those properties are. Through abstraction we can either separate the two methods through:


```
attr_reader :name, :breed
attr_writer :collar_color, :owner
```

...or we can combine the getter and setter into one!


```
attr_accessor :collar_color, :owner
```


Let's say that as soon as we create an instance of a new dog, we want it to be born and automatically assign it with a name and a breed. We can do that by using the initialize method.


```
class Dog

attr_reader :name, :breed
attr_accessor :collar_color, :owner

def initialize(name, breed)
  @name = name
	@breed = breed
end

def collar(color)
  self.collar_color = color
end

def get_adopted(owner_name)
  self.owner = owner_name
end

def bark
  puts "Woof!"
	  end
	end 
	
	fido = Dog.new("Fido", "Basset Hound")
	#<Dog:0x10fa31b68 @breed="Basset Hound", @name="Fido">
	
	fido.name
	#"Fido"
	
	fido.bark
	#"Woof!"
	
	fido.breed
	#"Basset Hound"
	
	fido.get_adopted("Sarah")
  #"Sarah"
  
	fido.owner
  #"Sarah"
        
  fido.collar("Green")
  #"Green"
	
  fido.collar_color
  #"Green"
```

Now Fido will be born with a name and breed, can bark and remember these things through dot notation (.) We also later assigned Fido his new owner and collar color through the methods and the attr_accessor, so what if we changed our mind about the collar color?


```
fido.collar("Blue studded")
#"Blue studded"

fido.collar_color
#"Blue studded"
```


**That's right! Thanks to the attr_accessor assignment, we can change the properties of objects as well!**

![](https://www.dogbreedinfo.com/images24/BassetHoundMollyPurebredDog.jpg)

So that is a sample of the start of OO Ruby. I can't wait to share with all of you my first project once I near the end of this segment and make my way towards Scraping!


