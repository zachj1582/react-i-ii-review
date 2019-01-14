### Remember

Answer these on your own, then compare answers as a group

1.  What is React?

- React is a Javascript library for building user interfaces that uses a component based architecture and unidirectional data flow.

2.  What is create-react-app?

- create-react-app is a library that creates a basic React project for us. It also sets up a development environment with auto-refresh to make development easier.

3.  What is Component Based Architecture?

- The concept of encapsulating individual pieces of a larger user interface into self-sustaining, independent pieces.

4.  What is JSX?

- JSX is the syntax that React uses to describe a User Interface. It looks a lot like HTML, but is eventually transpiled into a regular Javascript function call.

5.  What is the virtual DOM?

- The virtual DOM is a Javascript copy of the elements displayed on a webpage. React updates the virtual DOM when any changes to a component are made, and then uses the virtual DOM to decide what parts of the actual DOM to change, and only updates the pieces that actually need to be updated.

6.  What is unidirectional (one-way) data flow?

- Data passed from a parent to a child. In React, you use props to do this.

### Understand

Discuss these questions in pairs if you have a 4-person group

7.  Summarize what happens when you run `create-react-app my-app`

- create-react-app creates a new folder called my-app that contains all the boilerplate code for a new React application. It creates a git repository and also creates a package.json file so that other libraries can be incorporated into the project.

8.  Explain what this code does:

```jsx
import React from "react";

const Mentor = props => (
  <div className="mentor-container">
    <h1 className={props.title === "Lead Mentor" ? "lead" : ""}>Tim Biles</h1>
    <ul>
      <li>Fort Worth, TX</li>
      <li>My email address is timbilestimbiles@gmail.com</li>
    </ul>
  </div>
);

export default Mentor;
```

- This creates a functional, stateless Mentor component that display's a person's information. It is expecting a `title` prop to be passed in. If that prop has a value of "Lead Mentor" then React applies a class of `lead`. Otherwise, there is no class.

9.  Explain how data is passed from a parent component to a child component.

- Using props. Ex. <Child propName={propValue} />

### Apply

Try these on your own, but work together if you start to get stuck.

10. Use `create-react-app` to create a new React application called `student-directory`

11. Use the code from `Mentor` above to create a new component called `User` with a list of friends. Hard code the list of friends, do not use state or props.

```jsx
const User = props => (
  <ul>
    <li>Friend 1</li>
    <li>Friend 2</li>
  </ul>
);
```

### Analyze, Evaluate, Create

Discuss these questions as a group

12. What are the benefits and drawbacks of using a tool like create-react-app?

13. Compare and contrast JSX with other templating options, such as those used in Angular or Vue

14. Compare and contrast one-way data flow with two-way data binding.
