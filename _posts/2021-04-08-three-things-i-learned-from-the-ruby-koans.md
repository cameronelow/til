---
layout: post
title: Three things I learned from The Ruby Koans
---



This spring, I am taking Application Development II at the Chicago Booth School of Business. This is a more advanced version of AppDev I, where we learned the basics of Ruby on Rails. And we **barely** scratched the surface of what we can do in that language!

For our first assignment of ADII, we have to complete the Ruby Koans. If you haven't heard of it, Ruby Koans is a "path to enlightenment" in the community. You do many, many *koans*, or mini assignments going over data structures, automated tests, and syntax. Specifically, there are 278 koans in all. 

Here are (at least) three things I learned from [The Ruby Koans](http://rubykoans.com/):

## assert_equal

This is the crux of making automated tests in Ruby. As the first koan about_asserts.rb, I believe it is definitely one of the most important. By using `assert_equal expected_value, actual_value`, we can automatically check to see if our code's output matches what we expect it to be. 

## .map 

This method is a life-saver. Introduced in about_iteration.rb, it allows the coder to write an iterative loop in one line of code. 

```ruby
array = [1, 2, 3]
another_array = array.map { |item| item + 10 }
#[11, 12, 13]
#Note that .map is the same as .collect
```

Normally, we would probably write this as

```ruby
array = [1, 2, 3]
another_array = []
array.each do |num|
	new_num = num + 10
	another_array.push(new_num)
end
```

The `.map` function in arrays makes facilitates iteration and cleans up the code.

## regex

Admittedly, before doing the Ruby Koans, I didn't quite grasp regular expressions. In the koan about_regular_expressions.rb, not only did I learn how to use them to match words, characters, and numbers, but also new shorthands to do them! For example, instead of writing out `[/[a-zA-Z0-9_]+/]` to match word characters, we can write `[/\w+/]`. We can even do this with numbers, too! The typical regex for matching digits is `[/[0123456789]+/]`, but a short-hand is `[/\d+/]`. Moreover, I learned two new important functions to use in conjunction with regular expressions. One is `.scan` to find all instances of a regex and another is `.sub` to find and replace on instance of a regex. I already knew `.gsub` from AppDev1, which finds and replaces all instances of a regex.

The Ruby Koans project has been instrumental to advancing my Ruby knowledge, and I now keep it as an encyclopedia when I code.
