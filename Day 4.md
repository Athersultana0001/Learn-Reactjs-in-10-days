# Styling in React 🌈 

![Conditional Styling in React JS - Owlcation](https://images.saymedia-content.com/.image/t_share/MTg3MjAxODQyNTc1MzIwOTc0/conditional-styling-react.png)
## Objectives 🎯

1.  🎨 Understand the various methods of styling React components.

2.  🌟 Explore CSS-in-JS solutions such as Styled-components and Emotion.
3.  🌆 Learn how to integrate CSS frameworks with React applications.
4.  📚 Apply best practices for styling in React to create maintainable and visually appealing UIs.

## Key Topics 📝

1.    🎨 **Styling React Components with CSS:**
    
      -   Traditional CSS styling for React components.
      -   Scoped CSS and CSS Modules for encapsulation.
2.    🌟 **CSS-in-JS Solutions (Styled-components, Emotion):**
    
      -   Introduction to CSS-in-JS.
      -   Using Styled-components to style components.
      -   Exploring Emotion for dynamic styling.
3.    🌆 **CSS Frameworks with React:**
    
      -   Integrating popular CSS frameworks like Bootstrap or Material-UI with React.
      -   Customizing and theming CSS frameworks for your React app.
4.    📚 **Styling Best Practices:**
    
      -   Following best practices for organizing and structuring styles.
      -   Handling responsive design and media queries.
      -   Dealing with global styles and theming.

Day 4 will equip you with the skills and knowledge to make your React applications not only functionally rich but also visually appealing and well-organized. 🚀

#  **Styling React Components with CSS** 🎨

![What's the difference between rendering the CSS with React and applying the  CSS to React with a .css file? What should I use? - Quora](https://qph.cf2.quoracdn.net/main-qimg-b4df7c5f8087bf741337ca140433eef5)

Styling your React components is a crucial aspect of creating visually appealing and user-friendly user interfaces. You can use various methods to style your components, including traditional CSS, scoped CSS, and CSS Modules.

## 🖌️ Traditional CSS Styling

- Traditional CSS styling involves creating separate CSS files and applying styles to React components using class names.

``` css
/* styles.css */

.myButton {
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

.myButton:hover {
  background-color: #0056b3;
}
```

``` jsx
// Button.js

import React from 'react';
import './styles.css'; // Import the CSS file

const Button = () => {
  return (
    <button className="myButton">
      Click me!
    </button>
  );
};

export default Button;
```

**In this example:**

-   We create a CSS file, `styles.css`, with styles for a button.
-   We import the CSS file in our React component.
-   We apply the styles using the `className` attribute.

## 🔍 Scoped CSS and CSS Modules

Scoped CSS and CSS Modules offer a way to encapsulate styles, ensuring they only apply to specific components, avoiding global style conflicts.

### Scoped CSS

- Scoped CSS can be achieved using libraries like `styled-components`. It allows you to define styles within your component files.

``` jsx
// Button.js

import React from 'react';
import styled from 'styled-components';

const StyledButton = styled.button`
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;

  &:hover {
    background-color: #0056b3;
  }
`;

const Button = () => {
  return (
    <StyledButton>
      Click me!
    </StyledButton>
  );
};

export default Button;
```

### CSS Modules

- CSS Modules provide scoped CSS by default. You create a CSS file per component, and the class names are scoped to that component.

``` css
/* Button.module.css */

.myButton {
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

.myButton:hover {
  background-color: #0056b3;
}
```

``` jsx
// Button.js

import React from 'react';
import styles from './Button.module.css'; // Import the CSS module

const Button = () => {
  return (
    <button className={styles.myButton}>
      Click me!
    </button>
  );
};

export default Button;
```

## 🤔 Which Styling Method to Choose?

-   **Traditional CSS**: Suitable for small projects or when you have an existing CSS codebase.
-   **Scoped CSS and CSS Modules**: Recommended for larger projects as they provide better encapsulation and prevent global styling conflicts.

Choose the styling method that best fits your project's requirements and preferences. 🚀

# CSS-in-JS Solutions (Styled-components, 

![How to use Emotion to style you React components | by Nishit Maheta |  JavaScript in Plain English](https://miro.medium.com/v2/resize:fit:1400/1*hPN6aCm0RmEdHwksS8kaxA.png)Emotion) 🌟
CSS-in-JS is a modern approach to styling in React that allows you to write CSS directly in your JavaScript files. It offers dynamic styling and encapsulation, making it a popular choice for styling React components.

## Introduction to CSS-in-JS

CSS-in-JS is a methodology that enables you to write and manage CSS within your JavaScript files. It provides several benefits, including scoped styles, dynamic theming, and enhanced developer experience.

## Using Styled-components to Style Components

`Styled-components` is a popular CSS-in-JS library that allows you to define and attach styles to your components using tagged template literals. It offers a powerful and intuitive way to style React components.

``` jsx
import React from 'react';
import styled from 'styled-components';

const StyledButton = styled.button`
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;

  &:hover {
    background-color: #0056b3;
  }
`;

const Button = () => {
  return (
    <StyledButton>
      Click me!
    </StyledButton>
  );
};

export default Button;
```

In this example, we use `styled-components` to define styles for a button component directly within the component file.

## Exploring Emotion for Dynamic Styling

`Emotion` is another CSS-in-JS library that offers powerful styling capabilities with great performance. It allows you to write styles as JavaScript objects or template literals and provides features like theming and prop-based styles.

``` jsx
import React from 'react';
import { css } from '@emotion/react';

const buttonStyle = css`
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;

  &:hover {
    background-color: #0056b3;
  }
`;

const Button = () => {
  return (
    <button css={buttonStyle}>
      Click me!
    </button>
  );
};

export default Button;
```

In this example, we use `Emotion` to define styles using the `css` prop, providing dynamic styling capabilities.

## 🚀 Choose Your CSS-in-JS Adventure

Both `Styled-components` and `Emotion` offer powerful solutions for dynamic styling in React. Choose the one that aligns with your project's requirements and coding style to create beautiful and maintainable user interfaces. 🎨

# CSS Frameworks with React 🌆

![23 Best CSS Frameworks For React In 2023: A Comprehensive Overview |  LambdaTest](https://www.lambdatest.com/blog/wp-content/uploads/2023/04/Frame252525252525201.png)
CSS frameworks like Bootstrap and Material-UI provide pre-built styles and components that can be seamlessly integrated into React applications. Let's see how to use them effectively.

## 🚀 Integrating CSS Frameworks with React

### Using Bootstrap with React

Bootstrap is a widely used CSS framework. You can integrate it with React by installing the `react-bootstrap` library, which provides React components for Bootstrap.

``` bash
npm install react-bootstrap bootstrap
```

- Here's how you can use Bootstrap components in a React component:

``` jsx
import React from 'react';
import Button from 'react-bootstrap/Button';

const App = () => {
  return (
    <div>
      <h1>Using Bootstrap with React</h1>
      <Button variant="primary">Primary Button</Button>
    </div>
  );
};

export default App;
```

### Using Material-UI with React

Material-UI is a popular CSS framework for creating Material Design-themed applications. You can integrate it with React by installing the `@mui/material` package.

``` bash
npm install @mui/material @mui/icons-material
```

- Here's how you can use Material-UI components in a React component:
``` jsx
import React from 'react';
import Button from '@mui/material/Button';

const App = () => {
  return (
    <div>
      <h1>Using Material-UI with React</h1>
      <Button variant="contained" color="primary">
        Primary Button
      </Button>
    </div>
  );
};

export default App;
```

## 🎨 Customizing and Theming CSS Frameworks

Customizing and theming CSS frameworks is essential to maintain a consistent look and feel for your React application.

### Customizing Bootstrap

You can customize Bootstrap by overriding its default styles with your custom CSS or by using Bootstrap's built-in theming capabilities.

### Theming Material-UI

Material-UI offers a powerful theming system. You can create a custom theme to control the colors, typography, and other design aspects of your application.

- Here's an example of creating a custom Material-UI theme:

``` jsx
import { createTheme } from '@mui/material/styles';

const theme = createTheme({
  palette: {
    primary: {
      main: '#0074d9',
    },
    secondary: {
      main: '#0056b3',
    },
  },
  typography: {
    fontFamily: 'Arial, sans-serif',
  },
});

export default theme;
```

- You can then apply this theme to your entire application using a `ThemeProvider`:
``` jsx
import React from 'react';
import { ThemeProvider } from '@mui/material/styles';
import theme from './theme';

const App = () => {
  return (
    <ThemeProvider theme={theme}>
      {/* Your application content */}
    </ThemeProvider>
  );
};

export default App;
```

Customizing and theming CSS frameworks allows you to maintain a unique design while benefiting from the convenience of these frameworks.

### 🚀 Customize and Elevate Your UI

Integrating and customizing CSS frameworks like Bootstrap or Material-UI with React opens up a world of possibilities for creating beautiful and responsive user interfaces. Choose the framework that suits your project's requirements and start crafting stunning UIs! 🌆

Styling React components efficiently and maintaining a scalable and maintainable codebase is crucial. Here are some best practices to follow:

#  **Styling Best Practices:** 📚
![9 Ways To Implement CSS in React JS | by Dmitry Nozhenko | Medium](https://miro.medium.com/v2/resize:fit:2000/1*OjnZjw20cnBWVs4E_a3u4A.png)


### 1. **Component-Centric Styles** 📦

Keep styles scoped to individual components. This improves code maintainability and reduces the chances of style conflicts.

### 2. **Use CSS Modules** 🛠️

If possible, use CSS Modules or CSS-in-JS solutions like `Styled-components` to encapsulate styles within components.

### 3. **Keep Styles Near Components** 🏠

Place your stylesheets or style declarations close to the component they are styling. This makes it easier to understand the relationship between styles and components.
```  jsx
import React from 'react';
import './MyComponent.css'; // Styles located near the component
```

### 4. **Avoid Overly Specific Selectors** 🚫

Refrain from using overly specific CSS selectors that make it hard to override or reuse styles.

``` css
/* Avoid overly specific selectors */
.my-component button[type="submit"] {
  /* ... */
}

/* Prefer more generic selectors */
.my-button {
  /* ... */
}
```

## Handling Responsive Design and Media Queries

### 5. **Mobile-First Design** 📱

Start with styles for mobile devices and use media queries to progressively enhance for larger screens. This ensures a responsive design.

``` css
/* Mobile-first design */
.my-component {
  font-size: 16px;
}

/* Media query for larger screens */
@media (min-width: 768px) {
  .my-component {
    font-size: 20px;
  }
}
```

### 6. **Breakpoints** ⚡

Define breakpoints for different screen sizes to make media queries more readable and consistent.

``` css
/* Breakpoints for common screen sizes */
$small-screen: 576px;
$medium-screen: 768px;
$large-screen: 992px;

/* Usage in media queries */
@media (min-width: $medium-screen) {
  /* ... */
}
```

## Dealing with Global Styles and Theming

### 7. **Global Styles** 🌍

Use global stylesheets sparingly. Reserve them for styles that genuinely apply to the entire application, like resetting default browser styles.

### 8. **Theming** 🌈

Implement a theming strategy to manage colors, typography, and other design aspects consistently across the application.

``` jsx
import { createTheme } from '@mui/material/styles';

const theme = createTheme({
  palette: {
    primary: {
      main: '#0074d9',
    },
    secondary: {
      main: '#0056b3',
    },
  },
  typography: {
    fontFamily: 'Arial, sans-serif',
  },
});

export default theme;
```

### 🚀 Elevate Your Styling Game

Following these best practices not only makes your code more organized and maintainable but also enhances the user experience by ensuring your UI is responsive and visually pleasing. Happy styling! 🎨

# Activity: Styling in React 🌈 

In this activity, you'll apply what you've learned about styling in React. We'll cover various styling techniques using emojis to make it visually appealing.

## Task 1: Traditional CSS Styling 🎨

1.  Create a new React component named `MyComponent`.
2.  Style the component using traditional CSS.
3.  Add a button with a unique class name and apply styles to it.
4.  Ensure that the styles are located near the component.

<details> <summary>Task 1 Code Example</summary>

``` jsx
// MyComponent.js

import React from 'react';
import './MyComponent.css'; // Import the CSS file

const MyComponent = () => {
  return (
    <div className="my-component">
      <h1>Welcome to My Component</h1>
      <button className="my-button">Click me!</button>
    </div>
  );
};

export default MyComponent;
```

``` css
/* MyComponent.css */

.my-component {
  /* Component styles */
}

.my-button {
  /* Button styles */
}
```

</details>

## Task 2: CSS-in-JS with Styled-components 🌟

1.  Create a new React component named `StyledComponent`.
2.  Use `Styled-components` to style the component.
3.  Customize the styles for a button using tagged template literals.

<details> <summary>Task 2 Code Example</summary>

``` jsx
// StyledComponent.js

import React from 'react';
import styled from 'styled-components';

const StyledButton = styled.button`
  background-color: #0074d9;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;

  &:hover {
    background-color: #0056b3;
  }
`;

const StyledComponent = () => {
  return (
    <div>
      <h1>Welcome to Styled Component</h1>
      <StyledButton>Click me!</StyledButton>
    </div>
  );
};

export default StyledComponent;
```

</details>

## Task 3: Integrating Material-UI with React 🌆

1.  Create a new React component named `MaterialUIComponent`.
2.  Integrate Material-UI.
3.  Use Material-UI components to create a styled interface.

<details> <summary>Task 3 Code Example</summary>

``` jsx
// MaterialUIComponent.js

import React from 'react';
import Button from '@mui/material/Button';

const MaterialUIComponent = () => {
  return (
    <div>
      <h1>Welcome to Material-UI Component</h1>
      <Button variant="contained" color="primary">
        Primary Button
      </Button>
    </div>
  );
};

export default MaterialUIComponent;
```

</details>

## Task 4: Styling Best Practices 📚

1.  Implement styling best practices by organizing styles, handling responsive design, and dealing with global styles and theming.
2.  Customize the colors and typography using a theme in Material-UI.

<details> <summary>Task 4 Code Example</summary>

``` jsx
// StylingBestPractices.js

import React from 'react';
import { createTheme } from '@mui/material/styles';
import { ThemeProvider } from '@mui/material/styles';

const theme = createTheme({
  palette: {
    primary: {
      main: '#0074d9',
    },
    secondary: {
      main: '#0056b3',
    },
  },
  typography: {
    fontFamily: 'Arial, sans-serif',
  },
});

const StylingBestPractices = () => {
  return (
    <ThemeProvider theme={theme}>
      <div>
        <h1>Welcome to Styling Best Practices</h1>
        {/* Your styled components and content */}
      </div>
    </ThemeProvider>
  );
};

export default StylingBestPractices;
```

</details>

## 🚀 Ready to Shine!

Apply what you've learned in this activity to create stylish React components. Feel free to experiment further and enhance the styles to make your components visually appealing! 💅

# Applications 🚀

1.  🎨 **Traditional CSS Styling**: Apply traditional CSS styling techniques to create custom layouts and design elements for your React components.
    
2.  🌟 **CSS-in-JS with Styled-components**: Utilize CSS-in-JS libraries like `Styled-components` to create highly customizable and reusable styled components, allowing for dynamic theming and component-level encapsulation of styles.
    
3.  🌆 **Integrating Material-UI with React**: Integrate Material-UI to leverage its pre-built components and styles, making it easier to create responsive and visually appealing user interfaces. Customize Material-UI components to match your project's design requirements.
    
4.  📚 **Styling Best Practices**: Implement advanced styling practices, such as organizing styles in a component-centric manner, optimizing for mobile-first design, and creating themes for consistent styling across your React application. Handle global styles effectively while maintaining a clean and scalable codebase.

# Summary 🚀

1.  🎨 Traditional CSS Styling:
    
    -   Styled React components using traditional CSS.
    -   Kept styles scoped to individual components.
2.  🌟 CSS-in-JS with Styled-components:
    
    -   Utilized `Styled-components` for dynamic and scoped styling.
    -   Created styled components with tagged template literals.
3.  🌆 Integrating Material-UI with React:
    
    -   Integrated Material-UI to leverage pre-built UI components.
    -   Customized Material-UI components for a unique design.
4.  📚 Styling Best Practices:
    
    -   Followed best practices for organizing styles.
    -   Implemented mobile-first design and responsive styling.
    -   Managed global styles and applied theming for consistency.

Day 4 equipped us with various styling techniques and best practices to enhance the visual appeal and maintainability of React applications. 🌈

# 🌈 Styling in React- Quiz 🎨

1.  What is the primary benefit of using CSS Modules in React?
    
    a) 🎨 Easier integration with Material-UI  
    b) 🏠 Scoped styles for individual components  
    c) 📏 Automatic responsive design  
    d) 🌍 Global styling for the entire application
    
    **Answer: b**
    
2.  Which CSS-in-JS library allows you to create styled components using tagged template literals?
    
    a) 📚 CSS Modules  
    b) 🌟 Emotion  
    c) 🌆 Styled-components  
    d) 🎨 Material-UI
    
    **Answer: c**
    
