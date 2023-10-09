#  React Components 🧱

![Intro to React Components - Scaler Topics](https://www.scaler.com/topics/images/intro-to-react-components_thumbnail.webp)

## Objectives 🎯

-   Understand the concept of React components and their role in building user interfaces.
-   Learn how to create functional and class components in React.
-   Explore the use of props and state to manage data within components.
-   Gain insight into the lifecycle of React components and how to use lifecycle methods effectively.
-   Master the JSX syntax for creating dynamic and interactive UIs.

## Key Topics 📝

1.  📦 Creating Functional and Class Components:
    
    -   Learn the difference between functional and class components.
    -   Create functional components for simple UI elements.
    -   Build class components for more complex functionality.
2.  🌟 Props and State:
    
    -   Explore the use of props to pass data from parent to child components.
    -   Understand the concept of state for managing dynamic data within a component.
    -   Learn when to use props and state in your application.
3.  🌐 Component Lifecycle Methods:
    
    -   Dive into the lifecycle of a React component, including mounting, updating, and unmounting phases.
    -   Explore common lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
    -   Understand how to use these methods for tasks like data fetching and cleanup.
4.  📏 JSX Syntax:
    
    -   Master the JSX syntax for combining HTML-like elements with JavaScript expressions.
    -   Learn how to create dynamic UI components using JSX.
    -   Practice using JSX to render data and handle user interactions.

Day 2 will deepen your understanding of React components, from their creation and management of data to their lifecycle and rendering using JSX. Get ready to level up your React skills! 🚀

# 📦 Creating Functional and Class Components
![Overview of React.js](https://www.patterns.dev/img/reactjs/react-components@1.5x.svg)

## Understanding the Difference 🤔

In React, components are the building blocks of your application's user interface. They can be created in two primary ways: functional components and class components.

### Functional Components 📦

Functional components are the simpler of the two. They are JavaScript functions that return React elements (usually in the form of JSX). Functional components are ideal for rendering UI elements that don't require internal state or lifecycle methods.

**Example of a Functional Component:**

``` jsx
import React from 'react';

// A functional component
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default Greeting;
```

### Class Components 🧩

Class components, on the other hand, are more feature-rich. They are JavaScript classes that extend the `React.Component` class and have access to state and lifecycle methods. Use class components when you need to manage complex state or perform side effects.

**Example of a Class Component:**

``` jsx
import React, { Component } from 'react';

// A class component
class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Increment
        </button>
      </div>
    );
  }
}

export default Counter;
```

## When to Use Each Component 📊

-   **Functional Components**: 📦
    
    -   Use functional components for simple UI elements that are primarily concerned with rendering.
    -   They are the recommended choice for building "dumb" or presentational components that only receive data as props and display it.
    -   Functional components are easier to read and test.
-   **Class Components**: 🧩
    
    -   Use class components when you need to manage component state or utilize lifecycle methods.
    -   They are suitable for more complex components that require internal logic, state management, and side effects.
    -   Class components are traditionally used for container components.

In modern React development, functional components have gained popularity due to the introduction of React Hooks, which allow functional components to manage state and lifecycle effectively. However, class components are still essential for certain scenarios, especially in older codebases.

By understanding when to use each type of component, you'll be better equipped to structure your React applications efficiently. 🚀

# 🌟 Props and State

![How to update the state of a sibling component in React? | Alex Sidorenko](https://alexsidorenko.com/static/55e5f8c3513e625d38aac907319a4f37/f058b/prop-2.png)

In React, understanding the concepts of props and state is crucial for building dynamic and interactive user interfaces. Let's dive into these concepts:

## Exploring Props 🎁

**Props**, short for properties, are a way to pass data from parent components to child components. They allow you to make your components reusable and versatile.

-   **Passing Data**: You can pass data as props when you render a component. For example:
``` jsx
// Parent component
function App() {
  return <ChildComponent name="John" />;
}

// Child component
function ChildComponent(props) {
  return <p>Hello, {props.name}!</p>;
}
```

-   **Immutable**: Props are immutable, which means they cannot be modified by the child component that receives them.
    
-   **Custom Data**: You can pass any data, including strings, numbers, objects, or even functions, as props.
    

## Understanding State 📈

**State** is used to manage dynamic data within a component. Unlike props, which are passed down from parents, state is managed internally by the component.

-   **Setting Initial State**: In a class component, you initialize state in the constructor:
``` jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }
}
```

-   **Updating State**: You can update state using `setState()`. It merges new data into the existing state:
``` jsx
this.setState({ count: this.state.count + 1 });
```

-   **Reactive UI**: When state changes, React re-renders the component, updating the UI to reflect the new state.

## When to Use Props and State 🤔

-   **Props** are used when you need to pass data from a parent component to a child component. They are read-only for the child component and are typically used for configuration and data sharing.
    
-   **State** is used to manage data that can change over time within a component. It is mutable and allows you to build interactive and dynamic UIs.
    

Understanding when to use props and state is key to building well-structured React applications. Combining them effectively empowers you to create complex and responsive user interfaces. 🌟

# 🌐 Component Lifecycle Methods

![How to understand a component's lifecycle methods in ReactJS](https://cdn-media-1.freecodecamp.org/images/1*_drMYY_IEgboMS4RhvC-lQ.png)

In React, components have a lifecycle that consists of various phases, including mounting, updating, and unmounting. Understanding these phases and the associated lifecycle methods is crucial for controlling component behavior and performing tasks like data fetching and cleanup.

## Diving into the Lifecycle 🏊

A React component's lifecycle can be categorized into three main phases: Mounting, Updating, and Unmounting. Let's explore each phase in detail:

### Mounting Phase 🏔️

In the Mounting phase, a component is being created and inserted into the DOM.

-   **constructor()**: This method is called first when a component is created. It's used for initializing state and binding event handlers. Example:

``` jsx
constructor(props) {
  super(props);
  this.state = { count: 0 };
}
```

-   **render()**: This is where the component's UI is defined. It returns the JSX that will be displayed on the page. Example:
``` jsx
render() {
  return <div>Count: {this.state.count}</div>;
}
```

-   **componentDidMount()**: After the component is rendered and inserted into the DOM, this method is called. It's often used for data fetching, setting up subscriptions, or interacting with the DOM. Example:
```

componentDidMount() {
  // Fetch data from an API
  fetch('https://api.example.com/data')
    .then((response) => response.json())
    .then((data) => this.setState({ data }));
}
```

### Updating Phase 🔄

The Updating phase occurs when a component's state or props change.

-   **componentDidUpdate()**: This method is called after a component updates, either due to changes in state or props. It's useful for responding to changes and performing additional tasks. Example:
``` jsx
componentDidUpdate(prevProps, prevState) {
  if (this.props.id !== prevProps.id) {
    // Perform some action when props change
  }
}
```

### Unmounting Phase 🚀

The Unmounting phase occurs when a component is being removed from the DOM.

-   **componentWillUnmount()**: This method is called just before a component is unmounted. It's used for cleanup tasks, such as unsubscribing from subscriptions or canceling network requests. Example:
``` jsx
componentWillUnmount() {
  // Clean up resources
  clearInterval(this.intervalID);
}
```

## Practical Use Cases 🧰

Understanding component lifecycle methods enables you to perform tasks such as:

-   Fetching data when a component is first mounted.
-   Updating the UI in response to prop or state changes.
-   Managing cleanup and resource release when a component is unmounted.

By utilizing these methods effectively, you can create responsive and well-behaved React components that interact with data and the DOM efficiently. 🌐

# 📏 JSX Syntax

![The Difference Between React and JSX | Upbeat Code](https://www.upbeatcode.com/static/fbd35603b6d4c249baf0b479559175be/c40af/what-is-jsx.png)

JSX, short for JavaScript XML, is a syntax extension for JavaScript commonly used in React. It allows you to write HTML-like elements within your JavaScript code, making it easy to create dynamic and interactive UI components.

## Mastering JSX Basics 📚

JSX syntax resembles HTML but is used within JavaScript functions or classes. Here are some key points to master:

-   **Embedding JSX**: You can embed JSX directly within your JavaScript code using curly braces `{}`.
``` jsx
const element = <h1>Hello, World!</h1>;
```

- **JSX Expressions**: JSX can contain JavaScript expressions enclosed in curly braces `{}`.

``` jsx
const name = 'John';
const element = <h1>Hello, {name}!</h1>;
```

- **Self-Closing Tags**: Just like in HTML, you can use self-closing tags in JSX.
``` jsx
const image = <img src="image.jpg" alt="An image" />;
```
## Creating Dynamic UI Components 🧩

JSX allows you to create UI components that can dynamically render data and respond to user interactions. Here are some examples:

-   **Rendering Data**: Use JSX to display dynamic data.
``` jsx
const user = { name: 'Alice', age: 30 };
const element = <p>Name: {user.name}, Age: {user.age}</p>;
```

- **Conditional Rendering**: JSX can be combined with conditional statements to render different content based on conditions.

``` jsx
const isLoggedIn = true;
const greeting = isLoggedIn ? <p>Welcome, User!</p> : <p>Please log in.</p>;
```

## Handling User Interactions 🙌

JSX is not limited to displaying data; it can also handle user interactions through event listeners.

-   **Event Handling**: Attach event handlers to JSX elements.
``` jsx
function handleClick() {
  alert('Button clicked!');
}

const button = <button onClick={handleClick}>Click me</button>;
```

- **Forms and Input**: Create forms and input fields to gather user input.
``` jsx
function handleSubmit(event) {
  event.preventDefault();
  const formData = new FormData(event.target);
  // Process form data
}

const form = (
  <form onSubmit={handleSubmit}>
    <input type="text" name="username" />
    <button type="submit">Submit</button>
  </form>
);
```

## Practice, Practice, Practice! 🏋️‍♂️

The best way to master JSX is through practice. Experiment with different JSX elements, render data, handle user interactions, and build dynamic UI components. JSX is a powerful tool that simplifies the creation of complex user interfaces in React. 📏

# **Activity: Building a Dynamic User Profile Card 🧑**

**Objective:** Create a dynamic user profile card component that displays user information and allows users to update their age.

**Requirements:**

-   Basic knowledge of React components, props, state, and JSX.
-   A code editor and a React development environment set up. 📝

**Instructions:**

1.  **Create a React App**: If you haven't already, create a new React app using Create React App or your preferred setup method. 🚀
    
2.  **Create a User Profile Component**: Create a new component called `UserProfileCard.js`. This component will be responsible for displaying user information and allowing the user to update their age. 🧑
``` jsx
// UserProfileCard.js
import React, { useState } from 'react';

function UserProfileCard() {
  const [user, setUser] = useState({
    name: 'John Doe',
    age: 30,
  });

  const handleAgeChange = (e) => {
    setUser({ ...user, age: parseInt(e.target.value, 10) });
  };

  return (
    <div>
      <h2>User Profile</h2>
      <p>Name: {user.name}</p>
      <p>Age: {user.age}</p>
      <input
        type="number"
        placeholder="Enter new age"
        value={user.age}
        onChange={handleAgeChange}
      />
    </div>
  );
}

export default UserProfileCard;
```

3.  **Set Up State**: In the `UserProfileCard` component, we set up an initial state object for the user's data using the `useState` hook. 📦
    
2.  **Render User Information**: We render the user's name and age using JSX, with age being a dynamic value from our state. 📝
    
3.  **Add an Input Field**: We add an input field that allows the user to enter a new age. 📊
    
4.  **Event Handling**: We attach an `onChange` event handler to the input field. When the user enters a new age, we update the component's state to reflect the new age value. 📝
    
5.  **Conditional Rendering**: You can implement conditional rendering to display a message when the age is updated. For example:
``` jsx
// Inside UserProfileCard component
{user.age !== 30 && <p>Age updated to {user.age}!</p>}
```

8.  This will display a message when the age is updated. 🙌
    
2.  **Styling**: Style your `UserProfileCard` component using CSS or a CSS-in-JS solution like Styled Components to make it visually appealing. 🎨
    
3.  **Test Your Component**: Create an instance of your `UserProfileCard` component in the main app component and pass user data as props to it. Test whether the component correctly displays user information and updates the age. 🧪
    

### Here's how you can use it in your main app component:

``` jsx
// App.js
import React from 'react';
import UserProfileCard from './UserProfileCard';

function App() {
  return (
    <div className="App">
      <UserProfileCard />
    </div>
  );
}

export default App;
```

Enjoy building your dynamic user profile card and practicing your React skills! Happy coding! 🚀

# Applications 🚀


1.  🏡 **Building User Interfaces**: Create interactive and visually appealing user interfaces for web applications.
    
2.  📄 **Rendering Data**: Display data fetched from APIs or databases on your web page.
    
3.  🔄 **Updating User Interfaces**: Dynamically update the UI when data changes, keeping the user experience smooth.
    
4.  📊 **Managing State**: Control and manage the application's state, allowing for data persistence and user interactions.
    
5.  🧩 **Reusable Components**: Build modular and reusable UI components that can be used throughout your application.
    
6.  🎯 **Conditional Rendering**: Display different content based on conditions, enhancing user interaction and personalization.
    
7.  🎨 **Styling Components**: Apply styles to components to make them visually appealing and in line with your application's design.
    
8.  📥 **Data Fetching**: Fetch data from external sources like APIs, databases, or other services to populate your application.
    
9.  🕰️ **Handling Component Lifecycles**: Execute specific actions at different points in a component's lifecycle, such as fetching data when a component mounts.
    
10.  🙌 **User Interactions**: Implement event handling to respond to user interactions, such as button clicks or form submissions.
    
11.  🚀 **Dynamic UIs**: Create dynamic user interfaces that adapt and change in response to user actions or external events.
    
12.  📜 **Form Handling**: Manage forms and input fields for user data input, validation, and submission.
    

These practical applications showcase the versatility and power of React.js in building modern web applications. Each concept contributes to creating engaging and responsive user experiences. 🚀

# Summary 🚀
-   📦 **Components**: Explored the fundamentals of functional and class components, the building blocks of React applications.
    
-   🎁 **Props and State**: Understood how to pass data from parent to child components using props and manage dynamic data within a component using state.
    
-   🏔️ **Component Lifecycle**: Dived into the lifecycle of a React component, including mounting, updating, and unmounting phases, and how to utilize lifecycle methods.
    
-   📏 **JSX Syntax**: Mastered JSX syntax, combining HTML-like elements with JavaScript expressions to create dynamic UI components.
    
-   🧰 **Practical Applications**: Discovered practical applications such as building user interfaces, handling data, and responding to user interactions, making web development more dynamic and engaging.
    

These concepts form the foundation for developing interactive and responsive web applications with React.js. 🚀

# 🧱 React Components - Quiz 🤔

1.  📦 What are the building blocks of React applications?
    
    -   a) Modules
    -   b) Components
    -   c) Functions
    -   d) Variables
    -   **Correct Answer:** b) Components 🎯
