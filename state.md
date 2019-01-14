### Remember

Answer these on your own, then compare answers as a group

1.  What is state?

- State is data that is being managed by a component.

2.  Where do you set initial state?

- In the constructor, right after calling super();

3.  What method do you use to update state?

- this.setState({propert: value})

### Understand

Discuss this question in pairs if you have a 4-person group

4.  Explain what's happening in this component.

```jsx
import React, { Component } from "react";

class LeadMentor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAnswered: this.state.questionsAnswered + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Tim Biles</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <button onClick={this.handleClick}>Increase Answers</button>
    </div>;
  }
}
```

- This code creates a LeadMentor component that displays the number of questions answered from state. Every time the user clicks on the button, the number of questions answered on state increases by 1.

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Create a `Student` component that keeps track of the number of questions the student has asked, with a button that adds 1 to the total when it's clicked

```jsx
import React, { Component } from "react";

class Student extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAsked: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAsked: this.state.questionsAsked + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Student</h1>
      <h3>{this.state.questionsAsked}</h3>
      <h3>questions asked today</h3>
      <button onClick={this.handleClick}>Increase Questions</button>
    </div>;
  }
}
```

6.  Now add a text input where the student can type in their questions with a button to add them to a list of questions that is displayed below the number of questions asked.

```jsx
import React, { Component } from "react";

class Student extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: [],
      newQuestion: ""
    };

    this.handleClick = this.handleClick.bind(this);
  }

  handleChange(e) {
    this.setState({ newQuestion: e.target.value });
  }
  handleClick() {
    this.setState({
      questionsAnswered: [
        ...this.state.questionsAnswered,
        this.state.newQuestion
      ]
    });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Student</h1>
      <h3>{this.state.questionsAnswered.length}</h3>
      <h3>questions answered today</h3>
      <ul>
        {this.state.questionsAnswered.map(question => (
          <li>{question}</li>
        ))}
      </ul>
      <input onChange={this.handleChange} value={this.state.newQuestion} />
      <button onClick={this.handleClick}>Ask Question</button>
    </div>;
  }
}
```

### Analyze, Evaluate, Create

Discuss these questions as a group

7.  Could your `Student` component be refactored into a functional component? Why or why not?

- No, it could not, because it needs state and functional components cannot use state.

8.  What are the pros and cons of using a class method for an event handler vs. using an arrow function inline?

- A class method can have better performance because an arrow function in line would have to be recreated for every render. However, an arrow function would avoid any problems with the keyword this and there would be no need for binding in the constructor. Also, class methods may be better for code readability instead of trying to put everything inline.

9.  The render() method is called every time a component's state is updated. For a text input, that means the render method is called for every keypress. Why isn't this bad for performance?

- Just because the render method is called doesn't mean the actual DOM is re-rendered every time.