3.  When using Material-UI with React, what do you import to access Material-UI components?
    
    a) 🎨 `@mui/core`  
    b) 🏠 `@mui/components`  
    c) 🌆 `@mui/material`  
    d) 📚 `@material/react`
    
    **Answer: c**
    
4.  In the context of CSS, what does "scoped styles" refer to?
    
    a) 🎨 Stylesheets with global reach  
    b) 🏠 Styles that only apply to specific components  
    c) 🌟 Styles that adapt to screen size  
    d) 📚 Styles integrated with Material-UI
    
    **Answer: b**
    
5.  What is the purpose of tagged template literals in CSS-in-JS libraries like Styled-components?
    
    a) 📚 To define media queries  
    b) 🎨 To create dynamic styles  
    c) 🌟 To manage global styles  
    d) 🌆 To integrate with Material-UI
    
    **Answer: b**
    
6.  When implementing mobile-first design, where do you start when defining styles?
    
    a) 🎨 Larger screens and then adapt to smaller screens  
    b) 📚 Smaller screens and then adapt to larger screens  
    c) 🏠 A random screen size  
    d) 🌆 It doesn't matter; all screens are styled the same way
    
    **Answer: b**
    
7.  What is the purpose of defining breakpoints in responsive design?
    
    a) 🏠 To indicate where styles should break  
    b) 🌆 To create new components for each breakpoint  
    c) 🎨 To define specific style rules for different screen sizes  
    d) 🌟 To remove styles for larger screens
    
    **Answer: c**
    
