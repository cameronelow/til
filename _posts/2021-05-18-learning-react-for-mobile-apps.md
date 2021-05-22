---
layout: post
title:  "Learning React for Mobile Apps"
---

At this point in the quarter, App Dev 2 split into two tracks: Option A was to continue building Ruby apps and Option B was learning to make mobile apps. I decided to go with Option B and learn a new type of app development. Although my mobile apps would be simpler compared to the advanced Ruby apps I've made so far, I wanted to take on the challenge. As such, I'm learning React through Scrimba, which involves some JavaScript and JSX. It's more readable than Bootstrap and it allows for web components. 

This is my first time learning how to create a mobile app in React, and I'm excited to go down this track! Here are some of the key takeways from React.

## Functional Components
Functional components use, as the name suggests, functions to render HTML elements on a page and improves the readability of the code. For example,
```
import React from "react"
import ReactDOM from "react-dom"

function exampleComponent() {
  return (
    <div>
      <h1>This is a functional component! </h1>
      <p> And here is a subtitle paragraph </p>
     </div>
  )
}

ReactDOM.render(
  <exampleComponent />, 
  document.getElementById("root")
)
```
My typical coding style involves breaking out my code into chunks rather than "embed" them in one long mega-method. As such, functional components mesh with my style, and I know I will be using them a lot in my mobile projects. I can also separate components into their own files, which contrasts with the long HTML files I've made in the past. You can also use class-based components in React. 

## Props
Props (short for properties) are similar to HTML attributes. In order to reduce repetition in our functional components, we can use ```props``` to take in a user input. In one file, I could write
```
<ComponentName 
  param1 = "one"
  param2 = "two"
  param3 = "three"
/>
```
and in the ComponentName.js file, I'd write
```
function ComponentName(props){
  return(
    <div>
      <h1>{props.param1}</h1>
      <h2>{props.param2}</h2>
      <h2>{props.param3}</h2>
    </div>
  )
}
```
That way, I can have one functional component that I can pass any parameter into to build out my native app. You can also pass in an object with the parameters rather than multiple parameters.

## State
State is the data that a component maintains, which can change its value. This is one of the most important concepts in React. Inside the class-based component, I would include a constructor to initialize some values. The template to make a constructor is: 
```
constructor() {
  super()
  this.state = {}
}
```
With event handling, I can also change the state of a Component with ```this.setState()```. This makes the app more dynamic and interactive. 

These were some of the basics of React that I have learned so far. For my final project, I will be making a mobile app, which will build upon what I've learned so far in React development.
