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


# Componentizing our React app
https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components

At this point, our app is a monolith. Before we can make it do things, we need to break it apart into manageable, descriptive components. 
React doesn't have any hard rules for what is and isn't a component – that's up to you! In this article we will show you a sensible way to break our app up into components.

At this point, our app is a monolith. Before we can make it do things, we need to break it apart into manageable, descriptive components.
React doesn't have any hard rules for what is and isn't a component - that's up to you ! In this article we will show you a sensible way to break our app up into 
components.


## Defining our first component
Defining a component can seem tricky until you have some practice, but the gist is:

If it represents an obvious "chunk" of your app, it's probably a component
If it gets reused often, it's probably a component.
That second bullet is especially valuable: making a component out of common UI elements allows you to change your code in one place and see those changes everywhere that component is used. You don't have to break everything out into components right away, either. Let's take the second bullet point as inspiration and make a component out of the most reused, most important piece of the UI: a todo list item.

Defining a component can seem tricky until you have some practice, but the gist is :

If it represents an obvious "Chunk" of your app, it's probably a component
If it gets reused often, it's probably a component .
That second bullet is especially valuable: making a component out of common UI elements allows you to change your code in one place and see those changes everywhere
that component is used. You don't have to break everything out into components right away, either. Let's take the second bullent point as inspiration and make a component out of the most reused, most important piece of the UI: a todo list item.

## Make a unique <Todo />
Components are powerful because they let us re-use pieces of our UI, and refer to one place for the source of that UI. The problem is, we don't typically want to reuse all of each component; we want to reuse most parts, and change small pieces. This is where props come in.

Components are powerful because they let us rel-use pieces of our UI, and refer to one place
for the source of that UI. The problem is, we don't typically want to reuse all of each component; we want to reuse most parts, and change small pieces.This is where props come in.

![alt text](image.png)


## What's in a name?
In order to track the names of tasks we want to complete, we should ensure that each <Todo /> component renders a unique name.
In App.jsx, give each <Todo /> a name prop. Let's use the names of our tasks that we had before:


//When your browser refreshes, you will see… the exact same thing as before. We gave our <Todo /> some props, but we aren't using them yet. Let's go back to Todo.jsx and remedy that.

First modify your Todo() function definition so that it takes props as a parameter. You can console.log() your props if you'd like to check that they are being received by the component correctly.

Once you're confident that your component is getting its props, you can replace every occurrence of Eat with your name prop by reading props.name. Remember: props.name is a JSX expression, so you'll need to wrap it in curly braces.

Putting all that together, your Todo() function should read like this:

When your browser refreshes, you will see... the exact same thing as before.We gave our <Todo /> some props, but 
we aren't using them yet.Let's go back to Todo. jsx and remedy that.
First modify your Todo() function definition so that it takes props as a parameter.You can console.log()
your props if you'd like to check that they are being received by the component correctly.

Once you're confident that your component is getting its props, you can replace every occurrence of Eat with your name prop by reading props.name. Remember: props.name is a JSX expression, so you'll need to wrap it in curly braces.
Putting all that together, your Todo()function should read like this.

# Is it completed?
In our original static list, only Eat was checked. Once again, we want to reuse most of the UI that makes up a <Todo /> component, but change one thing. That's a good job for another prop! Give your first <Todo /> call a boolean prop of completed, and leave the other two as they are.

Is it completed?
In our original static list, only Eat was checked. Once again, we want to reuse most of the UI that makes up a 
<Todo /> component, but change one thing. That's a good job for another prop! Give your first <Todo /> call a boolean prop of completed, and leave the other two as they are.

If you change each <Todo /> component's completed prop, your browser will check or uncheck the equivalent rendered checkboxes accordingly.

If you change each <Todo />component's completed prop, your browser will check or uncheck the equivalent rendered checkboxes accordingly.

Gimme some id, please
We have still another problem: our <Todo /> component gives every task an id attribute of todo-0. This is bad for a couple of reasons:
// id attributes must be unique (they are used as unique identifiers for document fragments,) by CSS, JavaScript, etc.).
When ids are not unique,the funcitonality of label elements can break.


id attributes must be unique (they are used as unique identifiers for document fragments, 
by CSS, JavaScript, etc.).
When ids are not unique, the functionality of label elements can break.

Note: The completed prop is last here because it is a boolean with no assignment. This is purely a stylistic convention. The order of props does not matter because props are JavaScript objects, and JavaScript objects are unordered.

