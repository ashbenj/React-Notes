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









## Let's talk about PROPS---


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

<br />

If you want to use the component again, you can with different names like:

```
<Tweet name="Tillman"/>
<Tweet name="Hello"/>
<Tweet name="Goodbye"/>
```

<br />

So, you would then go into the actual component file - *Tweet.js* and then add 'props':


```
function Tweet(props) {

  return(

    <div className="tweet">

        <h3>{props.name}</h3>

    </div>
  );
}
```

<br />

You will see 'props' in the function parameter and then you see *'props.name'* in the h3. <br /><br /> 
**Name** is what we called the property, remember? 

<br />

We can add as many props to the component as we want to:<br />

```
<Tweet name="Jashele" message="This is a random tweet."/>
```
<br />


```
function Tweet(props) {

  return(

    <div className="tweet">

        <h3>{props.name}</h3>

        <p>{props.message}</p>

    </div>
  );
}
```

<br />


If you don't want to do props, you can deconstruct by doing this:

```
function Tweet({name, message}) {

  return(

    <div className="tweet">

        <h3>{name}</h3>

        <p>{message}</p>

    </div>
  );
}
```

<hr />
<br />


## Let's talk about State---

**State** - data, a variable, the app renders itself based on that data. <br /><br />
  Based on the state, the app changes.


<br />

**Example, state will change based on button click:**


  ```
  import React, {useState} from "react";
  

  function App() {

    const [isRed, setRed] = useState(false);
    const [count, setCount] = useState(0);



    const increment = () => {
      setCount(count + 1);
      setRed(!isRed);
    };



    return (

      <div className="app">

      <h1 className={isRed ? 'red' : ""}>Change my color!</h1>

      <button onClick={increment}>Increment</button>

      <h1>{count}</h1>

      </div>

    );
  }
  ```


<br />

```
<h1 className={isRed ? 'red' : ""}>Change my color!</h1>
```

This is an if/else statement in React.

<br />
<br />





**State with an Object:**

```
 import React, {useState} from "react";
  

  function App() {

    const [users, setUser] = useState([
      {name: 'Jashele', message: 'Hello there'},
      {name: 'John', message: 'I am John Snow'},
      {name: 'Traversy', message: 'I am awesome'}
    ]);



    return (

      <div className="app">

      {users.map(user => (
        <Tweet name={user.name} message={user.message} />
      ))}

      </div>

    );
  }
```

<br />

Remember our **Tweet** component example? <br />
Yeah, we're just returning that for each user now.


<br />
<br />

**Resource:**

  - <a href="https://youtu.be/dGcsHMXbSOA?t=1926" target=_blank>Video tutorial on State</a>
  - <a href="https://youtu.be/dGcsHMXbSOA?t=2396" target=_blank>Video Tutorial on State with an Object</a> (And also when you're getting data from an API)



<hr />
<br />



  ## React Router


  Install: <br />

```
  npm install react-router-dom
```



