2.  🎁 In React, what is used to pass data from parent to child components?
    
    -   a) Functions
    -   b) Props
    -   c) State
    -   d) Variables
    -   **Correct Answer:** b) Props 🎯
3.  🏔️ Which phase of a React component's lifecycle occurs when the component is first inserted into the DOM?
    
    -   a) Mounting
    -   b) Updating
    -   c) Rendering
    -   d) Unmounting
    -   **Correct Answer:** a) Mounting 🎯
4.  📏 In JSX syntax, what are the curly braces `{}` used for?
    
    -   a) To create HTML elements
    -   b) To define component methods
    -   c) To embed JavaScript expressions
    -   d) To comment out code
    -   **Correct Answer:** c) To embed JavaScript expressions 🎯
5.  🧩 Which type of component in React is recommended for simple UI elements that don't require state or lifecycle methods?
    
    -   a) Class Components
    -   b) Functional Components
    -   c) Module Components
    -   d) Styled Components
    -   **Correct Answer:** b) Functional Components 🎯
6.  📄 What is used to manage dynamic data within a React component?
    
    -   a) Functions
    -   b) Props
    -   c) State
    -   d) Methods
    -   **Correct Answer:** c) State 🎯
7.  🔄 Which lifecycle method in React is called after a component is updated due to changes in props or state?
    
    -   a) componentDidMount
    -   b) componentDidUpdate
    -   c) componentWillMount
    -   d) componentWillUnmount
    -   **Correct Answer:** b) componentDidUpdate 🎯
