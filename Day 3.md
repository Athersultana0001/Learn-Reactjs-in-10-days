# 📋 Working with React Forms

![How To Work With Forms in React](https://d2o2utebsixu4k.cloudfront.net/media/images/0c7920e7-3695-4bb7-8c66-2c96f43d1988.jpg)

## Objectives 🎯
1.  **Understand Controlled Components:** Learn how to build forms in React using controlled components, which allow you to manage form input as a part of your component's state.
    
2.  **Form Events and Handling:** Explore form events like `onChange` and `onSubmit` and how to handle them to create interactive forms.
    
3.  **Form Validation and Error Handling:** Discover techniques for validating user input in forms and handling errors gracefully to provide a better user experience.
    
4.  **Form Libraries:** Get introduced to popular React form libraries that simplify form creation and management.
    

## Key Topics 📝

-   📋 **Building Forms with Controlled Components:** Controlled components are React components that store form input values in their state, making it easier to handle changes and updates.
    
-   🌟 **Form Events and Handling:** Form events like `onChange` for input elements and `onSubmit` for the form itself are crucial for capturing user interactions and handling form submission.
    
-   📚 **Form Validation and Error Handling:** Form validation ensures that user input is accurate and meets specific criteria. Error handling involves providing feedback to users when validation fails.
    
-   📚 **Form Libraries:** React has a thriving ecosystem of form libraries like Formik, Redux-Form, and Yup that simplify form creation, validation, and state management.
    

Day 3 will empower you to create interactive and user-friendly forms in your React applications, a critical skill for building engaging web applications. 📋


# 📋 Building Forms with Controlled Components

![Controlled vs uncontrolled React components - why not both?](https://whereisthemouse.com/assets/controlled-uncontrolled.webp)


In React, forms are often created using controlled components. Controlled components are React components that store form input values in their state, making it easier to handle changes and updates. This approach gives you more control over the form data and provides a clear flow of data between the form inputs and the component's state.

## Why Use Controlled Components? 🤔

Controlled components offer several advantages:

-   **Single Source of Truth**: The form input values are directly tied to the component's state, creating a single source of truth for your data.
    
-   **Dynamic Updates**: You can easily update and validate form data as users interact with the inputs.
    
-   **Custom Behavior**: You have full control over how the data is processed before submission or display.
    

Let's create a simple controlled form component to understand the concept better:

``` jsx
import React, { Component } from 'react';

class ControlledForm extends Component {
  constructor(props) {
    super(props);
    this.state = {
      username: '',
      email: '',
    };
  }

  handleInputChange = (e) => {
    const { name, value } = e.target;
    this.setState({ [name]: value });
  };

  handleSubmit = (e) => {
    e.preventDefault();
    const { username, email } = this.state;
    console.log(`Username: ${username}, Email: ${email}`);
  };

  render() {
    const { username, email } = this.state;

    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Username:
          <input
            type="text"
            name="username"
            value={username}
            onChange={this.handleInputChange}
          />
        </label>
        <label>
          Email:
          <input
            type="email"
            name="email"
            value={email}
            onChange={this.handleInputChange}
          />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}

export default ControlledForm;
```

**In this example:**

-   We create a form with two input fields for username and email.
-   Each input field is associated with a piece of state in the component.
-   The `handleInputChange` function updates the state as the user types.
-   The form submission is handled by the `handleSubmit` function.

By connecting the form inputs to the component's state, we maintain control over the form data and can easily access, manipulate, or validate it as needed. Controlled components provide a solid foundation for building interactive forms in React. 🚀

# 🌟 Form Events and Handling

![React Events - javatpoint](https://static.javatpoint.com/tutorial/reactjs/images/react-events.png)

Form events are essential for creating interactive and responsive forms in React. Two key events we'll focus on are `onChange` for input elements and `onSubmit` for the form itself. Understanding how to use these events allows you to capture user interactions and manage form submissions effectively.

## Using `onChange` for Input Elements 💌

The `onChange` event is triggered when the value of an input element changes, such as when a user types into a text field or selects an option in a dropdown. This event is crucial for real-time updates and validation.

Let's see how to use `onChange` in a controlled component:

``` jsx
import React, { Component } from 'react';

class FormWithOnChange extends Component {
  constructor(props) {
    super(props);
    this.state = {
      inputValue: '',
    };
  }

  handleInputChange = (e) => {
    // Update the state when the input value changes
    this.setState({ inputValue: e.target.value });
  };

  render() {
    return (
      <div>
        <input
          type="text"
          value={this.state.inputValue}
          onChange={this.handleInputChange}
        />
        <p>You typed: {this.state.inputValue}</p>
      </div>
    );
  }
}
```

**In this example:**

-   We create an input element with an associated state called `inputValue`.
-   The `onChange` event is used to call the `handleInputChange` function, which updates the state with the current input value.
-   The input value is displayed below the input field, providing real-time feedback to the user.

## Using `onSubmit` for Form Submission 📤

The `onSubmit` event is triggered when a form is submitted, either by pressing Enter or clicking a submit button. This event is essential for handling form submissions and performing actions like data validation and sending data to a server.

Here's an example of how to use `onSubmit` in a React form:

``` jsx
import React, { Component } from 'react';

class FormWithOnSubmit extends Component {
  constructor(props) {
    super(props);
    this.state = {
      inputValue: '',
    };
  }

  handleSubmit = (e) => {
    e.preventDefault(); // Prevent the default form submission behavior
    alert(`Submitted value: ${this.state.inputValue}`);
  };

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <input
          type="text"
          value={this.state.inputValue}
          onChange={(e) => this.setState({ inputValue: e.target.value })}
        />
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

**In this example:**

-   We create a form with an input field and a submit button.
-   The `onSubmit` event is used to call the `handleSubmit` function, which prevents the default form submission behavior (page reload) and shows an alert with the submitted value.

Understanding and harnessing the power of `onChange` and `onSubmit` events are fundamental for creating interactive forms in React. These events enable you to capture user input and manage form submissions efficiently. 🚀

# 📚 Form Validation and Error Handling

![Handle form and validation with React - DEV Community](https://res.cloudinary.com/practicaldev/image/fetch/s--f2dSR5ub--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/myqfdzqp15p3h2pih8c4.png)


Form validation is a crucial part of creating robust and user-friendly web forms. It ensures that user input is accurate, meets specific criteria, and prevents invalid data from being submitted. Error handling is equally important, as it provides feedback to users when validation fails, helping them understand and correct their mistakes.

## Why Form Validation? 🤔

Form validation serves several purposes:

-   **Data Accuracy**: Ensures that the data submitted is accurate and in the expected format.
    
-   **Enhanced User Experience**: Provides users with immediate feedback, reducing frustration and errors.
    
-   **Security**: Protects your application from malicious input or data breaches.
    

Let's walk through an example of form validation and error handling in a React component:

``` jsx
import React, { Component } from 'react';

class FormWithValidation extends Component {
  constructor(props) {
    super(props);
    this.state = {
      email: '',
      password: '',
      errors: {
        email: '',
        password: '',
      },
    };
  }

  handleChange = (e) => {
    const { name, value } = e.target;
    this.setState({ [name]: value });
  };

  handleSubmit = (e) => {
    e.preventDefault();

    // Validate the form data
    const { email, password } = this.state;
    const errors = {};

    // Email validation (simple example)
    if (!email.includes('@')) {
      errors.email = 'Invalid email address';
    }

    // Password validation (simple example)
    if (password.length < 6) {
      errors.password = 'Password must be at least 6 characters';
    }

    // If there are errors, update the state
    if (Object.keys(errors).length > 0) {
      this.setState({ errors });
    } else {
      // Form is valid, proceed with submission
      console.log('Form submitted successfully');
    }
  };

  render() {
    const { email, password, errors } = this.state;

    return (
      <form onSubmit={this.handleSubmit}>
        <div>
          <label>Email:</label>
          <input
            type="email"
            name="email"
            value={email}
            onChange={this.handleChange}
          />
          {errors.email && <div className="error">{errors.email}</div>}
        </div>
        <div>
          <label>Password:</label>
          <input
            type="password"
            name="password"
            value={password}
            onChange={this.handleChange}
          />
          {errors.password && <div className="error">{errors.password}</div>}
        </div>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

**In this example:**

-   We create a form with input fields for email and password.
-   The `handleChange` function updates the state as the user types.
-   The `handleSubmit` function performs validation by checking if the email contains '@' and if the password is at least 6 characters long.
-   If there are validation errors, we update the `errors` state, and the error messages are displayed below the corresponding input fields.

Form validation and error handling ensure that user input is accurate and help users correct any mistakes they make. This leads to a smoother and more user-friendly experience in your React applications. 📚

# 📚 Form Libraries

React form libraries are powerful tools that simplify the process of creating, handling, and validating forms in your React applications. These libraries provide a set of pre-built components, utilities, and abstractions to streamline form development, making it faster and more efficient.

## Why Use Form Libraries? 🤔

Form libraries offer several benefits:

-   **Reusability**: Pre-built form components can be easily reused across different parts of your application.
    
-   **Validation**: Many libraries come with built-in validation mechanisms to ensure data integrity.
    
-   **State Management**: Simplify state management for form inputs and submissions.
    

Let's introduce a popular React form library called Formik and demonstrate how it simplifies form handling:

## Using Formik 🌟

Formik is a widely used form library for React that simplifies form creation and management. It provides a powerful set of tools to handle form state, validation, and submission effortlessly.

Here's an example of how to use Formik:

``` jsx
import React from 'react';
import { useFormik } from 'formik';

const MyForm = () => {
  const formik = useFormik({
    initialValues: {
      email: '',
      password: '',
    },
    onSubmit: (values) => {
      // Handle form submission with the form values
      console.log('Submitted Values:', values);
    },
    validate: (values) => {
      const errors = {};

      // Add custom validation logic here
      if (!values.email.includes('@')) {
        errors.email = 'Invalid email address';
      }

      if (values.password.length < 6) {
        errors.password = 'Password must be at least 6 characters';
      }

      return errors;
    },
  });

  return (
    <form onSubmit={formik.handleSubmit}>
      <div>
        <label>Email:</label>
        <input
          type="email"
          name="email"
          value={formik.values.email}
          onChange={formik.handleChange}
        />
        {formik.errors.email && <div className="error">{formik.errors.email}</div>}
      </div>
      <div>
        <label>Password:</label>
        <input
          type="password"
          name="password"
          value={formik.values.password}
          onChange={formik.handleChange}
        />
        {formik.errors.password && (
          <div className="error">{formik.errors.password}</div>
        )}
      </div>
      <button type="submit">Submit</button>
    </form>
  );
};

export default MyForm;
```

**In this example:**

-   We import Formik and `useFormik` to create a form instance.
-   Formik manages form state, including initial values, submission logic, and validation.
-   The `validate` function defines custom validation rules for the form fields.
-   The form values and errors are easily accessible through the `formik` object.

By using Formik, you can simplify form handling and validation, making your React application development more efficient and maintainable. 🚀

Explore other popular React form libraries like Redux-Form, Final Form, or Yup for additional features and flexibility tailored to your project's needs. 📚


# **Activity: 📋 Form Validation Adventure in React Forms 🚀**

### **Objective:** 
Dive into the exciting world of React forms by creating a registration form with form validation and a sprinkle of Formik magic!

### **Instructions:**

1.  **Set Up Your React Playground:** 🏗️
    
    -   Open your code editor.
    -   Create a new React application (if you don't have one).
    -   Make sure you have Formik installed by running `npm install formik` or `yarn add formik`.
2.  **Design Your Registration Form:** ✏️
    
    -   Create a new component, let's call it `RegistrationForm.js`.
    -   Design a form with the following fields:
        -   First Name
        -   Last Name
        -   Email
        -   Password
3.  **Formik Setup:** 🌟
    
    -   Import Formik and other necessary dependencies at the top of your component:

``` javascript
import React from 'react';
import { Formik, Form, Field, ErrorMessage } from 'formik';
```

- Set up the initial values and validation schema:
``` javascript
const initialValues = {
  firstName: '',
  lastName: '',
  email: '',
  password: '',
};

const validationSchema = {
  firstName: Yup.string().required('First Name is required'),
  lastName: Yup.string().required('Last Name is required'),
  email: Yup.string().email('Invalid email address').required('Email is required'),
  password: Yup.string().min(6, 'Password must be at least 6 characters').required('Password is required'),
};
```

5.  **Form Validation Magic:** 🧙‍♂️
    
    -   Notice how we used `validationSchema` to define validation rules for each field.
    -   Error messages will automatically display when validation fails.
2.  **Handle Form Submission:** 📤
    
    -   In the `onSubmit` function, you can implement your form submission logic, such as sending data to a server or displaying a success message.
3.  **Test Your Form:** 🧪
    
    -   Start your development server (`npm start` or `yarn start`).
    -   Open your form in a web browser.
    -   Try submitting the form with different inputs to see how validation works.
4.  **Reflect and Expand:** 🤔
    
    -   Think about how form validation enhances user experience and data quality in web applications.
    -   Explore more Formik features and try adding custom validation rules.
5.  **Share Your Progress:** 📣
    
    -   If you're part of a course or community, share your registration form and any interesting discoveries with your peers.
6.  **Keep Exploring:** 🌐
    
    -   Continue your React journey, and remember that practice makes perfect!


# Applications 🚀

1.  🌐 **User Registration**: Implement form validation to ensure users provide accurate information when signing up for a website.
    
2.  📧 **Contact Forms**: Create contact forms with error handling to collect inquiries or feedback from users.
    
3.  🛡️ **Password Reset**: Build a password reset form that validates user input and securely handles password changes.
    
4.  🌟 **Search Filters**: Use controlled components to create search filters for a product catalog, enabling users to refine their searches.
    
5.  📝 **Feedback Surveys**: Develop interactive feedback surveys with validation to gather user opinions effectively.
    
6.  📤 **Data Submission**: Implement forms for data submission, such as job applications or content uploads, with error handling for incomplete or incorrect submissions.
    
7.  📊 **Survey Forms**: Create survey forms that validate responses and provide users with real-time feedback on their answers.
    
8.  📫 **Subscription Forms**: Design subscription forms for newsletters or updates, ensuring users provide valid email addresses.
    
9.  🛒 **Shopping Carts**: Use forms to manage item quantity and selection in an online shopping cart, with validation for stock availability.
    
10.  🗺️ **Address Forms**: Build address input forms with validation for accurate shipping or delivery information.
    

These practical applications demonstrate how form handling, validation, and error management play a crucial role in various aspects of web development. They contribute to better user experiences and data accuracy in your React.js applications. 🚀


# Summary 🚀

-   📋 **Controlled Components**: Learned how to create controlled form components to manage form input values in component state.

-   🌟 **Form Events**: Explored form events like `onChange` and `onSubmit` for capturing user interactions and form submissions.
-   📚 **Form Validation**: Discovered the importance of form validation to ensure data accuracy and error handling to provide user feedback.
-   📚 **Form Libraries**: Got introduced to popular React form libraries like Formik for simplifying form creation and management.

Day 3 has equipped you with essential skills for creating interactive and user-friendly forms in React, enabling you to build more robust web applications. 🚀


# 📋 Working with React Forms - Quiz 🧐

1.  🤔 What is the primary purpose of form validation in web development?
    
    -   a) To make forms look more attractive
    -   b) To ensure data accuracy and integrity
    -   c) To increase website loading speed
    -   d) To add animations to forms
    -   **Correct Answer:** b) To ensure data accuracy and integrity 🎯
2.  🌟 Which React library is commonly used for simplifying form creation and management?
    
    -   a) React-Form
    -   b) Forminator
    -   c) Formik
    -   d) Formify
    -   **Correct Answer:** c) Formik 🎯
