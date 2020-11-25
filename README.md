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
    return Hi, I am a Car!;
  }
}

                                                                      Function Component
                                                                  
A Function component also returns HTML, and behaves pretty much the same way as a Class component, but Class components have some additions, and will be preferred in this tutorial.

Example:

function Car() {
  return Hi, I am also a Car!;
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
        My Car
      </div>
    );
  }
}

                                                         ReactJS - Environment Setup
PREREQUISITES:
1. NodeJS
2. NPM

After successfully installing NodeJS, we can start installing React upon it using npm. The most effective way is by using create-react-app command.

                                                       Using the create-react-app command
Step 1 - install create-react-app
Browse through the desktop and install the Create React App using command prompt as shown below −

C:\Users\Mahan>cd C:\Users\Mahan\Desktop\
C:\Users\Mahan\Desktop>npx create-react-app my-app
This will create a folder named my-app on the desktop and installs all the required files in it.

Step 2 - Delete all the source files
Browse through the src folder in the generated my-app folder and remove all the files in it as shown below −

C:\Users\Mahan\Desktop>cd my-app/src
C:\Users\Mahan\Desktop\my-app\src>del *
C:\Users\Mahan\Desktop\my-app\src\*, Are you sure (Y/N)? y

Step 3 - Add files
Add files with names index.css and index.js in the src folder as −

C:\Users\Mahan\Desktop\my-app\src>type nul > index.css
C:\Users\Mahan\Desktop\my-app\src>type nul > index.js
In the index.js file add the following code

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

Step 4 - Run the project
Finally, run the project using the start command.

npm start

After this you will get a basic starting point for building your React application.

![welcome-to-react](https://user-images.githubusercontent.com/41227164/100254507-80ddf200-2f6a-11eb-872c-7b2b3e19e494.png)
