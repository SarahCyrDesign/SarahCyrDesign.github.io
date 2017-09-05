---
layout: post
title:  "Vineyard Companion Sinatra App"
date:   2017-09-05 17:53:37 +0000
---

![](http://www.terlatovineyards.com/sites/default/files/slideshow/vineyard-grapes-home-slideshow.jpg)

With the many possibilities for my Sinatra app to choose from, I decided on a Vineyard/Winery app that follows a User's wine tasting adventures and records their experiences. This app can be utilized in lieu of paper wine tasting lists that get lost over time.


This is done by:
* Adding a new Vineyard you visited with a name/location/phone number and review
* Adding new wines from your wine tasting and either associating them to an existing
vineyard or add a new vineyard in the same form
* Rate your wine by it's taste, scent, color, etc.

I first structured an outline and fleshed out how I wanted the views pages of the MVC to be laid out as well as structuring model relationships. The three models used are: **User, Vineyard, Wine**
* **User:** has_many :vineyards, has_many :wines
* **Vineyard:** belongs_to :user, has_many :wines
* **Wine:** belongs_to :user, belongs_to :vineyard

Next is was time to layout the controllers for each model in order to structure out the flow of the routes of my app.
Logically, the **users_controller** was the first to be worked on after the **application_controller** due to the factors of being logged in or not controlled the routes flow of the wines_controller and vineyards_controller. 

```
class UsersController < ApplicationController
  
	get '/signup' do
	
	end


  post '/signup' do

  end
	
	

  get '/login' do


  end
	
	
	
	post '/login' do
	
	end
	
	
	get '/users/:id' do
	
	end
	
	
	delete '/users/:id/delete' do
	
	end
	
	
	get '/logout' do
	
	end
	
end
```


Each controller inherits from the application_controller and the application_controller inherits from ActiveRecord in order to utilize CRUD actions within my app. A user can Create, Read, Update and Delete vineyards and wines as long as they are under their own account. There are also conditions within the controller methods to make sure users cannot adjust another user's wine or vineyard.

```
 @vineyard = Vineyard.find_by(name: params[:vineyard][:name], user_id: current_user.id)
        if @vineyard.nil?
          @wine.vineyard = Vineyard.new(params[:vineyard])
          @wine.vineyard.user_id = current_user.id
        else
          flash[:message] = "This vineyard already exists"
redirect to 'wines/new'
```

Finally, it was time to create the views in the MVC, where the html and ruby logic are rendered in their own erb pages. 
```
<h1>Welcome, <%=current_user.username%></h1>

<h2>Here are your Vineyards and Wines!</h2>

<%@user.vineyards.each do |vineyard|%>
<p>Vineyard: <a href="vineyards/<%= vineyard.id %>"><%= vineyard.name %></a></p>
<br>
<br>
<br>
<h2> Wines </h2>
<% vineyard.wines.each do |wine| %>
<p><a href="wines/<%= wine.id %>"><%= wine.name %></a></p>
<%end%>
<%end%>
```

There was so much I have learned from making this app and much more I can improve on in the future. Inbetween classes I plan on adding more features and improve on the CSS aethetic of the app as I move forward. Lastly, I plan on deploying the app on Heroku for many users to utilize.

Follow my project and keep a look out for more additions and refactoring!
[My repo for this project on GitHub](https://github.com/SarahCyrDesign/vineyard_companion)