8.  🎯 In React, what allows you to make your components reusable and versatile?
    
    -   a) Modules
    -   b) Props
    -   c) State
    -   d) Methods
    -   **Correct Answer:** b) Props 🎯
9.  🧰 What's the primary purpose of conditional rendering in React?
    
    -   a) To hide components from the DOM
    -   b) To display content based on conditions
    -   c) To create complex animations
    -   d) To increase component reusability
    -   **Correct Answer:** b) To display content based on conditions 🎯
10.  🎨 How can you apply styles to React components for a visually appealing user interface?
    

     -   a) Using React props
     -   b) Using HTML `<style>` tags
     -   c) Using CSS-in-JS solutions like Styled Components
     -   d) Using JavaScript `style` objects
     -   **Correct Answer:** c) Using CSS-in-JS solutions like Styled Components 🎯

11.  🚀 Which React lifecycle method is used for cleanup tasks like unsubscribing from subscriptions or canceling network requests?
    
     -   a) componentWillMount
     -   b) componentDidUpdate
     -   c) componentWillUnmount
     -   d) componentDidUnmount
     -   **Correct Answer:** c) componentWillUnmount 🎯
12.  📝 In React JSX, what do you use to embed JavaScript expressions within curly braces?
    
     -   a) `<% %>`
     -   b) `{= =}`
     -   c) `{}` (e.g., `{data}`)
     -   d) `[[ ]]`
     -   **Correct Answer:** c) `{}` (e.g., `{data}`) 🎯