8.  In Material-UI theming, which object is used to define custom color palettes?
    
    a) 📚 `breakpoints`  
    b) 🌆 `spacing`  
    c) 🎨 `palette`  
    d) 🏠 `components`
    
    **Answer: c**
    
9.  Which best practice helps maintain clean and organized styles in a React application?
    
    a) 🌟 Using overly specific selectors  
    b) 🎨 Keeping all styles in a single global stylesheet  
    c) 📚 Using component-centric styles  
    d) 🌍 Not using any styles
    
    **Answer: c**
    
10.  What is the primary role of CSS Modules in React?
    
     a) 🌆 To provide pre-built UI components  
    b) 🏠 To create global styles for the entire app  
    c) 🎨 To scope styles to individual components  
    d) 📚 To handle routing in React applications
    
     **Answer: c**
    
11.  Which of the following libraries is known for its theming and customization capabilities in React?
    
     a) 🎨 Bootstrap  
    b) 🌆 Material-UI  
    c) 📚 React Router  
    d) 🌟 Styled-components
    
     **Answer: b**
    
12.  What is the purpose of media queries in responsive design?
    
     a) 🌆 To define how to query a database  
    b) 📚 To optimize JavaScript code  
    c) 🎨 To conditionally apply styles based on screen size  
    d) 🏠 To create dynamic components
    
     **Answer: c**
    
