# Amazon-Clone-Guided-Learning

## Build an Amazon Clone Step-By-Step

In this Guided Learning, we will make the Amazon Clone using React. 
- We will also be using Firebase for Authentication, Database, Functions and Hosting.
  - Firebase is a great tool to get started with projects quickly. 
- We will also be using HTML, CSS, and React Context API. 

**Please keep in mind, you need to have [Visual Studio Code](https://code.visualstudio.com/) and [NodeJS](https://nodejs.org/) installed.**

Are you ready? LET’S GOOOOO 🔥 🚀

Let’s make a new folder named ```amazon-clone``` and open it. 
- As soon as you are in the folder, right click and select Open With Code.

After you click Open with Code, you’ll see a huge weird window. Don’t worry we got you covered. This is what you might be seeing:

![](https://github.com/DrVicki/Amazon-Clone-Guided-Learning/blob/main/images/VSC-OpenWindow.png)

**Visual Studio Code** is the Code Editor we are going to use; this is what professionals mostly use, but this is more of a personal preference. You can use Atom or any other editor too, but Visual Studio Code makes your life easier.

Now that in you are in Visual Studio Code, Press Ctrl + J (on Windows) and ```Command + J``` (on Mac) and you should see a terminal window at the bottom just like shown below.

![](https://github.com/DrVicki/Amazon-Clone-Guided-Learning/blob/main/images/command-j.png)

Now you’re in the terminal, we can install and setup React app. 
- This is usually a headache when doing manually. So Facebook, the creator of React, made a script which installs and sets up React for you without any type of headache.
- To use this script, just type the following in the terminal and press Enter. This will take time so till then you can read what the script actually does below.

```npx create-react-app ```

How does this work?? 

```NPX``` is part of npm (Node Package Manager) except npx runs a remote script instead of installing it locally. 
- This is done so you always have the latest version of React installed in your project. ```create-react-app``` is the name of the remote script and ```“.”``` specifies we want the script to make a React project in the SAME FOLDER and not make a new folder for it, if you had to make a new folder name, you could just provide the name of folder instead of ```“.”``` and it would make a folder for you.
- You know it is finished when you see ```“Happy Hacking”``` on your terminal. If you see this, we are ready to move on.

HAPPY HACKING

We have our React App installed, now we can start it. 

- In the terminal type the following command. This command will start the React App.
```npm start```

After you hit Enter, you should see your default browser open. 
- Although I suggest Google Chrome because of it’s development tools making life easier, it’s still your personal preference, but we cannot guarantee development quality with other browsers.

NPM START

If you did everything correct, you must see the following screen on your browser window.
- If you do not see the browser tab open
```http://localhost:3000```
- then go to above URL or even better, I’ve something for you. This will take you to your app.

LOCALHOST

This is the Welcome screen of React. But we want to build an Amazon Clone, so we need to clean up our React project so we can get started with the Amazon clone.

CLEANUP-FILES

Delete (optional) three files in the ```src``` folder from the React App. Those three files are
- ```App.test.js```
- ```logo.svg``` 
- ```setupTests.js```

We are deleting these files because they are not relevant to us in the project.

That’s not all, if you check the browser window now, I know what you’re seeing. Do not panic, we have the solution. Go to ```App.js``` and remove the following line from code.

```import logo from “./logo.svg”;```

Also, remove everything under the first ```<div>``` element from your ```App.js``` file. You’re code should look like the following:

```
import React from “react”;
import “./App.css”;
function App() {
    return <div className=”app”>React App</div>;
}
export default App;
```

Let’s cleanup the CSS files a bit.

- Go to ```App.css``` and remove all the contents of your file.
- Now go to ```index.css``` and add this piece of code on the top. Look at the change on the app. What do you see?

```
*{
 margin: 0;
 padding: 0;
}
```

This will get rid of the margin and padding of the page.

Now we have our React project perfectly set up. We can start making the **Amazon Clone**.

## Setting up the React Router

A very important thing to consider in a React app is navigation (moving from one page to another) of the users. 
- Since React is a single page application, it doesn’t support multiple routes by default.

But the node packages come to our rescue. 
- There’s a package named ```react-router-dom``` which allows us to create routes for our React project. 
- Setting up is one time, and then whenever you add a new page, you just need to inform the Router. 
- Don’t worry we will cover that in depth here!

Open your terminal and enter the following command to install ```react-router-dom```;

```npm install react-router-dom```
For reference [click here](https://reactrouter.com/web/guides/quick-start).
- When the installation completes, you should see something like this;

NPMINSTALL

After it's installed, let’s get our hands dirty and write some actual code. 
- Let’s make a new component. 
  - To make a component, simpl make a new file. Call it ```Home.js``` for our case. 
    - The convention is; the first letter of a component must be in capitals. Also create a ```Home.css``` file for the component styling.
- To make life easier, go ahead and install a Visual Studio Code extension named ```ES7 React/Redux/GraphQL/React-Native``` snippets. 
  - This extension will make the boiler plate for React components without typing the code all by yourself.

Let’s go inside ```Home.js```. 
- Type in ```“rfce”``` and you should get an option to autocomplete the snippets as shown in following picture.

RFCE

Hit Enter while on ```“rfce”```. 
- This will autocomplete the React boiler plate for you. 

Now let’s change the class of the div element provided us to ```“home”```. 
- We follow BEM convention while styling our components.
  - BEM Convention helps our CSS and JSX be organized to read later, and everything becomes easy to keep track of.

Let’s just add some text there for now; let’s say Hello. The code on the ```Home.js``` file now should be;

```
import React from "react";
function Home() {
   return <div className="home">Hello</div>;
}
export default Home;
```

Check the browser. You will not see anything because we haven’t prepared our entry point ```App.js``` yet. So let’s open the file and start setting up the React Router. 
- First, we need to import the dependencies. 
  - Import them using the following code at the top of ```App.js```.

```
import { BrowserRouter as Router, Route, Switch } from "react-router-dom";
```

Once you’ve imported the code, you can now use React Router in your file. 
- Let’s configure ```React Router``` according to our needs. Use the below code in your ```App.js```.

```
import React from "react";
import "./App.css";
import { BrowserRouter as Router, Route, Switch } from "react-router-dom";
import Home from "./Home";
function App() {
return (
  <div className="app">
    <Router>
      <Switch>
        <Route path="/">
          <Home />
        </Route>
      </Switch>
    </Router>
  </div>
);
}
export default App;
```

Now you can see Hello on the screen. Don’t worry, we are now running over the code to see what we have done.

Our motive is to have ```Home``` component to be rendered on the default route that is ```“/”```.
- To use the ```Home``` component, we need to import it, so we imported it at the top. 
- We need to wrap the entire app into the Router component, so that every component is a part of Router and has access to the Router.
- The ```switch``` specifies the components beneath it are to be rendered only under certain routes. So if a route is meant for ```“/”```, you cannot see the information on``` “/hello”``` route.
- The ```Route``` component is used under the ```Switch``` component. The ```Route```component specifies the rules of the Routes and components to render at a specific route. For example in this case we have the ```Home``` component render at ```“/”``` route. We will be adding more routes to this.

We now have the ```Router``` set up. Let’s go ahead and make the Amazon Navbar.
2. Creating the Navbar
I hope you guys are still pumped because now we are going to do some real cloning stuff! I’m pumped for this.
We are going to use a package for icons, and we need Material Icons to use them. So open your terminal and write the following command.
npm install @material-ui/core @material-ui/icons
Once you installed the dependencies, you can use it to display SVG icons which are provided by Material UI. Material UI is a very popular UI library for React which has a lot of prebuilt components just as icons which makes life easier.
So enough talking, let’s get back to code. Now let’s make a new component called Header.js and let’s make a new file and call it Header.css just as we did with the home component. In each component, we will follow the same steps
We have to initialize the component boiler plate using “rfce” and follow the BEM convention and include the CSS file and update the class names.
We have the component ready. Before we actually start designing it, we need to include it in Router so that we can actually display it. In App.js where you mentioned Route for “/” route, let’s include the Header component in it too. Your updated route should look like this
<Route path="/">
  <Header />
  <Home />
</Route>
Remember you place Navbar before the Home component, because the Amazon Navbar is always at the top.
Now finally let’s get back to Header.js and start setting up the layout of our classic Amazon Navbar. The code in your Header.js should look like this. We would go through the entire code after the code block.

Before moving on to tearing this apart on what’s exactly going on, let’s just also grab the Header.css file so that the styling part is done.

Now the time to tear apart what we are exactly doing in the above two gigantic pieces of code
We made a Navbar for Amazon Clone. In the first code block we laid out the layout. It’s just like basic HTML but in React we call it JSX.
We set up that we want the Amazon logo at the left, the search bar at the center, and the other options at right which we then make happen with our CSS files
We have used Material UI icons in the Navbar too, like the Search Icon and the Basket icons, they were imported from the Material UI Icons package.
In the CSS, we basically set the display property of the Navbar to flex so that the items align next to each other, we changed the background colors, we tweaked the search box and then we styled the options.
Once you’ve done this, you will see a Navbar like this