13.  📊 What type of component is ideal for managing complex state, handling user interactions, and performing side effects in React?
    
     -   a) Functional Components
     -   b) Class Components
     -   c) Stateful Components
     -   d) Stateless Components
     -   **Correct Answer:** b) Class Components 🎯
14.  🎯 In React, which technique allows you to re-render a component when its state or props change?
    
     -   a) Rebooting
     -   b) Rebinding
     -   c) Re-rendering
     -   d) Reconciliation
     -   **Correct Answer:** c) Re-rendering 🎯
15.  🏋️‍♂️ What's the main benefit of creating reusable React components?
    
      -   a) Faster application development
      -   b) Smaller bundle size
     -   c) Better SEO optimization
      -   d) Improved security
     -   **Correct Answer:** a) Faster application development 🎯
16.  🙌 In React, how can you handle user interactions like button clicks?
    
     -   a) Using jQuery
     -   b) Using `setState()`
     -   c) Using global variables
     -   d) Using inline HTML attributes
     -   **Correct Answer:** b) Using `setState()` 🎯
17.  🚀 What phase of the component lifecycle is associated with fetching data from an API?
    
     -   a) Mounting
     -   b) Updating
     -   c) Rendering
     -   d) Unmounting
     -   **Correct Answer:** a) Mounting 🎯
