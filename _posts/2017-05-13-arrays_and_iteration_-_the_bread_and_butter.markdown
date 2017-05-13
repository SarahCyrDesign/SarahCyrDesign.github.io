---
layout: post
title:  Arrays and Iteration - The Bread and Butter
date:   2017-05-13 14:52:56 +0000
---


Full steam ahead! It seems like the HTML and CSS lessons were over in a blink of an eye, but there was so much I gained. I had experience with HTML and CSS in the past, but these lessons went even more in depth than I could ever imagine. What helped me the most was understanding the "point system" when overwriting CSS rules and values also known as calculating CSS specificity value. I especially enjoyed the Star Wars spin on the point sytem [Star Wars Take on CSS specifity value](https://stuffandnonsense.co.uk/archives/css_specificity_wars.html).

At this time I am back on track with Procedural Ruby and am struggling to grasp the understanding of return values. *What does the method return once it is called versus what it is told to print on the screen* I have been automatically assuming to tell the computer to put or print to the screen that I have forgotten that the return value is just as important, especially when dealing with arrays.

I have learned how Arrays and iteration play an important role within Ruby as well as other languages. I admit that the present lessons on these have been a struggle for me to learn and solve the consequent problems. I am determined to ingrain the ability to manipulate Arrays, understand Iteration and most importantly, what they return. What better way to learn than to teach?
![](http://img.pandawhale.com/post-20396-Teach-funny-Cg1H.jpeg)

Let's say you have a dog adoption even that needs to assign a specific dog to a family. We need an array of dog names
```
adopted_dogs = ["Clifford", "Snoopy", "Odie"]
```
Happy news! It turns out that there is a family that wants to adopt for each dog. We want to document the happy news! In order to do this we need to iterate over the adopted_dogs and create a new array that assigns each dog to a family, which will be documented as a number in this case. We need to index the number according to what position each dog is in.

```
def assign_family(adopted_dogs)

end
```

*We pass the array of adopted_dogs as an argument in this method*

```
def assign_family(adopted_dogs)
new_family = []

new_family
end
```

*Next we need to create a new array to contain the information for the assigned family numbers as well as state the new array at the end of the code so the it can be a return value once the method is called*

```
def assign_family(adopted_dogs)
new_family = []
  adopted_dogs.each_with_index {|dog, family|}

new_family
end
```

*We will iterate over the array and take in each index according to the position each dog is in*

```
def assign_family(adopted_dogs)
new_family = []
  adopted_dogs.each_with_index {|dog, family| new_family.push}

new_family
end
```
*Time to collect this analyzed data from the iterarion and .push it onto our new array one by one*

```
def assign_family(adopted_dogs)
new_family = []
  adopted_dogs.each_with_index {|dog, family| new_family.push ("Congratulations #{dog}! You are adopted by family number #{family + 1}!") }
new_family
end
```

*Let's add a happy message to our array for each dog as well! Notice that we have to add 1 to our index or "family number" because arrays always start at 0*

**Congratulations Clifford! You are adopted by family number 1!**
**Congratulations Snoopy! You are adopted by family number 2!**
**Congratulations Odie! You are adopted by family number 3!**

By far for me arrays and iteration have been the biggest challenge in learning the Ruby language, but I can they will be one of the greatest tools in the future for me. Until next time!

