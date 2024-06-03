# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh


## Note
The App.jsx file consists of three main parts: some import statements at the top, the App() function in the middle, and an export statement at the bottom. Most React components follow this pattern.
The App.jsx file consists of three main parts: some import statements at the top, the App() function in the middle, and an export statement at the bottom. Most React components follow this pattern

# Import statements
The import statements at the top of the file allow App.jsx to use code that has been defined elsewhere. Let's look at these statements more closely.

The import statements at the top of the file allow App.jsx to use code that has been defined elsewhere. Let's look at these
statements more closely.

import { useState } from "react";
import reactLogo from "./assets/react.svg";
import viteLogo from "/vite.svg";
import "./App.css";


import { useState} from "react";
import reactLogo from "./assets/react.svg";
import viteLogo from "/vite.svg";
import "./App.css";


The first statement imports the useState hook from the react library. Hooks are a way of using React's features inside a component. We'll talk more about hooks later in this tutorial.

After that, we import reactLogo and viteLogo. Note that their import paths start with ./ and / respectively and that they end with the .svg extension at the end. This tells us that these imports are local, referencing our own files rather than npm packages.

The final statement imports the CSS related to our <App /> component. Note that there is no variable name and no from directive. This is called a side-effect import — it doesn't import any value into the JavaScript file, but it tells Vite to add the referenced CSS file to the final code output, so that it can be used in the browser.

The first statement    statement imports the useState hook from the react libray. Hooks are a way of using React's features inside a component. We'll talk more about hooks later in this tutorial.
After that, we import reactLogo and vitelogo. Note that their import paths start with ./and / respectively and that they end with the .svg extension at the end. This tells us that these imports are local, referencing our own files rather than npm packages.

The final statement imports the CSS relaated to our<App /> component.Note that there is no variable name and no from directive. This is called a side-effect import - it doesn't import any value into the JavaScript file, but it tells Vite to add the referenced CSS file to the final code outpu, so that it can be used in the browser.

The App() function
After the imports, we have a function named App(), which defines the structure of the App component. Whereas most of the JavaScript community prefers lower camel case names like helloWorld, React components use Pascal case (or upper camel case) variable names, like HelloWorld, to make it clear that a given JSX element is a React component and not a regular HTML tag. If you were to rename the App() function to app(), your browser would throw an error.

Let's look at App() more closely.

The App() function 
After the imports, we have a function named APp(),which defines the structure of the App component. Whereas most of the JavaScript community prefers lower camel case names like helloWorld, React components use Pascal case (or upper camel case variable names, like HelloWorld, to make it clear that a given JSX element is a React component and not a regular HTML tag. If you were to rename the App() function to app(), your browser would throw an error.)

The App() function returns a JSX expression. This expression defines what your browser ultimately renders to the DOM.

Just under the return keyword is a special bit of syntax: <>. This is a fragment. React components have to return a single JSX element, and fragments allow us to do that without rendering arbitrary <div>s in the browser. You'll see fragments in many React applications.

Just under the return keyword is a special bit of syntax:<>.This is a fragment. React components have to return a single
JSX element, and fragments allow us to do that without rendering arbitrary <div>s in the browser.You'll see fragments in many
React applications.

The export statement
There's one more line of code after the App() function:

JSX
Copy to Clipboard
export default App;
This export statement makes our App() function available to other modules. We'll talk more about this later.

Moving on to main
Let's open src/main.jsx, because that's where the <App /> component is being used. This file is the entry point for our app, and it initially looks like this:

## Moving on to main
Let's open src/main.jsx, because that's where the <App />component is being used . This file is the entry point for our app,
and it initially looks like this:

The first two statements import the React and ReactDOM libraries because they are referenced later in the file. We don't write a path or extension when importing these libraries because they are not local files. In fact, they are listed as dependencies in our package.json file. Be careful of this distinction as you work through this lesson!

Note: <App /> is rendered inside a special <React.StrictMode> component. This component helps developers catch potential problems in their code.
Note: <App /> is rendered inside a special <React.StrictMode> component. This component helps developers catch potential 
problems in their code.

## Practice with JSX
Next, we'll use our JavaScript skills to get a bit more comfortable writing JSX and working with data in React. We'll talk about how to add attributes to JSX elements, how to write comments, how to render content from variables and other expressions, and how to pass data into components with props.

Next, we'll use our JavaScript skills to get a bit more comfortable writing JSX and working with data in React. We'll talk about how to add attributes to JSX elements, how to write comments, how to render content from variables and other expressions, and how to pass data into components with props.


Some attributes are different than their HTML counterparts. For example, the class attribute in HTML translates to className in JSX. This is because class is a reserved word in JavaScript, and JSX is a JavaScript extension. If you wanted to add a primary class to your button, you'd write it like this:

Some attributes are different than their HTML counterparts.For example, the class attribute in HTML translates to className in JSX.
This is because class is a reserved word in JavScript, and JSX is a JavaScript extension.If you wanted to add a primary class to your button, you'd write it like this:

## JavaScript expressions as content
Unlike HTML, JSX allows us to write variables and other JavaScript expressions right alongside our other content. Let's declare a variable called subject just above the App() function:
Unlike HTML, JSX allows us to write variables and other JavaScript expressions right alongside our other content.Let's declare a variable called subject just above the App() function:
