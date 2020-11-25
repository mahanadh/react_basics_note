                                                   React - A JavaScript library for building user interfaces

                                                                        Declarative:
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.

                                                                        Component-Based:
Build encapsulated components that manage their own state, then compose them to make complex UIs.React can also render on the server using Node and power mobile apps using React Native.

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


                                                                 REACT COMPONENTS 
                                                                 
Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and returns HTML via a render function.
Components come in two types, Class components and Function components, in this tutorial we will concentrate on Class components.

                                                                  Class Component
When creating a React component, the component's name must start with an upper case letter. The component has to include the extends React.Component statement, this statement creates an inheritance to React.Component, and gives your component access to React.Component's functions. The component also requires a render() method, this method returns HTML.

Example:

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

                                                                  Function Component
                                                                  
A Function component also returns HTML, and behaves pretty much the same way as a Class component, but Class components have some additions, and will be preferred in this tutorial.

Example:

function Car() {
  return <h2>Hi, I am also a Car!</h2>;
}

                                                                  React Props
React Props are like function arguments in JavaScript and attributes in HTML. To send props into a component, use the same syntax as HTML attributes:

Example: 

const myelement = <Car brand="Ford" />;

                                                                  React State
                                                                  
React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

Creating the state Object:

Example:

class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {brand: "Ford"};
  }
  render() {
    return (
      <div>
        <h1>My Car</h1>
      </div>
    );
  }
}
