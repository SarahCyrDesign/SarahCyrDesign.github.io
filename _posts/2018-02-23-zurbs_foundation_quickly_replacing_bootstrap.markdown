---
layout: post
title:      "Zurb's Foundation quickly replacing Bootstrap"
date:       2018-02-23 20:02:42 +0000
permalink:  zurbs_foundation_quickly_replacing_bootstrap
---


Upon speaking to to a few Front-end Developers out there I was informed that there was another framework out there that gives Bootstrap a run for it's money, Zurb's Foundation! On first glance it looks very similar to Bootstrap's familiar grid system, however, Foundation utilizes the CSS grid model along with Flexbox to make a powerful web layout. Flexbox is now pretty much universally supported so it is a perfect integration.

With Foundation's XY Grid you can do may things:

1) Define Horizontal and Vertical rows

```
<div class="grid-x">
</div>

<div class="grid-y">
</div>
```

2) Set margins and padding

```
<div class="grid-x grid-padding-x">
</div>
```

3) Set grids to be full size of the browser window upon shrinking

```
<div class="grid-y grid-frame">
  <div class="cell-shrink header">
  </div>>
</div>
```

4) Combine more flexbox CSS with the grid to fine tune your styling

```
.center {
  display: flex;
	align-items: center;
	justify-content: center;
}
```

5) Set the amount of cells inside each row

```
<div class=" lower-hero large-12 frame-grid">
   <div class="grid-x grid-padding-x lower-hero-height">
      <div class="large-3 medium-3 cell">
     </div>

    <div class="large-6 medium-6 cell space-above">
      <h3 class="white-txt">Learn more about the Ownes Corning Roofing System</h3>
     <p class="white-txt">Contact us today to get started with a free estimate</p>
   </div>

   <div class="large-2 medium-2 cell space-above">
     <a href="#" class="lower-right-btn callout">Get a FREE Quote</a>
   </div>
</div>
```

and much more!

A final note worth mentioning is Foundation provides a gem you can incorportate seemlessly with Rails so you can get started on your client side right away.