Note: The completed prop is last here because it is a boolean with no assignment . This is purely a stylistic convention.
The order of props does not matter because props are JavaScript objects, and JavaScript objects are unordered.

We can clean up our code with one of JavaScript's core abilities: iteration. To use iteration, we should first re-think our tasks.

We can clean up our code with one of JavaScript's core abilities: iteration. To use iteration, we should first
re-think our tasks.



、、Note: ALL_CAPS constant names have no special meaning in JavaScript; they're a convention that tells other developers "this data will never change after being defined here".
Note: All_CAPS constant names have no special meaning in JavaScript ; they're a convention that tells other developers "this data will never change after being defined here".

JSX
Copy to Clipboard
<ul
  role="list"
  className="todo-list stack-large stack-exception"
  aria-labelledby="list-heading">
  {taskList}
</ul>
This gets us some of the way towards showing all the components again, but we've got more work to do: the browser currently renders each task's name as plain text. We're missing our HTML structure — the <li> and its checkboxes and buttons!

//This gets us some of the way towards showing all the components again, but we've got more work to do: the browser
currently renders each task's name as plain text. We're missing our HTML structure -the <li> and its checkboxes and buttons!

![alt text](image-1.png)

Now the app looks like it did before, and our code is less repetitive.

Now the app looks like it did before, and our code is less repetitive.

## Unique keys
You should always pass a unique key to anything you render with iteration. Nothing obvious will change in your browser, but if you do not use unique keys, React will log warnings to your console and your app may behave strangely!

You should always pass a unique key to anything you  render with iteration. Nothing obvious will change in your 
browser, but if you do not use unique keys, React will log warnings to your console and your app may behave strangely!

With this in place, your React app should render basically the same as it did before, but using your shiny new components.
With this in place, your React app should render basically the same as it did before,but using your shiny new 
components.
在编程中,`vanilla`这个词通常用来指**纯净、原生、未经修改的**代码或框架。

具体来说:

1. **Vanilla JavaScript**:
   - 指纯粹使用 JavaScript 语言,没有使用任何第三方库或框架(如 jQuery、React、Angular 等)。
   - 这种 JavaScript 代码是没有任何依赖和附加功能的基础 JavaScript 代码。

2. **Vanilla CSS**:
   - 指纯粹使用 CSS 语言,没有使用任何 CSS 预处理器(如 Sass、Less、Stylus)或 CSS 框架(如 Bootstrap、Foundation)。
   - 这种 CSS 代码是没有任何复杂功能的基础 CSS 代码。

3. **Vanilla Web Development**:
   - 指不使用任何 JavaScript 框架或库,只使用原生 JavaScript 进行 Web 开发。
   - 这种开发方式更加关注基础知识和底层原理,不依赖任何框架或库的功能。

使用 vanilla 方式有以下优点:

- **更轻量**: 没有框架或库的额外代码,网页加载更快。
- **更灵活**: 不受框架或库的限制,可以根据需求进行定制开发。
- **更易维护**: 代码结构更清晰,更容易理解和维护。
- **更易学**: 学习原生 JavaScript 和 CSS 是掌握 Web 开发基础的关键。

当然,使用框架或库也有其优点,如提高开发效率、添加更多功能等。因此,实际开发中需要根据具体需求,权衡使用 vanilla 还是框架的利弊。

<button type="button" onClick={() => alert("hi!")}>
  Say hi!
</button>

<button type="button" onClick={() =>alert("hi!")}>
Say hi!
</button>
In this example, we're adding an onClick attribute to the <button>element. The value of that attribute is a function that triggers a simple alert. This may seem counter to best practice advice about not writing event listeners in HTML, but remember: JSX is not HTML.
The camel-cased nature of onClick is important - JSX will  not recognize onclick (again,it is already used in JavaScript for a specific purpose, which is related but different - standard onclick handler properties).
All browser events follow this format in JSX-on, followed by the name of the event.
Let's apply this to our app, starting in the Form.jsx component.

## Persisting and changing data with state
So far, we've used props to pass data through our components and this has served us just fine. Now that we're dealing with interactivity, however, we need the ability to create new data, retain it, and update it later. Props are not the right tool for this job because they are immutable — a component cannot change or create its own props.
--**Props**-- are not the right tool for this job because they are immutable - a component cannot change or create its own props.

This is where state comes in. If we think of props as a way to communicate between components, we can think of state as a way to give components "memory" – information they can hold onto and update as needed.

