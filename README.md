# Jashele's React Notes







**Create a React App**

```
// yarn command

create-react-app nameOfAppHere
```

```
// npm command using the npx utility 

create-react-app nameOfAppHere
```


<br />
<br />
<hr />








## React Component


**React.Component base class**


- allows us to tap into Component lifecycle.
- give us control into how our components work. 

<br />


**Build:**

``` 
class App extends React.Component {

} 
``` 

<br />



```render()```

- Life-cycle hook
- Used when we have some data we can render out to the DOM 


<br />





**A complete component looks like this:**

``` 
class App extends React.Component {
  constructor() { 
    super();
    this.state = {};
  }
  render() {
    return <div>Hello, I am Foo Component</div>;
  }
} 
``` 

<br />


**Props:**

- The ability to pass & share state around from one component to another. 
- are read only


<br />


**State:**

- An object that we have access to which lives on the class component's constructor.
- When it changes our component will re-render.
- We can also pass whatever data is found on this state object around as props to other components.
- When a component’s props are bound to the state of a parent component the child component will re render as well.


<br />


[see example](https://codesandbox.io/s/props-hr6rq?fontsize=14)




<br /><br />


**Event Handling**

Synthetic Event - how we interact with the DOM within the React Virtual DOM ecosystem.

- onClick 
- onDoubleClick 
- onMouseEnter 
- onChange



<br />

[see example](https://codesandbox.io/s/eventhandlers-react-pik2o?fontsize=14)




<br />
<br />
<hr />









## Styling


**Semantic UI**

*Import components*

```
import { Grid, Form, Input, TextArea, Button, Select } from "semantic-ui-react";
```


*Import the CSS*

```
import "semantic-ui/dist/semantic.min.css";
```



<br />

**Styled Components**

*Import Components*

```
import styled from 'styled-components'
```


*Usage*

```
// div 
const StyledDiv = styled.div``; 

// paragraph 
const StyledP = styled.p``; 

// section 
const StyledSection = styled.section``; 

// headers h1 - h6 
const StyledHeading = styled.h1``; 

// a 
const StyledA = styled.a``; 

// etc.....
```


<hr />

<br />


## React Router
**Add react-router**

```
 yarn add react-router-dom 
 ```

<br />

*In index.js import the BrowserRouter component and wrap your app with it:*

``` 
import { BrowserRouter as Router } from 'react-router-dom'; 
```

```
ReactDOM.render(    

  <Router>   

    <App />   

  </Router>,    

  document.getElementById("root")   

);
```

<br />

**Route Component**

The ```Route``` component is the way we declare what components will be mounted based on what URL's are being requested by the user.

```
import { Route } from 'react-router-dom';
```
<br />

**Component Prop:**

The component that you want React to mount when the URL matches the requested path. So in our case when /users is requested, the Users component will be mounted.
```
Example:

<Route path="/users"/ component={Users} />
```

**Think of your Route components asking you this question every single time you set one up.**

*What component do you want mounted when a users asks for what url path?*

<br />


**Exact**

By placing ```exact``` on a ```<Route />``` component you are saying that the specific path requested will be the only if the path matches exactly what was requested.

```
<Route exact path="/" component={Home}/>
```

<br />

**Link Component**

Helps us stay within the realm of our “client-side app.”

```
import { Link } from 'react-router-dom'
```


*Example:*

```
<Link to="/about">About</Link>
```

<br />

**Dynamic Routing**

*Example:*

```
<Route path='/users/:userId' component={SingleUser} />
```

<br />

**Find specific user data**

```
Example:


const avenger = 

avengerData.find(avenger => 

props.match.params.id === `${avenger.id}`);

```

<br />
<hr />

## Pass data to components rendered by React Router via the render prop


**Render prop**

A function prop that a component uses to know what to render. React Router uses this pattern to let us pass data to the component we want to render.

```
<Route render={() => 

<MyComponent 

someProp={someData} 

someOtherProp={moreData} 

/>} />
```
<br />

If we still need props - ```match, history, and location``` in our component (and most the time we will), they are actually passed to the function inside render as an argument in an object. 

```
<Route render={props => 

<MyComponent 

someProp={someData} 

someOtherProp={moreData} 

/>} />
```

<br />

Now with access to all 3 props:

```
<Route render={(props) => (

  <MyComponent 

    someProp={someData} 

    someOtherProp={moreData} 

    match={props.match}

    history={props.history}

    location={props.location}

  />

)} />
```
<br />


**Use spread operator to make the above easier.**

```{...props}``` - will “spread” in all three props that we passed through manually above:

```
<Route render={(props) => (

  <MyComponent 

    {...props}

    someProp={someData} 

    someOtherProp={moreData} 

  />

)} />
```


<br />

**Add nested routes to an application and display sub-nav views.**

As to not re-render a whole page.


```
Example:

<Route exact path="/" component={Home} />

        <Route
          path="/avengers/:id"
          render={props => <AvengerPage {...props} avengers={avengerData} />} />


        <Route
          path="/avengers"
          render={props => <AvengerList {...props} avengers={avengerData} />}
        />


```

<br />

**Use the built in `history` object to programmatically navigate to other routes.**

 Example: Navigating to a new page after a promise has resolved and new data is available.

```
 function routeToAvenger() {
  props.history.push(`/avengers/${avenger.id}`)
}
```


<br />


**Link and NavLink**


**Link**<br />
Renders an anchor tag with an href of the path we have specified on it.

<br />


**NavLink**<br />
Adds the class active to the anchor tag when the url matches the path in the NavLink component.


```
import { NavLink } from 'react-router-dom'

<NavLink to="/">Home</NavLink>

<NavLink to="/about">About</NavLink>
```


Navigating to ```about``` would render:

```
<a href="/about" class="active" aria-current="page">About</a>
```
<br />
<hr />

## Formik to Control Forms

**Installation**
```
npm install formik --save
```

or

```
yarn add formik
```
<br />

**Import:**
```
import { withFormik, Form, Field } from "formik";
```
<br />


```mapPropsToValues``` allows us to create a connection between the data being handled in the form and the handlers for the data. The conditional values for the key-values allow you to pass in default or custom data to the form initially (great for a ‘change-data’ form, for example).
<br /><br />

**Example:**

```
const FormikLoginForm = withFormik({

  mapPropsToValues({ username, password }) {
    return {
      username: username || "",
      password: password || ""
    };
  },

  handleSubmit(values) {
    console.log(values)
    //THIS IS WHERE YOU DO YOUR FORM SUBMISSION CODE... HTTP REQUESTS, ETC.
  }

  )(LoginForm);
  ```
<br />
<hr />

## Learn to validate user input in forms

  **Yup dependency**

```
  yarn add yup or npm install --save yup
  ```



**Import**

```
  import * as Yup from "yup";

// You may see this as (import Yup from 'yup') in some tutorials, the above method seems less buggy
```

<br />

Formik wants to see a “Yup Schema,” which is basically a description of what each named field is supposed to look like, so that Yup can pass or fail the input.

```
  //======VALIDATION SCHEMA==========
  validationSchema: Yup.object().shape({
    email: Yup.string()
      .email()
      .required(),
    password: Yup.string()
      .min(6)
      .required()
  }),
  //======END VALIDATION SCHEMA==========
  ```
<br />

## YUP - Checking for Errors

How do you know if you’ve gotten a bad input after validating it?  Connect validation to your form the following ways. 
<br /><br />


  **Props:**

 ``` Errors  ``` - 

 ```
   { errors.email && <p>{errors.email}</p> }
  ```

<br />

  ``` Touched ``` - 

  This prop keeps track of whether you’ve been in this field previously. This makes it possible for you to avoid seeing validation errors as you’re typing into the field the very first time.

 ```
{ touched.email && errors.email && <p>{errors.email}</p> }
 ```

<br />

## YUP - Custom Error Messages

 ```
 validationSchema: Yup.object().shape({
    email: Yup.string()
      .email("Email not valid")
      .required("Email is required"),
    password: Yup.string()
      .min(6, "Password must be 6 characters or longer")
      .required("Password is required")
  }),
 ```

  All you need to do is add your custom error message into the arguments for the method!



  
<hr />



## Make POST requests to pass data collected from a form to a database

   ```POST ``` - the method that allows us to “post” (or create) information on a web server. When a user makes a POST request, that data is usually being added to the server’s database.

   1. Install axios dependency: <br />
   ```yarn add axios```<br />

   2. import axios alongside our other imports in our Formik form component.<br />
   ```import axios from "axios";```<br /><br />



   **Sample POST request:**

```
   const sentData = { data: "Hello World!" };

axios
  .post("https://yourdatabaseurlgoeshere.com", sentData)
  .then(res => {
    console.log(res.data); // Data was created successfully and logs to console
  })
  .catch(err => {
    console.log(err); // There was an error creating the data and logs to console
  });
  ```

  **Facts:**
  - using a .post() call instead of a .get() after it.<br />
  -  follow that up with a URL passed in as an argument.<br />
  - pass in the data that we want to send to our web server as the second argument.<br />
  - In this example, the data that we’re sending is our sentData variable which is an object. This would be sent to our web server.<br />
  -  You will need to initially console.log() the server’s response to find out what kind of data you’re receiving back in your response.