3.  📝 What is the purpose of the `onChange` event in a form element?
    
    -   a) It triggers when the form is submitted.
    -   b) It handles form validation.
    -   c) It captures changes in the form input values.
    -   d) It resets the form.
    -   **Correct Answer:** c) It captures changes in the form input values. 🎯
4.  📚 What does the `onSubmit` event in a form do?
    
    -   a) It cancels form submission.
    -   b) It validates form data.
    -   c) It handles form submission.
    -   d) It changes form styling.
    -   **Correct Answer:** c) It handles form submission. 🎯
5.  🌟 Which form library allows you to define custom form validation logic easily?
    
    -   a) Formster
    -   b) Formify
    -   c) Formulator
    -   d) Formik
    -   **Correct Answer:** d) Formik 🎯
6.  📚 What is the purpose of error handling in forms?
    
    -   a) To make forms more colorful
    -   b) To display feedback to users when validation fails
    -   c) To increase server performance
    -   d) To hide form fields
    -   **Correct Answer:** b) To display feedback to users when validation fails 🎯
7.  🤔 Why use controlled components in React forms?
    
    -   a) To make forms less interactive
    -   b) To prevent form submission
    -   c) To manage form input values in component state
    -   d) To eliminate the need for form validation
    -   **Correct Answer:** c) To manage form input values in component state 🎯
