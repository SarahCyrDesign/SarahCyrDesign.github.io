---
layout: post
title:      "Rails and JS Front-end Project - Freelancelot"
date:       2017-11-28 00:38:49 +0000
permalink:  rails_and_js_front-end_project_-_freelancelot
---


Freelancelot has just gotten a facelift! For this project it was time to add more dynamic features to my current app by creating a fully functioning API. This is done by using jQuery and rendering JSON which aids in rendering content without a page load.

When deciding on which elements in my project to have dynamic features I needed to take into account what might be beneficial to the user. I narrowed down the 2 models to be converted, the Project model and Category model as they would both be equally utilized frequently throughout the app. 

- For Freelancers that log into their dashboard, they can quickly take glimpses into each of their project details without leaving the page.
- An Admin can add a new category and watch the name appear as each is created
- For admin and Clients that log in, they can view an index of projects under each category and also cycle through each category name with a 'next' button function. This is due to the model relationships where a category has many projects from the join model, project_category.

In the future, more dynamic features can be possible such as indexing projects from page to page when the list of overall projects grow further.

In the end, I have learned an immense amount of JavaScript principles and how much they differ from Ruby fundamentals. It was a great experience to mesh the two together in a cohesive mix of front-end and back-end functionality. They can work harmoniously together when Rails is in the mix as long as you make sure one end correctly communicates to the other...

![](https://i.makeagif.com/media/6-28-2015/AD8ARk.gif)

Be sure to follow my repo for Freelancelot for more features to come!
https://github.com/SarahCyrDesign/freelancelot
