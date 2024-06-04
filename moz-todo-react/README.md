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



The curly braces around subject are another feature of JSX's syntax. The curly braces tell React that we want to read the value of the subject variable, rather than render the literal string "subject". You can put any valid JavaScript expression 
inside curly braces in JSX: React will evaluate it and render the result of the expression as the final content. Following is a series of examples, with comments above explaining what each expression will render:
{/* Hello, React :)! */}
<h1>Hello, {subject + ' :)'}!</h1>
{/* Hello, REACT */}
<h1>Hello, {subject.toUpperCase()}</h1>
{/* Hello, 4 */}
<h1>Hello, {2 + 2}!</h1>


Even comments in JSX are written inside curly braces! This is because comments, too, are technically JavaScript expressions. The /* block comment syntax */ is necessary for your program to know where the comment starts and ends.

Even comments in JSX are written inside curly braces! This is because comments, too, are technically JavaScript expressions.
The /* block comment syntax */ is necessary for your program to know where the comment starts and ends.

# Component props
Props are a means of passing data into a React component. Their syntax is indentical to that of attributes, in fact:
prop ="value". The difference is that whereas attributes are passed into plain elements, props are passed into React 
components.

In React, the flow of data is unidirectional: props can only be passed from parent components down to child components.

For additional practice, you could try adding an additional greeting prop to the <App /> component call inside main.jsx and using it alongside the subject prop inside App.jsx.
For additional practice ,you could try adding an additional greeting prop to the <App /> component call inside main.jsx and 
using it alongside the subject prop inside APP.jsx.
Components can import modules they need and must export themselves at the bottom of their files.
Component functions are named with PascalCase.
You can render JavaScript expressions in JSX by putting them between curyly braces, like {so}.

Some JSX attributes are different than HTML attributes so that they don't conflict with JavaScript reserved words. For example, class in HTML translates to className in JSX>
Props are written just like attributes inside component calls and are passed into components.
## beginning our React todo list
https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning

Let's say that we've been tasked with creating a proof-of-concept in React – an app that allows users to add, edit, and delete tasks they want to work on, and also mark tasks as complete without deleting them. This article will walk you through the basic structure and styling of such an application, ready for individual component definition and interactivity, which we'll add later.
## Our app's user stories
In software development, a user story is an actionable goal from the perspective of the user.Defining user stories before
we begin our work will help us focus our work. Our app should fulfill the following stories:
=
As a user, I can read a list of task. add a task using the mouse or keyboard. 
/mark any task as completed, using the mouse or keyboard.
delete any task, using the mouse or keyboard.
edit any task, using the mouse or keyboard.
View a specific subset of tasks:All tasks, only the active task, or only the completed tasks.
We'll tackle these stories ont-by-one.

、、Note: If you stopped your server to do the terminal tasks mentioned above, you'll have to start it again using npm run dev.
// Note: If you stopped your server to do the terminal tasks mentioned above , you'll have to start it agin 
using npm run dev.

Now open index.html and change the <title> element's text to TodoMatic. This way, it will match the <h1> at the top of our app.

Now open index.html and change the <title> element's text to TodoMatic. This way, it will math the <h1> at the top of our app.

It's ugly, and doesn't function yet, but that's okay — we'll style it in a moment. First, consider the JSX we have, and how it corresponds to our user stories:

We have a <form> element, with an <input type="text"> for writing out a new task, and a button to submit the form.
We have an array of buttons that will be used to filter our tasks.
We have a heading that tells us how many tasks remain.
We have our 3 tasks, arranged in an unordered list. Each task is a list item (<li>), and has buttons to edit and delete it and a checkbox to check it off as done.
The form will allow us to make tasks; the buttons will let us filter them; the heading and list are our way to read them. The UI for editing a task is conspicuously absent for now. That's okay – we'll write that later.

It's ugly, and doesn't  function yet, but that's okay - we'll style it in a moment. First, consider the JSX we have ,and how it corresponds to our user stories:

The class visually-hidden has no effect yet, because we have not included any CSS. Once we have put our styles in place, though, any element with this class will be hidden from sighted users and still available to assistive technology users — this is because these words are not needed by sighted users; they are there to provide more information about what the button does for assistive technology users that do not have the extra visual context to help them.

The class visually-hidden has no effect yet, because we have not included any CSS. Once we have put pur styles in place, though, any element with this class will be hidden from sighted users and still available to assistive technology users- this is because these words are not needed by sighted users; they are there to provide more information about what the button does for assistive technology users that do not have the extra visual context to help them.


The role attribute helps assistive technology explain what kind of element a tag represents. A <ul> is treated like a list by default, but the styles we're about to add will break that functionality. This role will restore the "list" meaning to the <ul> element. If you want to learn more about why this is necessary, you can check out Scott O'Hara's article, "Fixing Lists".

The role attribute helps assistive technology explain what kind of element a tag represents. A <ul> is treated like a list by default, but the styles we're about to add will break that functionality. This role will restore the "list" meaning to the  <ul> element. If you want to learn more about why this is necessary, you can check out Scott o'Hara's article, "Fixing Lists".



Note: The aria-pressed attribute used in our earlier code snippet has a value of "true" because aria-pressed is not a true boolean attribute in the way checked is.


Note: The aria-pressed attribute used in our earlier code snippet has a value of "true" because aria-pressed is not a true boolean attribute in the way checked is.

Note： The aria-pressed attribute used in our earlier code snippet has a value of "true" because aria-pressed is not a true boolean attribute in the way checked is/


Summary
Now our todo list app actually looks a bit more like a real app! The problem is: it doesn't actually do anything. We'll start fixing that in the next chapter!

Now our todo list app actually looks a bit more like a real app! The problem is : it doesn't actually do anything.We'll start fixing that in the next chapter!


















