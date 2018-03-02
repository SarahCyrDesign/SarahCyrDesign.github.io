---
layout: post
title:      "Styling Vineyard Companion Sinatra App"
date:       2018-03-02 22:46:25 +0000
permalink:  styling_vineyard_companion_sinatra_app
---

I've been looking forward to styling the Vineyard Companion ever since creating the app in the Summer.  The best tool that comes to mind when styling a responsive layout is utilizing flexbox along with vanilla CSS. After finishing a comprehensive site map and moodboard, it was time to style the erb pages.

****Here we will take a look at the vineyard_companion/vineyards page:

With the help of codepen.io I was able to experiment with the page in real time utilizing this sandbox environment:

***Example of Vineyards page:***

https://codepen.io/sarahcyrdesign/pen/zRaMMO?editors=1100

**In the following example:**

*display: flex;* - Sets the container/div to be used with flexbox

*flex-direction: column;* -  Items are displayed vertically, as a column

*justify-content: center ;* - distributes items evenly along the axis

```
.top-img-container, .bottom-content, .top-img-container-vineyards {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```

To learn much more about flexbox, W3Schools provides a comprehensive guide with interactive examples: https://www.w3schools.com/css/css3_flexbox.asp

Be sure to follow my repo https://github.com/SarahCyrDesign/vineyard_companion as I continue to stylize the app and in the future deploy the finished product to Heroku.
