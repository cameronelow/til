---
layout: post
title:  "Building an Industrial Photogram App"
---

In App Dev 1, one of the big key projects we worked on was Photogram, a photo-sharing platform akin to Instagram. Looking back, I thought it was a challenging project
because we were making a social media app as a culmination of the Ruby on Rails topics we had learned up to that point, including sessions, forms, and conditionals.

Now, we revisited this project, and our goal was to make it an industrial-grade application. 

## Devise and Scaffolds
There are many shortcuts in Ruby. A couple of them are the Devise gem and scaffolding. In the Terminal, I could write ```rails generate devise user column_names``` to automatically generate a user model and ```rails generate scaffold model_name column_names``` to create scaffolds. I think of scaffolds as models with the bonus of included CRUD RCAVs. It makes building databases more straightforward.

## Association Accessors
Although I had learned about direct and indirect associations in App Dev 1, industrial-grade apps require many of these associations to make coding them easier, especially since we want to join many of the models together. For example, to build out the Discover page, the user should be able to see the liked posts from people they follow, which could be done through an indirect association like```has_many :discover, through: :leaders, source: :liked_photos```. This project showed that it's better to plan out and draw any and all associations we may need before building out the pages for professional applications.

## Sample Data Task
To make a sample data task (i.e. rails sample_data), you need to create a dev.rake file in the lib/tasks folder. By pre-populating my models with data, I can iteratively debug my app and test out associations. 
```
task :sample_data do
  #insert code here
end
```
The rest of the project was using Bootstrap to build out the user interface and add in validations.
