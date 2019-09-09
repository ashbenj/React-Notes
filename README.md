# React Notes - By Jashele Tillman

This is just a reference guide that I can easily refer back to.  This is not intended to be a full on React walk-through or a tutorial.  I recommended checking out <a href="https://reactjs.org" target=_blank>Reactjs.org</a> or <a href="https://www.youtube.com/channel/UClb90NQQcskPUGDIXsQEz5Q" target=_blank>Dev Ed</a>.  I also will be adding additional resources to this file as I write it.  This file is never complete.
<br />


<a href="https://www.linkedin.com/in/jashelet/" target=_blank>
<img src="images/linkedin.png" alt="Contact Jashele on LinkedIn"> </a><a href="https://twitter.com/jasheloper" target=_blank>
<img src="images/twitter.png" alt="Contact Jashele on Twitter"></a><a href="mailto:jtmediaaccts@gmail.com">
<img src="images/email.png" alt="Contact Jashele via Email"></a>

<br />

**My Portfolio:** <a href="http://jasheletillman.me/" target=_blank>JasheleTillman.Me</a>
<br />
**My Blog:** <a href="https://jashele.blog/" target=_blank>Jashele.Blog</a>

<br />









# What is React?

A JavaScript library for building user interfaces.


<br />
<hr />









## The Basics

Creating a new React app, type this into the terminal:

```
npx create-react-app my-app
```

<br />






CD into the app: <br />
```
cd my-app
```
<br />






Open the app in browser: <br />


```
yarn start

OR

npm start
``` 
<br />







When starting any React file, add the following the header:

```
import React from 'react';
```
<br />






**Basic App.js file using a Functional Component:**

```
import React from "react";


function App() {
  return (
    <div>
      <h1>Hello React</h1>
    </div>
  );
}

export default App;
```

<br />

**Resources:** <br />

- <a href="https://youtu.be/dGcsHMXbSOA?t=1111" target=_blank>Creating a component with added logic & importing a component</a>
- <a href="https://youtu.be/dGcsHMXbSOA?t=1354" target=_blank>Styling a Component</a>




<hr />
<br />









## Let's talk about PROPS


**What is a prop?** <br />
A property that we can define on each individual component.<br /><br />

So, let's say we have a component called 'Tweet' that we've imported into the app.js file.
<br />

```
<Tweet />
```
<br />

We can add a name on it like so: <br />

```
<Tweet name="Jashele"/>
```


















