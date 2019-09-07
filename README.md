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

```
import React from 'react';
```
<br />

`render`  tells react what will be mounted to the screen.
- called in the mounting phase & the updating phase.
<br /><br />

`constructor` function serves the component up with the initial state data that it needs to have during initial render.



<br /><br />

<hr />



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
<hr />



- ## Hooks

useState hook <br />

**Importing the useState hook involves first adding this code to the header:**

`import React, {useState} from "react";`





<br />





**And this is how you would use it:**

`const [state, setState ] = useState();`





<br />
<hr />


- ## Skeletons

**App.js - begin a new app file**
```
import React from "react";

function App() {

  return (
    <>
     
     <h1>JSX</h1>
    <Component />

    </>

  );
}

export default App;
```


<br />
<br />


**Index.js - begin a new index file**
```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```


<br />
<br />



**Component - begin a new component file**
```
import React from 'react';

const Component = () => {
  return (
    <>
      <h1>I'm a React Component!</h1>
    </>
  );
};

export default Component;
```


<br />
<br />




### Sample Demos:

- <a href="https://codesandbox.io/s/light-bulb-state-9ovk4?fontsize=14" target=_blank>LightBulb Project</a> 

- <a href="https://github.com/jasheloper/react-american-football-scoreboard/tree/jashele-tillman" target=_blank>American Football Scorecard Project</a>


<br />
<br />
<hr />


- ## React Class Component

```
class App extends React.Component {
  constructor() {
    super();
    this.state = { 
        message: "Hello from App State!!"
};
  }
  render() {
  return <div>{this.state.message}</div>;
}
```

<br />

### Sample Demos:

- <a href="https://codesandbox.io/embed/friends-betjt" target=_blank>Friends Project</a>

- <a href="https://codesandbox.io/embed/propscomponents-hr6rq" target=_blank>Props / Class Components Project</a>

<br />
<br />

<hr />


- ## Event Handlers

**Button Example:**

Click handler code:
```
singleClickHandler = () => alert("Single Click!");
```

<br />




Click handler usage:
```
<button onClick={this.singleClickHandler}>Click Handler Demo</button>
```

<br />
<br />

**DIV Example:**

Mouse handler code:

```
mouseEnterHandler = () => alert("Mouse Entered");
```

<br />

Mouse handler usage:
```
<div onMouseEnter={this.mouseEnterHandler}>Mouse Enter</div>
```

<br />

## Here's a cool event handler sample if you wanted to change the value of something: 

**Set an empty string in state:**

```
  constructor() {
    super();
    this.state = {
      someValue: '',
    }
  }
  ```

<br />

**The state would change based on new value:**

```
changeHandler = event => {
  this.setState({someValue: event.target.value});
};
```

<br />

### Sample Demos:

- <a href="https://codesandbox.io/embed/eventhandlers-react-pik2o" target=_blank>Event Handlers Project</a>










