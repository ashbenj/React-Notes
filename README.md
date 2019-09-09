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
<br />
<br />


















# What is React?

- A JavaScript library for building user interfaces.


<br />
<br />
<br />












# The Basics

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





<br />
<br />
<br />












# Let's talk about PROPS---


**What is a prop?** <br />
- A property that we can define on each individual component.<br /><br />

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

- You will see that 'props' has been added to the function's parameter and then you see *'props.name'* in the h3. 
- **Name** is what we called the property, remember? 

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


<br />
<br />
<br />

















# Let's talk about State---

**State** 
- data, a variable, the app renders itself based on that data. 
- Based on the state, the app changes.


<br />

**Example, state will change based on button click.  This is an example component using state:**


  ```
  import React, {useState} from "react";
  

  function App() {

    
    /// SET STATE ///

        const [isRed, setRed] = useState(false);
        const [count, setCount] = useState(0);


    /// VARIABLES CALLING STATE /// 

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


 ///  MOST OF THE TIME THIS DATA WILL COME FROM AN API... OR SOMETHING   ///

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
Yeah, we're just returning that for each user now using .map


<br />
<br />

**Resource:**

  - <a href="https://youtu.be/dGcsHMXbSOA?t=1926" target=_blank>Video tutorial on State</a>
  - <a href="https://youtu.be/dGcsHMXbSOA?t=2396" target=_blank>Video Tutorial on State with an Object</a> (And also when you're getting data from an API)



<br />
<br />
<br />









  # React Router


  Install: <br />

```
  npm install react-router-dom
```

<br />

Importing to your React file:
<br />


```
import {BrowserRouter as Router, Switch, Route} 'react-router-dom'; 
```

<br />

- Importing *BrowserRouter* as *Router* means you're renaming the default **BrowserRouter** to **Router**.  This is what handles routing.
- You must wrap your components in `<Router>` that you want to have the routing funcionality to be available in.  



<br />




- ## Route:

`Route` renders out the component based on the URL.


```
function App() {

        <Router>

            <div className="App">

                <Nav />

                <Route path "/" component={Home}>

                <Route path="/about" component={About} />

                <Route path="/shop" component={Shop} />

            <div>

      </Router>

}
```


<br /><br />


- ## Switch:
`Switch` stops the route from going further & only renders out that component you're trying to go to. <br />


```
function App() {

        <Router>

            <div className="App">

                <Nav />

                <Switch>

                <Route path "/" component={Home}>

                <Route path="/about" component={About} />

                <Route path="/shop" component={Shop} />

                 </Switch>

            <div>

      </Router>

}
```

<br />

As soon as it detects say... `/about` or `/shop`  the route will stop so that it won't render out every component with a `/`.

<br />


- ## Exact:

`Exact` specifies path.


```
function App() {

        <Router>

            <div className="App">

                <Nav />

                <Switch>

                <Route path "/" exact component={Home}>

                <Route path="/about" component={About} />

                <Route path="/shop" component={Shop} />

                 </Switch>

            <div>

      </Router>

}
```

<br />


In the above example example that demonstrates a **Nav** component you would go into that file and import `Link`: <br />

```
import {Link} from 'react-router-dom';

function Nav() {
  return (

    const navStyle = {
      color: 'white'
    };



      <nav>
        <h3>Logo<h3>
                  <ul className="nav-links">

                            <Link style={navStyle} to='/about'>

                              <li>About</li>

                              </Link>




                            <Link style={navStyle}  to='/shop'>

                              <li>Shop</li>

                              </Link>


                    </ul>
          </nav>
    )
}

export default Nav;
```

<br />


- Wrap the links with `<Link>`.
- `<Link>` takes 1 prop called `to` which is where you put the route.
- `navStyle` has also been added which adds styling to the links.



<br />
<br />



## Dynamic Routing


Example: <br />
Editing the shop.js component -- 
<br />

```
import React, {useState, useEffect} from 'react';
import {Link} from 'react-router-dom';
import './App.css';


