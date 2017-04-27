---
layout: post
title:  "Intro to Ruby Wrap-up"
date:   2017-04-27 10:05:44 -0400
---


This has been my 3rd week into the Online Developer Program and I have reached the end of the "Intro to Ruby" Course. The biggest challenge so far has been the continuation of building the Tic Tac Toe game. What I've learned from building the game in Ruby is how each method interacts with each other. As I learned the hard way, if one method with it's arguments doesn't mesh well with the rest, the game will not work. 
![](http://levelsave.com/wp-content/uploads/2014/01/this-game-is-broken-6.png)

Towards the end of the Ruby segment I was also introduced to Object Oriented Ruby versus the Procedural Ruby I have been working with from the beginning. From converting parts of the Tic Tac Toe from Procedural to Object Oriented I observed that the code feels more intuitive and readable without keeping track of many redundant arguments:


```
#Procedural Ruby

def full?(board)

  board.all? do |index|

    index == "X" || index == "O"

  end

end



def draw?(board)

  !won?(board) && full?(board)

end



#Versus Object Oriented Ruby

#first establish the class

class TicTacToe
  def initialize(board = nil)

    @board = board || board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]

end

def full?


  @board.all? do|index|

    index == "X" || index == "O"

  end

end


def draw?

  !won? && full?

end

```


*Notice how you don't need to repeat the argument "board" constantly with each method? look forward to learning more about Object Oriented Ruby down the line!*


The other night I finished the Version Control/Git/GitHub class relatively faster then I thought. I had some experience with the terminal, Git and GitHub before, but still need some fine tuning with branches and pull requests. I hope to apply these newfound skills very soon with future projects. Approaching week 4 soon and about to dive into some HTML and CSS, which I am very excited to revisit again!

**Class progress so far:
Intro to Ruby - 100%
Git/GitHub - 100%
Beginning HTML/CSS** 
