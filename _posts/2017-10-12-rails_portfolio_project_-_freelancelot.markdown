---
layout: post
title:      "Rails Portfolio Project - Freelancelot"
date:       2017-10-12 11:57:49 -0400
permalink:  rails_portfolio_project_-_freelancelot
---

When approaching this project differently from the Sinatra app, I wanted to create something that was relevant to my background in graphic design and my life in general as a freelancer. I asked myself "Would I use this? Is this helpful to other users?" At this point in the project I can finally answer these questions with a resounding "Yes!"

As with the Sinatra project, this process has been a fantasic learning experience. It also brought out things about myself that I needed to improve upon, which meant going back to Ruby basics and brush up on my foundations as the principles continue to be applied here. An ongoing problem I seem to have is object scope. I tend to lose track where class variables end up throughout the models, controllers, and views. By going through this process, I am confident now that I can learn to hone this in as time goes on. 

So what kind of features can you expect from Freelancelot?


![](https://img.memecdn.com/hey-freelance-artists_o_825620.gif)

* Choose from 2 Roles - Freelancer or Client

* Freelancers can create projects with many attributes and features such as:

      1. Title and Description
      2. Client/Company Name
      3. Ticket Number
      4. Start Date and Deadline
      5. Budget 
      6. Time log (hours spent on project can be updated)
      7. Status of project ("Received", "In Progress" or "Completed")
      8. Invoice sent to client? (Defaults to False)
* Freelancers have their own dashboard, which keeps track of their progress and alterts them if deadlines of thier projects are a week away or overdue.

* Clients can view the status of their project from their freelancer

* Clients can utilize the search feature to enter in their unique ticket number to instantly view their specified project from their freelancer

* Clients can view all projects by their category

The gems utilized in this project include Devise (Aides in User Registrations and Sign-in), Omniauth (Users can log in from 3rd party sites such as Facebook in this case) and Pundit (An authorization gem allowing me assign roles and easily delegating which type of users can use CRUD actions throughout the app).

Keep a look out for new features and the Rails/JS front-end transformation by following the repo:
https://github.com/SarahCyrDesign/freelancelot
