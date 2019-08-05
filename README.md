# Jashele's Notes
My Notes.
<br /><br />

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

