---
layout: post
title:  "Ionic React for Cross Platform Mobile Development"
---

After finishing the React course, I took an online class on Ionic.js. After importing react via ```npm install @ionic/react```, I followed along with the instructor in making a simple Ionic app in VS Code. Below, I noted some of my top takeaways from the topic. 

## Ionic Components
The biggest draw to Ionic.js is its [components](https://ionicframework.com/docs/components). It contains a library of Ionic components and Ionicons. If I wanted to add a button, for example, I could import it and add it to my app. 
```
import {IonButton, IonToast} from '@ionic/react'
function Example(){
  return (
    <div>
      <IonButton onClick = {handleClick}>Click me!</IonButton>
      <IonToast isOpen = {showToast} message= "Hello world!"/>
    </div>
  );
}

```
Ionic comes with adaptive styling, so the UI will adjust to fit to any screen without sacrificing good front-end design.


## User Input with Forms
Just about any dynamic app needs to take in inputs, generally through forms. The Ionic framework comes with a template for forms, like the following:
```
<IonApp>
   <IonHeader>
     <IonToolbar>
       <IonTitle>App Title</IonTitle>
     </IonToolbar>
   </IonHeader>
   <IonContent className="ion-padding">
     <IonItem>
       <IonLabel>Label Name: </IonLabel>
       <IonInput value = {value}
         onIonChange = {(event) => setValue(event.detail.value)}
       />
    </IonItem>
   </IonContent>
 </IonApp>

```

## Unit Testing
Like rails sample tasks, we can run unit tests to make sure that the code works as intended. First, you'd import the JavaScript file you want to test. Next, you'd write a sample method in a format like:
```
it('calculates correct answer', () => {
  const variable = someMethodName(param1, param2);
  expect(variable).toEqual("some value");
});
```
It provides a good sanity check, ensuring that we're not breaking any code when making major changes. 


_______________________
### CSS Import Statements to Use. 
```
Core CSS required for Ionic components to work properly     
import '@ionic/react/css/core.css'; 

Basic CSS for apps built with Ionic.  

import '@ionic/react/css/normalize.css';  
import '@ionic/react/css/structure.css';  
import '@ionic/react/css/typography.css';  


Optional CSS utils that can be commented out.  

import '@ionic/react/css/padding.css';  
import '@ionic/react/css/float-elements.css';  
import '@ionic/react/css/text-alignment.css';  
import '@ionic/react/css/text-transformation.css';  
import '@ionic/react/css/flex-utils.css';  
import '@ionic/react/css/display.css';  
```
