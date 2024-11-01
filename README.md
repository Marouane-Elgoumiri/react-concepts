# React.js Mastery Concepts
<div align="center">

![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![React Hook Form](https://img.shields.io/badge/React%20Hook%20Form-%23EC5990.svg?style=for-the-badge&logo=reacthookform&logoColor=white)
</div>
This repository aims to cover essential React.js concepts for entry-level developers preparing for full-stack internship positions. Each concept is explained with theory and practical code examples.

## Table of Contents

- [Component Architecture](./concepts/component-architecture.md)
- [Props and State](./concepts/props-and-state.md)
- [Lifecycle Methods](./concepts/lifecycle-methods.md)
- [Hooks](./concepts/hooks.md)
- [Context API](./concepts/context-api.md)
- [Routing](./concepts/routing.md)
- [Forms](./concepts/forms.md)
- [Error Boundaries](./concepts/error-boundaries.md)

## Getting Started

To get started with the examples in this repository, clone the repository and run:

```bash
npm install
npm start
```

### Example Concept File: `concepts/props-and-state.md`

# Props and State

In React, **props** (short for properties) and **state** are two essential concepts that help manage data in a component.

## Props

Props are used to pass data from a parent component to a child component. They are immutable within the child component.

### Example:

```javascript
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

const ParentComponent = () => {
  return <ChildComponent name="John" />;
};

export default ParentComponent;
```

```javascript
// ChildComponent.js
import React from 'react';

const ChildComponent = (props) => {
  return <h1>Hello, {props.name}!</h1>;
};

export default ChildComponent;
```

## State

State is used to manage data that can change over time within a component. Unlike props, state is mutable and can be updated using the setState function.

### Example

```javascript
// StatefulComponent.js

import React, { useState } from 'react';

const StatefulComponent = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
};

export default StatefulComponent;
```


### Example Concept File: `concepts/hooks.md`


# Hooks

Hooks are functions that let you use state and other React features in functional components. The most common hooks are `useState` and `useEffect`.

## useState

The `useState` hook allows you to add state to your functional components.

### Example:

```javascript
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};

export default Counter;
```

