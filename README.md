# Jashele's Notes
Notes from Lambda School.  Study all you need!! 

<br />

# React
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


<br />



# React Router
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

The Route component is the way we declare what components will be mounted based on what URL's are being requested by the user.

```
import { Route } from 'react-router-dom';
```
<br />

*Component Prop (example)*

The component that you want React to mount when the URL matches the requested path. So in our case when /users is requested, the Users component will be mounted.
```
<Route path="/users"/ component={Users} />
```

<br />

**Think of your Route components asking you this question every single time you set one up.**

*What component do you want mounted when a users asks for what url path?*