function Shop() {




// useEffect() TO RUN THIS & THE [ ] MEANS THIS WILL ONLY RUN WHEN THE COMPONENT MOUNTS //


    useEffect(() => {

        fetchItems();

    }, []);





// CREATE A STATE TO PUT THOSE ITEMS IN 

  const [items, setItems] = useState([]);





// CREATE A FETCH CALL //


    const fetchItems = async () => {

          const data = await fetch('https://fortnite-public-api.theapinetwork.com/prod09/upcoming/get');
    }




// CONVERTING ITEMS TO JSON TO MAKE THE ITEMS EASIER TO READ IN THE CONSOLE // 

    const items = await data.json();

   
// YOU CAN SET ITEMS TO THE ITEMS THAT WE'RE GETTING BACK // 
    console.log(items.items)
    setItems(items.items)



    return (
        <div>

        /// HERE WE CAN RENDER OUT STUFF FROM THE API ///

          {items.map(item => (
            <h1 key={item.itemid}>{item.name}</h1>



            // WHAT IF YOU WANT TO ADD A LINK TO EACH ITEM??  
            WE CAN USE DYNAMIC ROUTING TO GO TO THE UNIQUE ITEM'S LINK (ID). //

                    <Link to={`/shop/${item.itemid}`}>{item.name}</Link>
          ))}
         
         

        </div>
    );
}

export default Shop;
```

<br />

The links above will not route anywhere, so we would need to go back into `App.js` and create more routes:
<br />
<br />

The dynamic routing way:

```
<Route path="/shop/:id" />
```

<br />


And you would also need to create a component for it:<br />
For example: *itemdetail.js*


```
import React, {useState, useEffect} from 'react';
import {Link} from 'react-router-dom';
import './App.css';


function ItemDetail({match}) {




// useEffect() TO RUN THIS & THE [ ] MEANS THIS WILL ONLY RUN WHEN THE COMPONENT MOUNTS //


   useEffect(() => {
     fetchItem();
     
   }, []);





// CREATE A STATE TO PUT THOSE ITEMS IN 

  const [item, setItem] = useState({
    
    images: {}
    
  });



  const fetchItem = async () => {
    const fetchItem = await fetch(`https://fortnite-public-api.theapinetwork.com/prod09/upcoming/get?ids=61ea3e9-8438e42-f53`)
    const item = await fetchItem.json();



  // SET ITEM TO OUR ITEM THAT WE'RE GETTING BACK //
    setItem(item);
    console.log(item);
  }





    return (
        <div>

          <h1>{item.name}</h1>

          <img src={item.images.transparent} alt="" />

        </div>
    );
}

export default Item;
```

<br />

The new route in app.js should be:

```
<Route path="/shop/:id" component={ItemDetail}>
```

<br />

We also need to change the shop route to `exact` so the dynamic route will work otherwise it'll stop routing at shop:

```
<Route path="/shop" exact component={Shop}>
```


<br />
<br />


If we do curly braces we get access to `match`.<br />

Instead of: 

```
const fetchItem = await fetch(`https://fortnite-public-api.theapinetwork.com/prod09/upcoming/get?ids=61ea3e9-8438e42-f53`)
```

<br />

We can simply add `${match.params.id}` after the id.

```
const fetchItem = await fetch(`https://fortnite-public-api.theapinetwork.com/prod09/upcoming/get?ids=${match.params.id}`)
```

Now we have access to the unique id of each item.

<br />


- <a href="https://youtu.be/Law7wfdg_ls?t=1787" target=_blank>Video tutorial that explains match</a>





<br />
<br />


**Resources:**


- <a href="https://youtu.be/Law7wfdg_ls?t=297" target=_blank>Tutorial that explains routing & a walk-through</a>
- <a href="https://youtu.be/Law7wfdg_ls?t=1007" target=_blank>Create Dynamic Routes tutorial</a>








<br />
<br />
<br />







