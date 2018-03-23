---
layout: post
title:      "Intro to Sass"
date:       2018-03-23 16:08:38 +0000
permalink:  intro_to_sass
---


Sass (Synthetically Awesome Style Sheets) is a preprocessor for CSS or a scripting language that extends CSS so developers can write code in one language which then compiles into CSS. Other examples of preprocessors include Less and Stylus. A few things you can use with Sass:

* Variables
* Nested Rules
* Inline Imports
* So much more!

The major advantage of using Sass is that you can keep things organized and create style sheets much faster! It is the next step in a Front-end Developer's world and keeps developers happy across the board when collaborating.

**How to use Sass**

The first requirement to utilize Sass is that you must have Ruby installed.
Since Sass is a compiler so it can't be interpreted to the Web so you can do the following:

1.  Install Sass through the CLI:

```
gem install sass
```
or
```
npm install node-sass
```

2. You must also cd to the file to convert your file from .scss (sass) to .css 

```
sass main.scss:main.css
```
**You can autoupdate the sass file:
```
sass --watch C:\ruby\lib\sass\style.scss:style.css
```
![](https://m.popkey.co/47013d/3GKNY.gif)

If you need to visually experiment with how Sass will be converted to CSS in real time I highly suggest popping on by to [SassMeister](https://www.sassmeister.com/)

*This will be a multi-part series so be on the look out for part 2 where we will discuss Sass Variables*
