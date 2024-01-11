# Frontend interview preparation 

### 1 What are State and props in react.js ? 

States manage components data they are like dynamic variable variables thant can change over time. state change value using useState() hook.

props are data which component receives and props are immutable. 

- State example 
```javascript
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
  
- Props example 
```javascript

import React from 'react';

function Greet(props) {

// receive props as name="john" in prop object
  return <p>Hello, {props.name}!</p>;
}

// Usage
<Greet name="John" />


```

### 2 what is mean by Hooks in react? 

Hooks are nothing but the javascript function that serves the specific task.
example :- useState(), UseEffect(), useReducer(), useContext(),useCallback(), useMemo()

### 3 What is JSX in react?

JSX is nothing but javascriptXML. which allows user to use javascript in html.
this is html like syntax. but it is not html.

### 4 What is the react components ? 

Building blocks of the react application, small chunks of code that can be reused while needed, components are made app clean and code readable.

### 5 What are the HOC components in react ? 
 
 *When a react function takes a component and returns a component that are called HOC in react. 

### 6 How do you pass data to different components .
 - Prop drilling 
    - sending data from parent to child and child to grandchild

- Context API
    - Central place to store the data and call it from any function if data does not change often

- Redux Store
  - If application is scalable we use redux that stores data in central place and we call or subscribe to the store and get data from it.

### 7 Controlled and Uncontrolled components in react ? 

For example if you does not use state variable to control input value  that are uncontrolled values.
in normal html code inputs are uncontrolled.

### 8 What are the Error Boundaries?
Error boundaries are a feature in React that allows components to catch JavaScript errors anywhere in their component tree and log those errors, display a fallback UI. 
```javascript 
import React, { Component } from 'react';

class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, errorInfo) {
    // You can log the error to an error reporting service
    console.error("Error caught by boundary:", error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      // Fallback UI when an error occurs
      return <p>Something went wrong. Please try again later.</p>;
    }

    return this.props.children;
  }
}

// Usage
class MyComponent extends Component {
  render() {
    // This component might throw an error
    return <p>{this.props.value.foo.bar}</p>;
  }
}

// Wrap MyComponent with ErrorBoundary
const MyComponentWithErrorBoundary = () => (
  <ErrorBoundary>
    <MyComponent value={{}} />
  </ErrorBoundary>
);


```

### Q9 What are Keys in react ? 

In React, keys are special attributes that provide a way to uniquely identify elements in a collection of elements. 
Each element in a React array should have a unique key assigned to it. The key is not accessible within the component using it but is important for React's internal reconciliation algorithm to optimize the rendering process. When React updates the UI due to changes in the data, it looks at the keys to determine which elements are added, removed, or changed.

### 10 What are synthetic events in React?

In React, synthetic events are a wrapper around the native browser events.
```javascript
import React from 'react';

const MyForm = () => {
  const handleSubmit = (e) => {
    // 'e' is a synthetic event
    e.preventDefault();
    console.log('Form submitted!');
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
};

export default MyForm;

```
In this example, the handleSubmit function is an event handler for the form's onSubmit event. The e.preventDefault() prevents the default form submission behavior, allowing you to handle the submission manually. The e object is a synthetic event provided by React, and preventDefault is one of its methods.

# 11 Difference between Virtual dom and Real Dom ?
