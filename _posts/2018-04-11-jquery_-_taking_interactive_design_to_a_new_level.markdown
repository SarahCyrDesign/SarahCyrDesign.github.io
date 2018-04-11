---
layout: post
title:      "jQuery - Taking Interactive Design to a New Level "
date:       2018-04-11 18:20:05 +0000
permalink:  jquery_-_taking_interactive_design_to_a_new_level
---


jQuery is the Javascript library that has gained traction over the years in creating dynamic content. You can create animations,  effects, traverse through HTML document, event handling as well as shorten your code significantly! Even better, jQuery is open source and can be accessible through download or be referenced directly from the CDN link.

```
<script type="text/javascript" language="Javascript" 

	src="http://ajax.aspnetcdn.com/ajax/jquery/jquery-1.4.1.min.js"></script> 
```


For UI designers there is also another library reference site loaded with UI Specific component source codes.
For example, for an [accordian effect](https://jqueryui.com/accordion/):

```
  <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script>
  $( function() {
    $( "#accordion" ).accordion();
  } );
  </script>
```

Over the course of the few weeks I have been experimenting with animation effects to be used with forms with jQuery. Any script used was created in its own js folder.

index.html

```
<div class="register">
        <button>Register</button>
      </div>

      <div class="form-container">
        <form>
          <label for="fname">First Name</label>
          <input type="text" id="fname" name="firstname" placeholder="Fast name...">

          <label for="lname">Last Name</label>
          <input type="text" id="lname" name="lastname" placeholder="last name...">

          <label for="country">Country</label>
          <select id="country" name="country">
            <option value="australia">Australia</option>
            <option value="canada">Canada</option>
            <option value="usa">USA</option>
          </select>

          <input type="submit" value="Submit">
        </form>

</div>

```

The following jQuery code allows for the following:
1. Hide the form upon loading via $(document).ready
2. Once register button is clicked, reveal the form via toggle effect
3. The form can be toggled on and off with the register button


```

$(document).ready(function(){
  $('.form-container').hide();
  $('.register').on('click', () => {
    $('.form-container').slideToggle('fast');
  });
});
```


With so many effects to choose from there are many more ways to experiment!
More to come in the next posts...
