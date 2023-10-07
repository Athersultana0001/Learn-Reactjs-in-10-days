# Introduction to React.js 🌐

![A Simple Introduction to React JS - DEV Community](https://res.cloudinary.com/practicaldev/image/fetch/s--C_RrV6UW--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/089ufl72giw5lc2t1sa1.png)

## Objectives 🎯

By the end of Day 1, you should:

-   Understand what React.js is and its role in web development.
-   Be able to set up a basic React.js environment for development.
-   Familiarize yourself with fundamental concepts of React.js.
-   Know how to navigate and utilize React.js documentation effectively.

## Key Topics 📝

### 🤔 What is React.js?

-   Definition and overview of React.js.
-   Why React.js is important in modern web development.
-   The Virtual DOM and its advantages.

### 🛠️ Setting up React.js

-   Installing Node.js and npm (Node Package Manager).
-   Creating a new React.js application using Create React App.
-   Understanding the project structure and files.

### 🌟 Basic React.js Concepts

-   Components: Building blocks of React.js applications.
-   JSX (JavaScript XML): Combining HTML and JavaScript in React.
-   Props and State: Managing data and passing information between components.
-   Component Lifecycle: Understanding the lifecycle methods.

### 📚 React.js Documentation

-   Navigating the official React.js documentation.
-   Finding answers to common questions and problems.
-   Learning resources and community support.


# 🤔 What is React.js?

![Introduction to ReactJS - DEV Community](https://res.cloudinary.com/practicaldev/image/fetch/s--w0VC-G5U--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nigommoqt57x17bwt8m3.png)



## Definition and Overview of React.js 📜

React.js, often referred to as React, is an open-source JavaScript library for building user interfaces (UIs) and single-page applications. It was developed and is maintained by Facebook, making it a robust and widely-used choice for web developers.

At its core, React.js is all about building reusable UI components. These components are like Lego pieces that you can assemble to create a complete web application. Each component encapsulates a piece of the user interface and its logic, making it easier to manage and maintain complex UIs.

## Why React.js is Important in Modern Web Development 🚀

React.js has gained immense popularity in modern web development for several reasons:

1.  **Component-Based Architecture 🧩**: React promotes a modular and component-based architecture. This allows developers to break down complex UIs into smaller, manageable pieces, making development more organized and efficient.
    
2.  **Virtual DOM (Document Object Model) 🕹️**: React uses a virtual representation of the DOM, known as the Virtual DOM. When changes occur in a React component, React creates a virtual copy of the DOM, compares it to the previous version, and updates only the parts that have changed. This approach significantly improves performance by minimizing actual DOM manipulation.
    
3.  **Reactive Updates ♻️**: React provides a simple and efficient way to update the UI in response to changes in data or user interactions. It automatically tracks data changes and efficiently re-renders only the affected components.
    
4.  **Community and Ecosystem 🌐**: React has a vast and active community, along with a rich ecosystem of libraries and tools (e.g., React Router for routing, Redux for state management). This ecosystem makes it easy to extend React's functionality and solve various development challenges.
    
5.  **Declarative Syntax 📝**: React uses a declarative syntax, allowing developers to describe how the UI should look based on the current state and data. This makes code more predictable and easier to understand.
    

## The Virtual DOM and Its Advantages 🌟

One of the key innovations in React.js is the Virtual DOM. Here's how it works and its advantages:

-   **Virtual DOM Basics 🌐**: React maintains a lightweight virtual representation of the actual DOM. When changes are made to a component, React first updates the virtual DOM, not the real one.
    
-   **Efficient Updates 🚀**: React then compares the new virtual DOM with the previous one, identifying the differences (or "diffs"). It updates only the parts of the real DOM that have changed, reducing unnecessary DOM manipulation and improving performance.
    
-   **Faster Rendering 🚄**: This approach results in faster rendering, especially for complex applications with dynamic content. React's intelligent handling of updates minimizes browser repaints and reflows.
    
-   **Improved User Experience 😃**: Faster rendering leads to a smoother user experience, as pages load quickly and respond seamlessly to user interactions.
    

With React's Virtual DOM, you can build blazing-fast web applications while maintaining a clean and organized codebase. 🌐

# 🛠️ Setting up React.js

![Setup React - Blog Post - codingforentrepreneurs.com](https://static.codingforentrepreneurs.com/media/cfe-blog/setup-react/setup_reactjs_logo.jpg)



## Installing Node.js and npm (Node Package Manager) 📦

Before we can start building with React.js, we need to ensure that you have Node.js and npm installed on your computer. These tools are essential for managing and running React applications.

### Step 1: Check if Node.js and npm are Installed

To check if Node.js and npm are already installed, open your terminal (command prompt or terminal emulator) and run the following commands:

``` bash
node -v
npm -v
```

These commands will display the installed Node.js and npm versions if they are already present. If not, you will need to install them.

### Step 2: Installing Node.js and npm

If Node.js and npm are not installed or if you need to update them to the latest versions, follow these steps:

#### For Windows:

1.  Download the Windows Installer for Node.js from the official website: [Node.js Downloads](https://nodejs.org/en/download/).
2.  Run the installer and follow the on-screen instructions.
3.  Once installed, open your terminal and run the previous `node -v` and `npm -v` commands to verify the installation.

#### For macOS:

1.  You can install Node.js and npm using [Homebrew](https://brew.sh/), a package manager for macOS.
    
   ```  bash
   brew install node
```

2.  After installation, verify by running `node -v` and `npm -v` in your terminal.
    

#### For Linux (Ubuntu/Debian):

1.  Use `apt-get` to install Node.js and npm.
``` bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
```

2.  Verify the installation with `node -v` and `npm -v`.
    

## Creating a New React.js Application using Create React App 🚀

Now that you have Node.js and npm installed, you can create a new React.js application with ease using Create React App, a popular React application generator.

### Step 1: Install Create React App Globally

Open your terminal and run the following command to install Create React App globally:

``` bash
npm install -g create-react-app
```

### Step 2: Create a New React Application

Once Create React App is installed, you can create a new React application with a single command:
``` bash
npx create-react-app my-react-app
```

Replace `my-react-app` with your desired project name. This command will set up a new React project for you.

## Understanding the Project Structure and Files 📂

After creating a new React application, it's essential to understand its structure and the purpose of each file and folder. Here's a brief overview:

-   📁 **node_modules**: This folder contains the dependencies required for your project. You don't need to manage these manually; npm takes care of it.
    
-   📄 **package.json**: This file lists your project's dependencies and scripts. You can add or update dependencies here.
    
-   📄 **src**: The source folder contains your application's source code. You'll spend most of your time here, working on components, styles, and logic.
    
-   📄 **public**: This folder contains static assets like HTML files and images. The `index.html` file is the entry point for your React application.
    
-   📄 **App.js**: The main React component representing your application. You'll define your UI and logic in this file.
    
-   📄 **index.js**: The entry point of your application where React is initialized and the main component is rendered.
    

With this setup, you're ready to start building your React application! 🚀

# 🌟 Basic React.js Concepts

![10 Main Core Concept You Need to Know About React | by Payal Paul | Medium](https://miro.medium.com/v2/resize:fit:1400/0*qQs51ezKqLD5xbXr.jpg)

## Components: Building Blocks of React.js Applications 🧩

In React.js, components are the fundamental building blocks of user interfaces. They allow you to break your UI into reusable, self-contained pieces. Components can be as simple as a button or as complex as an entire page.

**Example:**

``` jsx
import React from 'react';

// A simple functional component
function Button(props) {
  return <button>{props.label}</button>;
}

export default Button;
```

## JSX (JavaScript XML): Combining HTML and JavaScript in React 📝

JSX is a syntax extension for JavaScript that allows you to write HTML-like code within your JavaScript files. It makes your React components more readable and expressive.

**Example:**

``` jsx
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

const element = <Greeting name="John" />;
```

## Props and State: Managing Data and Passing Information Between Components 📦

-   **Props (Properties)**: Props are used for passing data from parent to child components. They are immutable and read-only within the child component.

**Example:**

``` jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

const element = <Welcome name="Alice" />;
```

-   **State**: State is used to manage data that can change over time and affect a component's behavior and rendering. Unlike props, state is mutable and can be changed.

**Example:**

``` jsx
import React, { Component } from 'react';

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

## Component Lifecycle: Understanding the Lifecycle Methods ⏳

React components have a lifecycle, which includes methods that are automatically called at different stages. These methods allow you to perform actions like fetching data, updating the UI, and cleaning up resources.

**Example:**

``` jsx
import React, { Component } from 'react';

class LifecycleDemo extends Component {
  constructor(props) {
    super(props);
    this.state = { data: null };
  }

  componentDidMount() {
    // Called after the component is inserted into the DOM
    // Ideal for making network requests
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => this.setState({ data }));
  }

  componentWillUnmount() {
    // Called before the component is removed from the DOM
    // Cleanup tasks go here
  }

  render() {
    return (
      <div>
        {this.state.data ? <p>Data: {this.state.data}</p> : <p>Loading...</p>}
      </div>
    );
  }
}

export default LifecycleDemo;
```

These are some of the essential concepts in React.js that you'll use frequently as you develop React applications. Understanding them is key to becoming proficient in React development! 🧩

# 📚 React.js Documentation

![A Guide to using JSDoc for React.js | Better Documentation in React](https://www.inkoop.io/static/banner-2e20c7d7ea0af826ae8ee40428861ed9.png)

## Navigating the Official React.js Documentation 🧭

The official React.js documentation is a treasure trove of information. It's essential to know how to navigate it effectively to find what you need:

1.  **Home Page**: Start at the [React.js official website](https://reactjs.org/). The home page provides a quick overview of React and links to essential sections.
    
2.  **Getting Started**: Look for a "Getting Started" or "Quick Start" section. It typically contains instructions on setting up a React development environment and creating your first React application.
    
3.  **API Reference**: The "API Reference" section is where you can explore React's core concepts, components, and functions in detail. It's organized into different categories for easy access.
    
4.  **Guides**: Guides offer in-depth explanations and examples for various React topics. They provide step-by-step instructions and best practices for common use cases.
    
5.  **Tutorials**: Check for tutorials that walk you through building complete applications with React. These tutorials often cover more advanced topics and real-world scenarios.
    
6.  **Blog**: React's blog can be a great source of updates, news, and insights from the React team. It's a good place to stay informed about the latest developments.
    

## Finding Answers to Common Questions and Problems 🤔

When you encounter issues or have questions while working with React, you can often find solutions and guidance in the documentation:

1.  **Search Bar**: Use the search bar on the documentation website to search for specific topics, functions, or error messages. It's a quick way to find relevant information.
    
2.  **FAQ (Frequently Asked Questions)**: Check if there's an FAQ section in the documentation. It often addresses common issues and questions faced by developers.
    
3.  **Troubleshooting**: Look for a "Troubleshooting" or "Common Problems" section. It can help you diagnose and resolve common React-related issues.
    
4.  **Community Discussions**: React has a dedicated community that actively discusses problems and solutions. You can find links to community forums, such as Stack Overflow and Reddit, in the documentation.
    

## Learning Resources and Community Support 🌐

Learning React is an ongoing process, and it's beneficial to have access to a supportive community and additional resources:

1.  **React Community**: The React community is active on various platforms. Join React-related forums, groups, or subreddits to ask questions, share knowledge, and connect with other developers.
    
2.  **Reactiflux**: Reactiflux is a community of React enthusiasts on Discord. It's a great place for real-time discussions and support.
    
3.  **Learning Paths**: Explore learning paths and tutorials recommended by the React team or experienced developers. These paths often include a curated list of resources for different skill levels.
    
4.  **YouTube and Online Courses**: Many online platforms offer React courses and tutorials. Websites like Udemy, Coursera, and YouTube have a wealth of video tutorials and courses.
    
5.  **Books**: Consider reading React-related books, such as "Learning React" by Alex Banks and "React Up and Running" by Stoyan Stefanov, for in-depth knowledge.
    

By effectively navigating the documentation and tapping into the React community, you'll have access to a vast pool of knowledge and support to enhance your React.js journey! 🌐


# Assignment 📝

## Step 1: Install Node.js and npm 📦

Node.js and npm are essential tools for developing React applications. Follow these steps to install them on your computer:

### For Windows:

1.  Download the Windows Installer for Node.js from the official website: [Node.js Downloads](https://nodejs.org/en/download/).
    
2.  Run the installer and follow the on-screen instructions.
    
3.  Once installed, open your terminal (Command Prompt or PowerShell) and verify the installation by running the following commands:

``` bash
node -v
npm -v
```

### For macOS:

1.  You can install Node.js and npm using [Homebrew](https://brew.sh/), a package manager for macOS.
    
   ```  bash
    `brew install node` 
```

2.  After installation, open your terminal and verify the installation by running the following commands:
    
   ``` bash
    `node -v
    npm -v` 
```
    

### For Linux (Ubuntu/Debian):

1. Use `apt-get` to install Node.js and npm.
``` bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
```

2. Verify the installation by running the following commands:
``` bash
node -v
npm -v
```

## Step 2: Create a New React.js Application 🚀

Now that you have Node.js and npm installed, let's create a new React application using Create React App:

1.  Open your terminal and run the following command to install Create React App globally:
``` bash
npm install -g create-react-app
```

2. Once installation is complete, create a new React application with a unique name. Replace `my-react-app` with your preferred project name:
``` bash
npx create-react-app my-react-app
```

3. Navigate to your project directory using the `cd` command:
``` bash
cd my-react-app
```

4. Start your React application:
``` bash
npm start
```
This will launch a development server, and you should see your new React app running in your web browser.
    

## Step 3: Experiment with JSX and Create a Simple React Component 📝

Now that you have a React application set up, let's experiment with JSX by creating a simple React component:

1.  Open the `src` directory in your project folder.
    
2.  Inside the `src` directory, you'll find a file called `App.js`. Open it using your code editor.
    
3.  Modify the `App.js` file to experiment with JSX. You can create a simple component, change text, or add HTML elements within the `return` statement.

``` jsx
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, React!</h1>
      <p>This is a simple React component.</p>
    </div>
  );
}

export default App;
```

4.  Save your changes. You should see the updates in your browser as the development server automatically reloads.

## Step 4: Explore the React.js Documentation 📚

Explore the official React.js documentation to find answers to three common questions or topics related to React. Use the documentation's search feature and navigate through relevant sections to find the information you need. Remember, the documentation is a valuable resource for learning React and solving problems.


# Applications 🚀

1.  🏡 **Building User Interfaces**: React.js is widely used for creating interactive and dynamic user interfaces in web applications. You can use it to design beautiful and responsive web pages.
    
2.  🚀 **Single-Page Applications (SPAs)**: React is the foundation for building SPAs, where a single HTML page dynamically updates and responds to user actions without requiring full-page reloads.
    
3.  🔄 **Real-time Updates**: React's ability to efficiently update and re-render components makes it suitable for real-time applications, such as social media feeds, chat applications, and live dashboards.
    
4.  📦 **Component Reusability**: React encourages the creation of reusable components. This is beneficial when you want to maintain a consistent design and functionality across your application.
    
5.  🌐 **Web Development Projects**: React is a popular choice for web development projects, from small personal websites to large-scale e-commerce platforms.
    
6.  📱 **Mobile Apps**: React Native, a framework built on React, enables you to build native mobile applications for iOS and Android using a single codebase.
    
7.  🎨 **User Interface Libraries**: React can be used to develop user interface libraries and design systems, making it easier to maintain a cohesive design across multiple applications.
    
8.  📡 **Fetching Data**: React can be integrated with APIs to fetch and display data in real-time. This is crucial for applications that rely on external data sources.
    
9.  🧪 **Testing and Debugging**: Understanding React's component lifecycle and state management is essential for effective testing and debugging of your applications.
    
10.  📚 **Continuous Learning**: React's popularity and rapid evolution mean that learning and mastering it can lead to exciting career opportunities and lifelong learning in web development.
    

These practical applications showcase how React.js can be used in various web development scenarios, making it a valuable skill for developers in today's digital world. 🌟

# Summary 🚀

-   **Introduction to React.js** 🌟:
    
    -   React.js is an open-source JavaScript library for building user interfaces (UIs) 🖥️.
    -   It's widely used in modern web development for creating dynamic and interactive applications 🚀.
-   **Setting up React.js** 🛠️:
    
    -   Install Node.js and npm (Node Package Manager) to manage dependencies 📦.
    -   Create a new React.js application using Create React App, a popular React application generator 📲.
    -   Understand the project structure and files in a typical React application 📂.
-   **Basic React.js Concepts** 🧩:
    
    -   Components are the building blocks of React.js applications, enabling modular development 🏗️.
    -   JSX (JavaScript XML) allows you to write HTML-like code within JavaScript, making UI development more expressive 📝.
    -   Props (Properties) and State are used for managing data and passing information between components 📦.
    -   Component Lifecycle methods provide control over component rendering and behavior ⏳.
-   **React.js Documentation** 📚:
    
    -   Learn how to navigate the official React.js documentation effectively 🧭.
    -   Find answers to common questions and problems while working with React 🤔.
    -   Access a wealth of learning resources and community support to enhance your React skills 🌐.
-   **Practical Applications** 🚀:
    
    -   React.js is used for building web user interfaces, single-page applications, and real-time updates 🌐.
    -   It promotes component reusability and is suitable for web and mobile app development 📱.
    -   React can fetch data from APIs, facilitate testing, and offer exciting career opportunities in web development 💼.


# 🌐 React.js Fundamentals - Quiz 🤔

1.  🤔 What is the main purpose of React.js?
    
    -   a) To create beautiful designs
    -   b) To build user interfaces and applications
    -   c) To manage databases
    -   d) To play online games
    -   **Correct Answer: b) To build user interfaces and applications 🚀**
2.  📦 Which tool do you need to install alongside React.js for managing dependencies?
    
    -   a) Yarn
    -   b) Babel
    -   c) Gulp
    -   d) npm
    -   **Correct Answer: d) npm 📦**
3.  🌐 What is the primary use of JSX in React.js?
    
    -   a) Managing state
    -   b) Combining HTML and JavaScript
    -   c) Storing data
    -   d) Creating components
    -   **Correct Answer: b) Combining HTML and JavaScript 📝**
4.  🧩 In React, what are components?
    
    -   a) HTML elements
    -   b) Building blocks of user interfaces
    -   c) JavaScript libraries
    -   d) External plugins
    -   **Correct Answer: b) Building blocks of user interfaces 🧩**
5.  ⏳ Which method allows you to control the rendering and behavior of a React component over its lifecycle?
    
    -   a) `renderComponent()`
    -   b) `componentWillUnmount()`
    -   c) `componentDidMount()`
    -   d) `lifeCycleUpdate()`
    -   **Correct Answer: c) `componentDidMount()` ⏳**
6.  🚀 What is the primary advantage of using React for single-page applications (SPAs)?
    
    -   a) Smaller bundle sizes
    -   b) Faster initial page load times
    -   c) Server-side rendering
    -   d) Support for multiple databases
    -   **Correct Answer: b) Faster initial page load times 🚀**
7.  📚 Where can you find official documentation and resources for React.js?
    
    -   a) GitHub
    -   b) Reddit
    -   c) The React.js official website
    -   d) Stack Overflow
    -   **Correct Answer: c) The React.js official website 📚**
8.  📂 In a typical React application, where can you find static assets like HTML files and images?
    
    -   a) In the `components` folder
    -   b) In the `src` folder
    -   c) In the `public` folder
    -   d) In the `node_modules` folder
    -   **Correct Answer: c) In the `public` folder 📂**
9.  📱 Which framework allows you to build native mobile applications for iOS and Android using React?
    
    -   a) Angular
    -   b) Vue.js
    -   c) React Native
    -   d) Ionic
    -   **Correct Answer: c) React Native 📱**
10.  📝 What is the purpose of the `state` in a React component?
    
     -   a) To store and manage data that can change over time
     -   b) To define the component's structure
     -   c) To handle user interactions
     -   d) To render the component
     -   **Correct Answer: a) To store and manage data that can change over time 📝**
11.  🧪 Which concept allows you to test and debug React components effectively?
    
     -   a) Prop drilling
     -   b) Component composition
     -   c) Component lifecycle methods
     -   d) State management
     -   **Correct Answer: c) Component lifecycle methods 🧪**
12.  🌟 What makes React.js a popular choice for building web applications?
    
     -   a) It's a database management system
     -   b) It supports server-side rendering
     -   c) It promotes component-based architecture and reusability
     -   d) It only works with PHP
     -   **Correct Answer: c) It promotes component-based architecture and reusability 🌟**
13.  🚄 React's efficient updates result in a smoother user experience by minimizing what?
    
     -   a) Network latency
     -   b) Actual DOM manipulation
     -   c) CPU usage
     -   d) Server load
     -   **Correct Answer: b) Actual DOM manipulation 🚄**
14.  🏡 In which type of applications is React.js commonly used to build beautiful and interactive user interfaces?
    
     -   a) Console applications
     -   b) Web applications
     -   c) Mobile applications
     -   d) Desktop applications
     -   **Correct Answer: b) Web applications 🏡**
15.  🌐 What is the role of the Virtual DOM in React.js?
    
     -   a) It manages database connections
     -   b) It handles user authentication
     -   c) It efficiently updates the real DOM
     -   d) It optimizes server responses
     -   **Correct Answer: c) It efficiently updates the real DOM 🌐**
16.  🌍 What does Reactiflux refer to in the context of React development?
    
      -   a) A JavaScript library for routing in React
     -   b) An official React conference
      -   c) A community of React enthusiasts on Discord
     -   d) A popular React animation library
     -   **Correct Answer: c) A community of React enthusiasts on Discord 🌍**
17.  📡 When using React, what does API integration typically involve?
    
     -   a) Handling user interface events
     -   b) Fetching and sending data to external services
     -   c) Defining component styles
     -   d) Creating user interfaces
     -   **Correct Answer: b) Fetching and sending data to external services 📡**
18.  🏢 Which type of applications is React.js not typically used for?
    
     -   a) Single-page applications (SPAs)
     -   b) E-commerce platforms
     -   c) Enterprise resource planning (ERP) software
     -   d) Social media feeds
     -   **Correct Answer: c) Enterprise resource planning (ERP) software 🏢**
19.  💼 What exciting career opportunities can learning React.js lead to?
    
     -   a) Opportunities in culinary arts
     -   b) Opportunities in space exploration
     -   c) Opportunities in web development and software engineering
     -   d) Opportunities in professional sports
     -   **Correct Answer: c) Opportunities in web development and software engineering 💼**
20.  🧐 Where can you find curated learning paths and tutorials for React.js?
    
     -   a) In the React.js documentation's "Getting Started" section
     -   b) On YouTube, by searching for "React tutorials"
     -   c) By asking random strangers on the street
     -   d) In the "About" section of your favorite social media platform
     -   **Correct Answer: a) In the React.js documentation's "Getting Started" section 🧐**
21.  🎓 What term describes the ability of React.js to efficiently update only the parts of the user interface that have changed?
    
     -   a) Partial rendering
     -   b) Lazy loading
     -   c) Incremental DOM updates
     -   d) Virtual DOM diffing
     -   **Correct Answer: d) Virtual DOM diffing 🎓**
22.  📂 In a typical React application, where would you find the project's dependencies listed?
    
     -   a) In the `node_modules` folder
     -   b) In the `package.json` file
     -   c) In the `src` folder
     -   d) In the `public` folder
     -   **Correct Answer: b) In the `package.json` file 📂**
23.  🧩 What is the primary advantage of component reusability in React?
    
     -   a) It reduces the number of components needed.
     -   b) It ensures that components never change.
     -   c) It simplifies the development process.
     -   d) It makes the code longer and more complex.
     -   **Correct Answer: c) It simplifies the development process. 🧩**
24.  🤖 Which React.js feature allows you to optimize the rendering of components by preventing unnecessary updates?
    
     -   a) Component props
     -   b) PureComponent
     -   c) React Router
     -   d) Stateless components
     -   **Correct Answer: b) PureComponent 🤖**
25.  📱 What framework is built on React and enables the development of native mobile applications for iOS and Android?
    
     -   a) Angular
     -   b) React Native
     -   c) Vue.js
     -   d) Flutter
     -   **Correct Answer: b) React Native 📱**

Good luck with your quiz on Day 1 of React.js fundamentals! 🚀

🎉 Today, you've taken your first steps into the exciting world of React.js. You've learned about the fundamentals, set up your environment, and explored the key concepts. Keep the momentum going, and I can't wait to see your progress on Day 2. Happy coding! 🚀







