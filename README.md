                                                   React - A JavaScript library for building user interfaces

Declarative
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.

Component-Based
Build encapsulated components that manage their own state, then compose them to make complex UIs.

React can also render on the server using Node and power mobile apps using React Native.

FIRST CODE EXAMPLE:

class HelloMessage extends React.Component {
  render() {
    return (
      <div>
        Hello {this.props.name}
      </div>
    );
  }
}

ReactDOM.render(
  <HelloMessage name="Mahan" />,
  document.getElementById('hello-example')
);

RESULT:
Hello Mahan

WHAT IS HAPPENING IN THIS PIECE OF CODE:
React components implement a render() method that takes input data and returns what to display. This example uses an XML-like syntax called JSX. Input data that is passed into the component can be accessed by render() via this.props.

SECOND CODE EXAMPLE:

class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = { seconds: 0 };
  }

  tick() {
    this.setState(state => ({
      seconds: state.seconds + 1
    }));
  }

  componentDidMount() {
    this.interval = setInterval(() => this.tick(), 1000);
  }

  componentWillUnmount() {
    clearInterval(this.interval);
  }

  render() {
    return (
      <div>
        Seconds: {this.state.seconds}
      </div>
    );
  }
}

ReactDOM.render(
  <Timer />,
  document.getElementById('timer-example')
);
  
RESULT:
Increase in time from 1.

WHAT IS HAPPENING HERE?
A component can maintain internal state data (accessed via this.state). When a component’s state data changes, the rendered markup will be updated by re-invoking render().


  
