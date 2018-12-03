### Remember

Answer these on your own, then compare answers as a group

1.  What is create-react-app?

2.  What is JSX?

3.  What is the virtual DOM?

4.  What is unidirectional (one-way) data flow?

### Understand

Discuss these questions in pairs if you have a 4-person group

5.  Summarize what happens when you run `create-react-app app`

6.  Explain what this code does:

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

7.  Explain how data is passed from a parent component to a child.

### Apply

Try these on your own, but work together if you start to get stuck.

8.  Use create-react-app to create a new React application called "student-directory"

9.  Use the code from Student above to create a new component called User with a list of friends. Hard code the list of friends, do not use state or props.

### Analyze, Evaluate, Create

Discuss these questions as a group

10. What are the benefits and drawbacks of using a tool like create-react-app?

11. Compare and contrast JSX with other templating options, such as those used in Angular or Vue

12. Compare and contrast one-way data flow with two-way data binding.
