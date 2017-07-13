---
layout: post
title:  "NES Collector CLI Gem"
date:   2017-07-13 12:06:56 -0400
---


My husband and I are avid retro game players and collectors which inspired me to create this project. What better way to show the love of retro gaming than to share with other potential collectors the values of Nintendo's beloved classic NES games!

![](https://media.giphy.com/media/O7k0gpm0dH6ik/giphy.gif)


Upon brainstorming this project, I at first wanted to obtain every retro game from the consoles of the Sega Genesis and SNES as well, but that soon became obvious that many layers of scraping had to be involved and lead me to simplify this project to a single console. This allowed me to focus more on the object classes instead of being too overwhelmed with segmenting every scraping detail. In the future, I would love to more versions of this gem belonging to the other consoles as a collection.

The first aspect I wanted to get working in the gem was making sure the look and feel of my CLI class was right for the user:
1. Greet the user with a title
2. Give menu options and a gets prompt 'List' or 'Exit'
3. If 'List' is chosen, a numbered list of NES games are shown
4. If the user decides to pick from the list of games, the chosen game with show the 3 values (loose, CIB, New)
5. The menu options are prompted after each choice for ease of use
6. Once 'Exit' is chosen a goodbye greeting is shown to the user


Next, it was time to start the Scraper class and get scraping! The website I have chosen for this is one of the most searched and used by me and my husband, www.pricecharting.com. The site had a table set up with all every game and was intuitively broken down by table rows and columns, making the scraping aspect much easier. There definitely should be credit given to those who built this site as everything was well organized and the Class/ID selectors were wonderfully labled.

```
class Scraper

  def scrape_page

  end

  def scrape_table

  end

   def make_games
   
	 end
```

I started scraping the whole page using Nokogiri and Open URI with the **scrape_page** method. We dig deeper into the document by scraping the table in the **scrape_table** method. Finally, we dig out each row and iterate over the rows in the **make_games** method. Once we optain the information on the *game's title, loose_price, cib_price and new_price*, it's time to pass the heavy lifting to the **Game class**! 

```
class Game

  attr_accessor :name, :loose_price, :cib_price, :new_price

  @@all = []

  def self.new_from_file(doc)
  
	end

  def initialize(name, loose_price, cib_price, new_price)
	
  end

  def self.all
	
  end

  def self.find(id)

  end
```

It was very easy to overcomplicate the Game class unecessarily at first. I wanted to find a game by name, find out the maximum price of all the games and so forth, but I quickly lost focus on what would be beneficial to the user first. Instead I focused of making sure the Game class worked with the Scraper class in order to list all the games and delve another layer deeper to the price properties. **The Each_with_index method** became a better way to showcase the games in the end. The best lesson I took away from building the Game class is how the **self.new_from_file method** established the object relationship between the Scraper class and the Game class.

This project has been a great challenge for me this month as I was intimidated from starting at a blank slate, but it truly has been a rewarding experience.

Follow my project and keep a look out for more additions and refactoring!
 [My repo for this project on GitHub](https://github.com/SarahCyrDesign/nes-collector-cli-gem)
