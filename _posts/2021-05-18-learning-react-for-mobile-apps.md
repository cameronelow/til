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
My typical coding style involves breaking out my code into chunks rather than "embed" them in one long mega-method. As such, functional components mesh with my style, and I know I will be using them a lot in my mobile projects.

##
