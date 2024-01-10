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