8.  📝 In React, what function is used to prevent the default behavior of a form submission?
    
    -   a) `preventSubmission()`
    -   b) `cancelSubmission()`
    -   c) `e.stop()`
    -   d) `e.preventDefault()`
    -   **Correct Answer:** d) `e.preventDefault()` 🎯
9.  🌟 Which method is used to define custom validation rules for form fields in Formik?
    
    -   a) `validateField`
    -   b) `validateForm`
    -   c) `validateInput`
    -   d) `validate`
    -   **Correct Answer:** d) `validate` 🎯
10.  📚 What is the purpose of the `initialValues` property in Formik?
    
     -   a) To set the initial form state
     -   b) To define form validation rules
     -   c) To trigger form submission
     -   d) To hide form elements
     -   **Correct Answer:** a) To set the initial form state 🎯
11.  📝 Which form input type is used for email addresses in HTML?
    
     -   a) `email`
     -   b) `text`
     -   c) `password`
     -   d) `input`
     -   **Correct Answer:** a) `email` 🎯
12.  📚 What does the `validate` function in Formik return if there are no validation errors?
    
     -   a) An empty string
     -   b) An error message
     -   c) `undefined`
     -   d) An object with error messages
     -   **Correct Answer:** c) `undefined` 🎯
13.  🌟 Which event in a form is triggered when a user presses the "Submit" button?
    
     -   a) `onValidate`
     -   b) `onSubmit`
     -   c) `onChange`
     -   d) `onClick`
     -   **Correct Answer:** b) `onSubmit` 🎯