13.  Which of the following is NOT a benefit of using CSS Modules in React?
    
     a) 🌆 Scoped styles for individual components  
    b) 📚 Easier integration with Material-UI  
    c) 🏠 Avoidance of global style conflicts  
    d) 🎨 Improved code maintainability
    
     **Answer: b**
    
14.  In Material-UI theming, what does the `palette` object allow you to customize?
    
     a) 🎨 Typography settings  
    b) 🏠 Component structure  
    c) 🌟 Color palettes  
    d) 📚 Breakpoints for responsive design
    
     **Answer: c**
    
15.  How can you ensure that styles are located near the components they are styling?
    
     a) 🌟 Use CSS Modules  
    b) 📚 Define styles in a separate folder  
    c) 🏠 Place styles in a global stylesheet  
    d) 🎨 Use an external styling library
    
     **Answer: a**
    
16.  What is the primary advantage of using CSS-in-JS solutions like Styled-components?
    
     a) 🏠 Easier integration with Material-UI  
    b) 🌟 Scoped and dynamic styling  
    c) 🎨 Support for global styles  
    d) 📚 Automatic responsiveness
    
     **Answer: b**
    
17.  When customizing Material-UI components, which of the following allows you to change the default styles?
    
     a) 🎨 External CSS files  
    b) 📚 Component-specific styles  
    c) 🏠 Global stylesheets  
    d) 🌟 Theme customization
    
     **Answer: d**
    
