### Remember

Answer these on your own, then compare answers as a group

1.  What is React?
  JavaScript library

2.  What is create-react-app?
  command to create a new react app downloading all of the necasaries

3.  What is Component Based Architecture?
  breaks up code into smaller more manageable chunks

4.  What is JSX?
  is a syntactical way of writing JS that incorporates html

5.  What is the virtual DOM?
  it communicates with the actual dom to only update changes instead of refreshing the entire dom with every update

6.  What is unidirectional (one-way) data flow?
 data only flows in one direction, in react it only flows down (parent to child)
### Understand

Discuss these questions in pairs if you have a 4-person group

7.  Summarize what happens when you run `create-react-app my-app`
  your computer make a JS library called my app

8.  Explain what this code does:
  this is creating a functional(dumb) component that will be used to build a list section on a webpage

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

9.  Explain how data is passed from a parent component to a child component.
  with the props tag; in the parent you assign it to the child component tag, in the child component you reference the data with the props tag to incorporate the contained data into the component

### Apply

Try these on your own, but work together if you start to get stuck.

10.  Use `create-react-app` to create a new React application called `student-directory`

11.  Use the code from `Mentor` above to create a new functional, stateless component called `User` with a list of friends. Hard code the list of friends, do not use state or props.

### Analyze, Evaluate, Create

Discuss these questions as a group

12. What are the benefits and drawbacks of using a tool like create-react-app?

13. Compare and contrast JSX with other templating options, such as those used in Angular or Vue

14. Compare and contrast one-way data flow with two-way data binding.
