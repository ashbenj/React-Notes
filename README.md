# React Notes
**Create a React App**

```
// yarn command
yarn create react-app nameOfAppHere
```

```
// npm command using the npx utility 
npx create-react-app nameOfAppHere
```

<br />


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

*In app.js import the BrowserRouter component and wrap your app with it:*

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

```import { Link } from 'react-router-dom'```

<br />

*Example:*

```<Link to="/about">About</Link>```

<br />

**Dynamic Routing**

*Example:*

```<Route path='/users/:userId' component={SingleUser} />```

<br />

**Find specific user data**

```
Example:


const avenger = 

avengerData.find(avenger => 

props.match.params.id === `${avenger.id}`);

```

<br />

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

Now with a ccess to all 3 props:

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


**`Link` and `NavLink`**

<br />


```Link```
Renders an anchor tag with an href of the path we have specified on it.


<br />

```NavLink```
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