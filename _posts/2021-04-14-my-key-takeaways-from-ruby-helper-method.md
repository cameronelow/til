---
layout: post
title:  "My Key Takeways from Ruby Helper Methods"
---

This week, we learned about testing in Rails. Testing allows us to x. The link is [here](https://guides.rubyonrails.org/testing.html). For Part 1 of this assignment, we learned how to write clean code for a web application that stores a digital library of movies. 

## REFACTORING ROUTES

First, I refactored the routes to shorthand in routes.rb file. I updated the Hash syntax to be the modern syntax, by removing the curly braces and moving the : in :symbol to the end of the symbol, so now it reads as symbol:. I learned a new way to write routes. Instead of saying `get("/", {:controller ⇒ "movies", :action ⇒ "index"})`, we can instead say `get "/" => "movies#index"`. To make that even shorter, you can write, for the root path only, `root "movies#index`

## ROUTE HELPER METHODS

Second, we learned how to create routes helper methods. Take the line of code: 

`get "/movies/:id" => "movies#show"`

Let's say that in the future, we have to rewrite the route as

`get "/films/:id" => "movies#show"`

In our movie library, the word "movie" would appear in many routes and tags throughout the code, so it would be risk to do a "find and replace" to change "movies" into "films." As such, we can create a route helper method like the following:

`get "/movies/:id" => "movies#show", as: :movie`

```as: :details``` acts as a variable to hold the route path ```"/movies/:id"```. That way, in my ```<a>``` tags, I can write details_path(id) rather than the original url. That way, if I have to change the route, my code and HTML tags can still point to the same web page. For this part, I replaced the routes in the ```<a>``` tags to be 

`<a href = "/movies/42"> #old`

`<a href = "<%=movie_path(42) %>"> #new, uses route helper method`

## NEW WAY TO RENDER VIEW TEMPLATES

Third, and probably a small note, I learned that we can remove the .html.erb extension when we render a template. So instead of writing `render template: "movies/new.html.erb"` we can say `render template: "movies/new"`. However, we can also shorten the render template function even more! If the name of the folder matches the controller - in this case, Movies_Controller - and if the file name matches the method name, we can remove `render template:` and `"movies/new.html.erb"` altogether. The program will know that we implicitly want to render this view file.

## LINK_TO METHOD

Fourth, I learned how to use link_to methods, which is a simpler Ruby-version of ```<a> ```tags in HTML. The format is `<%= "Placeholder text", helper_method_path%>`. For example, `<%= link_to "Show details", movie_path(a_movie)%>`. If the helper method takes in a parameter, like an Active Record id, you can write, for example `<%= "Show details", a_movie%>`. The caveat for this is that the code follows standard convention, meaning that the Active Record Movie should be the same name as the movie helper method. 

---

Part 2 of this assignment focused on forms. 

## NEW WAY TO MAKE FORMS

First, we learned a simpler way to create a form to add movies, which is 

```ruby
<%=form_with(url: movies_path) do%>
#insert elements you want in the form here
<%end%>
```

Other elements that we can add include label_tag, text_field_tag, text_area_tag, and button_tag. 

## CONVENTION

Second, through this exercise, I learned a lot about Ruby convention; I'll probably save that for another blog post. 

## NESTED PARAMETERS

Third, I learned how to pass nested structures into a params hash. 

```ruby
<form>

<label>Red </label>

<input name = "zebra[giraffe]" value="red">

<label>Blue </label>

<input name = "zebra[elephant]" value="blue">

<button>Submit</button>

</form>
```

If I type 123 into the first input and 456 into the second input, I get:

`Parameters: {"zebra"=>{"giraffe"=>"123", "elephant"=>"456"}}`

##INSTANT ROUTES

Fourth, I learned a short cut to instantly create the 7 default CRUD routes using 

`resource :movies`

I hope to learn more professional-grad Ruby code in the weeks to come!