14.  📝 How can you prevent a form from being submitted when a user presses "Enter"?
    
     -   a) Use the `e.cancelSubmit()` method
     -   b) Use the `e.preventDefault()` method
     -   c) Use the `e.preventSubmission()` method
     -   d) Use the `e.stopPropagation()` method
     -   **Correct Answer:** b) Use the `e.preventDefault()` method 🎯
15.  📚 In React, what function is commonly used to handle changes in form input values?
    
     -   a) `handleInputChange`
     -   b) `handleChange`
     -   c) `handleFormChange`
     -   d) `onInputValueChange`
     -   **Correct Answer:** b) `handleChange` 🎯
16.  🌟 Which React form library is known for its simplicity and ease of use, making it suitable for many projects?
    
     -   a) Final Form
     -   b) Redux-Form
     -   c) Formik
     -   d) Formulate
     -   **Correct Answer:** c) Formik 🎯
17.  📝 What event is triggered when a user interacts with a form input field by typing or selecting an option?
    
     -   a) `onClick`
     -   b) `onMouseOver`
     -   c) `onFocus`
     -   d) `onChange`
     -   **Correct Answer:** d) `onChange` 🎯
18.  📚 How can you display an error message to the user when form validation fails using Formik?
    
     -   a) Use the `onError` event
     -   b) Use the `error` prop in the form component
     -   c) Add an error message directly to the form input
     -   d) Use the `errors` object in Formik
     -   **Correct Answer:** d) Use the `errors` object in Formik 🎯