React provides a special function for introducing state to a component, aptly named useState().
This is where state comes in. If we think of props as a way to communicate between components, we can think of state as a way to gibe components "memory - information they can hold onto and update as needed.

Note: useState() is part of a special category of functions called hooks, each of which can be used to add new functionality to a component. We'll learn about other hooks later on.

Note: useState() is part of special category of functions called hooks, each of which can be used to add new functionality to a component. 

useState() takes a single argument that determines the initial value of the state. This argument can be a string, a number, an array, an object, or any other JavaScript data type. useState() returns an array containing two items. The first item is the current value of the state; the second item is a function that can be used to update the state.

Let's create a name state. Write the following above your handleSubmit() function, inside Form():

// useState() takes a single argument that determines the initial value of the state. This argument can be a string, a number ,an array, an object, or any other JavaScript data type. useState() returns an array containing two items. The first item is the current value of the state; the second item is a function that can be used to update the state.
const [name, setName] = useState("Learn React");


//Several things are happening in this line of code:

We are defining a name constant with the value "Learn React".
We are defining a function whose job it is to modify name, called setName().
useState() returns these two things in an array, so we are using array destructuring to capture them both in separate variables.
// Several things are happening in this line of code:
We are defining a name constant with the value "Learn React".
We are defining a function whose job it is to modify name, called setName().
useState() returns these two things in an array, so we are suing array destructuring to capture them both in separate variables.


Change "Learn React" to an empty string once you're done; this is what we want for our initial state:


const [name, setName] = useState("");

Change "Learn React" to an empty string once you're done; this is what we want for our initial state:
const [name, setName] = useState("");


# Updating state
Logging isn't enough - we want to actually store what the user types and render it in the input! change your 
console.log() call to setName(), as shown below:
Logging isn't enough — we want to actually store what the user types and render it in the input! Change your console.log() call to setName(), as shown below:

function handleChange(event) {
  console.log(event.target.value);
}



Note: You'll notice that you are able to submit empty tasks by just pressing the Add button without entering a task name. Can you think of a way to prevent this? As a hint, you probably need to add some kind of check into the handleSubmit() function.

Note: You'll notice that  you are able to submit empty tasks by just pressing the Add button without entering a task
name. Can you think of a way to prevent this?

## Putting it all together: Adding a task
Now that we've practiced with events, callback props, and hooks, we're ready to write functionality that will allow a user to add a new task from their browser.##

Now that we've practiced with events, callback props, and hooks, we're ready to write functionality that will allow a user to add a new task from their browser.

We need to fix this. Making unique identifiers i
s a hard problem – one for which the JavaScript community has written some helpful libraries. We'll use nanoid because it's tiny and it works.

Make sure you're in the root directory of your application and run the following terminal command:

This javaScript nanoid library is important
## Completing a task

You might notice that, when you click on a checkbox, it checks and unchecks appropriately. As a feature of HTML, the browser knows how to remember which checkbox inputs are checked or unchecked without our help. 
//This feature hides a problem, however: toggling a checkbox doesn't change the state in our React application. This means that the browser and our app are now out-of-sync. We have to write our own code to put the browser back in sync with our app.

This feature hides a problem, however: toggling a checkbox doesn't change the state in our React application.
This means that the browser and our app are now out-of -sync. We have to write our own code to put the browser back in sync with our app.

# Summary
That's enough for one article. Here we've given you the lowdown on how React deals with events and handles state, and implemented functionality to add tasks, delete tasks, and toggle tasks as completed. We are nearly there. In the next article we'll implement functionality to edit existing tasks and filter the list of tasks between all, completed, and incomplete tasks. We'll look at conditional UI rendering along the way.
That's enough for one article. Here we've given you the lowdown on how React deals with events and handles state, and implemented functionality to add tasks, delete tasks, and toggle tasks as completed. We are nearly there. In the next article we'll implement functionality to edit existing tasks and filter the list of tasks between all, 
completed, and incomplete tasks. 

# React interactivity: Editing, filtering, conditional rendering
review the We'll use Array.prototype.map() instead of Array.prototype.filter()  and spread 


We've now got the two different template structures-"edit" and "view"- defined inside two separate constants.
This means that the return statement of <Todo /> is now repetiious -it also contains a definition of the "view"
template.We can clean this up by using conditional rendering to determine which template the component returns,
and is therefore rendered in the UI.

# Toggling the <Todo /> templates


Note: We are defining these constants outside our App() function because if they were defined inside it, they would
be recalculated every time the <App /> component re-renders, and we don't want that. This information will never change no matter what our application does.
