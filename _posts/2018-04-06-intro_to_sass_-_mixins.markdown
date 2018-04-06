---
layout: post
title:      "Intro to Sass - Mixins"
date:       2018-04-06 15:08:15 +0000
permalink:  intro_to_sass_-_mixins
---


Another method Sass utilizes that cuts down on repetative code is the use of Mixins. Mixins let you make groups of CSS declarations that you want to reuse throughout your site. They take in values/arguments/parameters to be utilized throught your CSS. It is important to note that you should only use a mixin if it takes an argument.

```
@mixin backface-visibility($visibility) {
  backface-visibility: $visibility;
  -webkit-backface-visibility: $visibility;
  -moz-backface-visibility: $visibility;
  -ms-backface-visibility: $visibility;
  -o-backface-visibility: $visibility;
}
```

```
@include backface-visibility(hidden);
```

**$visibility argument is now assigned value to hidden**

Default Arguments can be assigned if no value is given:

```
@mixin backface-visibility($visibility: hidden) {
  backface-visibility: $visibility;
  -webkit-backface-visibility: $visibility;
  -moz-backface-visibility: $visibility;
  -ms-backface-visibility: $visibility;
  -o-backface-visibility: $visibility;
}
```

```
.front, .back {
    width: 100%;
    height: 100%;
    position: absolute;
    @include backface-visibility ;
  }

```

*Things to consider about using Mixins*

1. Can take multiple arguments
2. Sass allows you to define each argument in your @include statement
3. When values are specified you can define them out of order
4. If a mixin definition has a combination of arguments and has no default value, you should define the arguments without the default value first

```
@mixin dashed-border($width, $color: #FFF) {
  border: {
    color: $color;
    width: $width;
    style: dashed;
  }
}
```

```
span {
  @include dashed-border(3px);
}

p {
  @include dashed-border(3px, green);
}

div {
  @include dashed-border(color: purple, width: 5px);
}
```
5. Mixins can be nested
6. You can pass multiple arguments as lists, maps or more mixins

```
@mixin stripes($direction, $width-percent, $stripe-color, $stripe-background: #FFF) {
  background: repeating-linear-gradient(
    $direction,
    $stripe-background,
    $stripe-background ($width-percent - 1),
    $stripe-color 1%,
    $stripe-background $width-percent
  );
}

$college-ruled-style: ( 
    direction: to bottom,
    width-percent: 15%,
    stripe-color: blue,
    stripe-background: white
);
```

When we include our mixing, we pass the arguments in a map with the …

```
.definition {
  width: 100%;
  height: 100%;
  @include stripes($college-ruled-style…);
}
```

****Use this method only if it's more readable in the context of code****

There is so much versatility with Mixins you can harness the power of DRYing up your CSS!

![](https://media1.tenor.com/images/eb8179bf500f84b27479b90fcbb316a9/tenor.gif?itemid=5378542)
