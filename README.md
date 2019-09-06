# React Notes - By Jashele Tillman


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









## Some Basic Stuff

When starting any React file, add the following the header:

`import React from 'react';`



<br /><br />





- ## Anatomy of a React component:

``` 
const Component = () => {
  return (
    <div>
      <h1>I'm a React Component!</h1>
    </div>
  );
};
```


<br />



- ## Hooks

useState hook <br />

**Importing the useState hook involves first adding this code to the header:**

`import React, {useState} from "react";`





<br />





**And this is how you would use it:**

`const [state, setState ] = useState();`





<br />




- ## Conditional Rendering: if statements for React.

Example:

`{lightOn === false ? <img src={white} /> : <img src={yellow} />}`





<br />




### Sample Projects:

<a href="https://codesandbox.io/s/light-bulb-state-9ovk4?fontsize=14" target=_blank>LightBulb Project</a> 

<a href="https://github.com/jasheloper/react-american-football-scoreboard/tree/jashele-tillman" target=_blank>American Football Scorecard Project</a>




Skeleton for app.js file