18.  📄 What is the purpose of the `componentDidUpdate` lifecycle method in React?
    
     -   a) Initializing component state
     -   b) Cleaning up resources before unmounting
     -   c) Fetching data from an API
     -   d) Responding to changes in props or state
     -   **Correct Answer:** d) Responding to changes in props or state 🎯
19.  🎨 Which approach is commonly used for styling React components by writing CSS styles in JavaScript?
    
     -   a) Inline styles
     -   b) External CSS files
     -   c) Sass or Less preprocessing
     -   d) HTML `<style>` tags
     -   **Correct Answer:** a) Inline styles 🎯
20.  📊 In React, which method is used to update the state of a class component?
    
     -   a) `this.updateState()`
     -   b) `this.setState()`
     -   c) `this.stateUpdate()`
     -   d) `this.update()`
     -   **Correct Answer:** b) `this.setState()` 🎯
21.  🧪 What is the purpose of testing a React component?
    
     -   a) To make the component look better
     -   b) To improve component reusability
     -   c) To ensure that the component behaves correctly
     -   d) To increase the component's download speed
     -   **Correct Answer:** c) To ensure that the component behaves correctly 🎯
22.  🏔️ In the React component lifecycle, which method is called first?
    
     -   a) `render()`
     -   b) `componentDidMount()`
     -   c) `constructor()`
     -   d) `componentDidUpdate()`
     -   **Correct Answer:** c) `constructor()` 🎯
23.  🧰 What's the primary purpose of a functional component in React?
    
     -   a) Managing complex state
     -   b) Handling user interactions
     -   c) Displaying simple UI elements
     -   d) Optimizing bundle size
     -   **Correct Answer:** c) Displaying simple UI elements 🎯
24.  🌟 What do you use in React to pass data from a parent component to a child component?
    
     -   a) Props
     -   b) State
     -   c) Variables
     -   d) Functions
     -   **Correct Answer:** a) Props 🎯
25.  📏 What is JSX used for in React?
    
     -   a) To create HTML elements
     -   b) To write CSS styles
     -   c) To manage component state
     -   d) To combine HTML-like elements with JavaScript expressions
     -   **Correct Answer:** d) To combine HTML-like elements with JavaScript expressions 🎯


🚀 "On Day 2 of your React journey, you've laid a solid foundation with components, props, state, and JSX. Keep building and experimenting—each day brings you closer to React mastery. Happy coding! 🌟"




