### Remember

Use https://reactjs.org/docs/react-component.html#the-component-lifecycle and http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/ to answer these on your own then compare answers as a group

1.  Each component has several `lifecycle methods` that you can override to do what?
to fire functions at different parts of the rendering process

2.  What are the 4 categories of lifecycle methods? (these are the headings from the first link)
initialization, mounting, updating, unmounting

3.  What are the names of the 5 commonly used lifecycle methods? (these are in bold in the first link)
render
componentdidupdate
componentdidmount
componentwillunmount
constructor

### Understand

Discuss this question in pairs if you have a 4-person group

4.  What's going on in this code?

creating a class component named mentor with display info and a button, when the button is clicked it will fire componentDidUpdate that will console log 'logan saved the day'. I cannot confirm whether he in fact did save the day however.

```jsx
import React, { Component } from "react";

class Mentor extends Component {
  componentDidUpdate() {
    ("Logan saved the day!");
  }
  render() {
    return (
      <div>
        <h1>Logan Mace</h1>
        <h2>{this.props.questions.length}</h2>
        <h3>questions to answer</h3>
        <button onClick={this.props.answerQuestion}>Answer a question!</button>
        <p></p>
      </div>
    );
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Update the `Mentor` component above so that the message that is currently being console.log'd is displayed below the number of questions answered instead.
