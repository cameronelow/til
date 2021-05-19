---
layout: post
title:  "Learning Javascript for Ruby Development"
---

Javascript is a great language to add dynamic interactions to a web application. It is the third language in the HTML-CSS-Javascript trifecta in front-end development. Following from the "Industrial Photogram App" post, JS has added another level of refined UI-design, like posting a comment on a post without the page redirecting the user back to the top. While I was already familiar with Javascript, these last couple of weeks were a good refresh on the topic. To add a Javascript template to our Ruby code, we would create a ```.js.erb``` file, like how we make a ```.html.erb``` page for HTML code.


## jQuery
A staple for front-end develpment, jQuery allows us to manipulate HTML elements. This library provides a shorthand for calls like ```document.getElementById()```, we can instead write ```jQuery() ``` or most commonly ```$()```. It also comes with built-in functions like ```.show()```, ```.hide()```, and ```$document.read()```. jQuery runs in the browswer, so it will live-update the Ruby app with any Javscript code.

## AJAX
Before adding in Javascript, CRUD actions like adding and deleting (in the case of Photogram, commenting and deleting comments) invoked a bad UX, since it would redirect each time these actions were made. AJAX allows us to update a web page without reloading it. 

### jQuery .ajax() Function
Luckily, Ruby has built-in functions to "AJAX-ify" our code, but I included an example below showing how the .ajax() function would work in the script to delete a comment. 
```
$.ajax({
      url: "/comments/<%= comment.id %>", 
      type: "DELETE",                     
      dataType: "script"                  
    });
 ```
 
### The AJAX shortcut
Instead of writing the above, I could use the ```link_to``` Ruby method to delete a comment and in the ```comments#destory``` action, I would render a JS template to do so. 
 ```
 <%= link_to comment,
      method: :delete,
      class: "btn btn-link btn-sm text-muted",
      remote: true do %>
```

There is a lot you could do with AJAX in web application development, but I listed a couple examples for future reference. 