19.  🌟 Which property in Formik is used to define custom validation logic for form fields?
    
     -   a) `validateInput`
     -   b) `onValidate`
     -   c) `validationRules`
     -   d) `validate`
     -   **Correct Answer:** d) `validate` 🎯
20.  📝 What does the `e.preventDefault()` method do in a form submission event?
    
     -   a) Stops the form from rendering
     -   b) Cancels the form submission
     -   c) Hides the form elements
     -   d) Resets the form to its initial state
     -   **Correct Answer:** b) Cancels the form submission 🎯
21.  📚 What is the primary purpose of form validation in web development?
    
     -   a) To improve form styling
     -   b) To increase server performance
     -   c) To ensure data accuracy and integrity
     -   d) To create interactive animations
     -   **Correct Answer:** c) To ensure data accuracy and integrity 🎯
22.  🌟 Which library allows you to manage form state, validation, and submission with ease in React applications?
    
     -   a) React-Formulate
     -   b) Formify
     -   c) Formik
     -   d) React-Validation
     -   **Correct Answer:** c) Formik 🎯
23.  📝 What is the purpose of the `initialValues` property in Formik?
    
     -   a) To set the initial form styling
     -   b) To define initial validation rules
     -   c) To set the initial form state
     -   d) To define initial form events
     -   **Correct Answer:** c) To set the initial form state 🎯
24.  📚 In Formik, where should you define custom validation rules for form fields?
    
     -   a) In the component's constructor
     -   b) In the `render` method
     -   c) In the `validate` function
     -   d) In the component's state
     -   **Correct Answer:** c) In the `validate` function 🎯
25.  🌟 Which event is triggered when a user submits a form in React?
    
     -   a) `onSubmit`
     -   b) `onClick`
     -   c) `onChange`
     -   d) `onValidate`
     -   **Correct Answer:** a) `onSubmit` 🎯


🌟 Today, you delved into the world of forms, mastering controlled components, handling form events, conquering form validation, and exploring the convenience of form libraries like Formik. Keep up the great work, and get ready for more exciting React adventures on Day 4! 🚀
