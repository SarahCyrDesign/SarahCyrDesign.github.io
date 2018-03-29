---
layout: post
title:      "Into to Sass: Variables"
date:       2018-03-29 14:54:32 +0000
permalink:  into_to_sass_variables
---


As we know, programmers are lazy and only want to write functional cade one time to use across various programs. What better way to utilize this than to have Sass take care of the work for us - **Introducing Variables **


Variables are a familiar concept to those who have delved in JavaScript or most programming languages. We can store information and assign an identifier to a specific value. This identifier can be used across your whole style sheet, cutting down the amount of repeated code. Also by doing this, you can change multiple rules. 


$ is used to define and receive a variable

```
$translucent-white: rgba(255, 255, 255, 0.3);
```


Just as global variables in CSS should be declared at the top so should your variables.
Thay can then be referenced inside CSS selectors:

```
.slogan {
  background-color: $translucent-white;
}
```

*Be sure to stick to specific naming conventions so other developers can understand variable references*


You can also reference variables within variables and operate on them!


```
$font-size: 16px;
$line-height: $font-size * 1.6;
$h1-size: $font-size * 2;
```

![](https://media1.tenor.com/images/062ae5d02dcb35364b15b35f72fd96eb/tenor.gif?itemid=5247626)
