### Remember

Answer these on your own, then compare answers as a group

1.  What are props?

- Data passed from a parent to a child

2.  How do you pass props from a parent to a child?

- <Child propName="propValue" />

3.  How do you access props from a class based child component?

- this.props

4.  How do you access props from a functional component?

- props (which comes from the parameter of the function)

5.  How do you bind a function to a parent component so that it can be passed to a child?

- this.functionName = this.functionName.bind(this)

### Understand

Discuss this question in pairs if you have a 4-person group

6.  What's happening in this component?

```jsx
import React, { Component } from "react";

class Queue extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questions: []
    };

    this.askQuestion = this.askQuestion.bind(this);
    this.answerQuestion = this.answerQuestion.bind(this);
  }
  askQuestion(newQuestion) {
    const questions = [...this.state.questions, newQuestion];
    this.setState({ questions });
  }
  answerQuestion(index) {
    const questions = [...this.state.questions];
    questions.splice(index, 1);
    this.setState({ questions });
  }
  render() {
    <div className="queue-container">
      <h1>The Queue</h1>
      <h3>{this.state.questions.length}</h3>
      <h3>questions need answers</h3>
      <Student askQuestion={this.askQuestion} />
      <Mentor
        answerQuestion={this.answerQuestion}
        questions={this.state.questions}
      />
    </div>;
  }
}
```

- The Queue component contains a Student and Mentor component. The method this.askQuestion is being passed to the Student component with a prop name of askQuestion. When it runs from the Student component, it adds a new question to the list of questions on the parent's state. A different function is passed to the Mentor component to remove a question from the list of questions on state.

### Apply

Try these on your own, but work together if you start to get stuck.

7.  Using the `Queue` component above, create a `Student` component that can add a question as a string and a `Mentor` component that can remove a question from the array.

```jsx
class Student extends Component {
  constructor(props) {
    super(props);
    this.state = {
      question: ""
    };
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(e) {
    this.setState({ question: e.target.value });
  }
  render() {
    return (
      <div>
        <h1>Student Component</h1>
        <input
          type="text"
          name="question"
          onChange={this.handleChange}
          value={this.state.question}
        />
        <button onClick={() => this.props.askQuestion(this.state.question)}>
          Ask Question
        </button>
      </div>
    );
  }
}
```

```jsx
const Mentor = (props) => {
  return (
    <div>
      <ul>
        {props.questions.map((question, i) => (
          <li>{question}
            <button onClick={() => props.answerQuestion(i)}>Answer</button>
          </li>))}
      </ul>
    </div>)
  }
}
```

### Analyze, Evaluate, Create

Discuss these questions as a group

8.  In the Queue component above, why are we holding state in the Queue component instead of Mentor or Student?

- Because both the Mentor and Student components need access to the same data, so that data must come from a common parent of both.