18.  What is the purpose of using breakpoints in responsive design?
    
     a) 🏠 To create breakpoints between components  
    b) 🎨 To define specific styling for different screen sizes  
    c) 🌟 To specify breakpoints in code  
    d) 📚 To add breakpoints in code for debugging
    
     **Answer: b**
    
19.  Which library provides pre-built UI components and styling options for React applications?
    
     a) 📚 React Router  
    b) 🏠 Redux  
    c) 🌟 Material-UI  
    d) 🎨 Bootstrap
    
     **Answer: c**
    
20.  How can you create responsive design using media queries?
    
     a) 🎨 By using JavaScript code  
    b) 📚 By defining breakpoints in the HTML file  
    c) 🏠 By adding styles to the component's constructor  
    d) 🌟 By conditionally applying styles based on screen size
    
     **Answer: d**

21.  Which library provides a theming system and pre-built UI components specifically designed for React applications?

     a) 🌟 Material-UI  
b) 🏠 Redux  
c) 🎨 Bootstrap  
d) 📚 React Router

     **Answer: a**

22.  In the context of CSS-in-JS, what is the primary benefit of scoped styles?

     a) 📚 Easy integration with external CSS libraries  
b) 🏠 Global access to styles across components  
c) 🌆 Avoidance of style conflicts between components  
d) 🎨 Improved code maintainability

      **Answer: c**

23.  When creating a responsive design, what is the significance of a mobile-first approach?

     a) 📚 Starting with the largest screens and working down  
b) 🏠 Beginning with styles for desktop screens  
c) 🎨 Starting with styles for mobile devices and adding for larger screens  
d) 🌟 Focusing on styles for tablets first

     **Answer: c**

24.  What role do breakpoints play in responsive design?

     a) 📚 Defining the layout of HTML documents  
b) 🎨 Specifying the exact pixel values for element sizes  
c) 🏠 Creating components with specific dimensions  
d) 🌟 Determining when styles should change based on screen width

     **Answer: d**

25.  Which CSS property allows you to apply styles to a specific screen size range in responsive design?

     a) 🏠 `display`  
b) 📚 `position`  
c) 🌟 `@media`  
d) 🎨 `flex`

     **Answer: c**

🚀 Today, you delved into the exciting world of styling in React, exploring traditional CSS, CSS-in-JS solutions like Styled-components, integrating Material-UI, and mastering styling best practices. You're now equipped with the skills to make your React applications not only functional but also visually stunning. Keep up the great work, and get ready to dive into more advanced topics tomorrow! 💅



