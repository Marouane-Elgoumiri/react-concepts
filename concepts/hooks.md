# useEffect

The `useEffect` hook allows you to perform side effects in your components, such as fetching data or subscribing to events.

### Syntax

```javascript
useEffect(() => {
    // Your side effect logic goes here.
    return () => {
        // Optional cleanup logic goes here.
    };
}, [dependencies]);
```

### Parameters

- Effect Callback: A function that contains the code for the side effect.
- Cleanup Function (optional): A function returned from the effect callback to clean up before the next effect runs or when the component unmounts.
- Dependency Array: An array of values that the effect depends on. If any value in this array changes, the effect will re-run.

```javascript
import React, { useState, useEffect } from 'react';

const DataFetchingComponent = () => {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []); // Empty dependency array means it runs once on mount

  return (
    <div>
      {data.map(item => (
        <div key={item.id}>{item.name}</div>
      ))}
    </div>
  );
};

export default DataFetchingComponent;

```
## Data Fetching:
The `useEffect` hook is commonly used for fetching data from an API when the component mounts.

```javascript
import React, { useState, useEffect } from 'react';

const DataFetchingComponent = () => {
    const [data, setData] = useState([]);

    useEffect(() => {
        fetch('https://api.example.com/data')
            .then(response => response.json())
            .then(data => setData(data))
            .catch(error => console.error('Error fetching data:', error));
    }, []); // Empty array means this effect runs once on mount

    return (
        <div>
            {data.map(item => (
                <div key={item.id}>{item.name}</div>
            ))}
        </div>
    );
};

export default DataFetchingComponent;

```
## Subscribing to Events:
You can use `useEffect` to set up subscriptions, such as listening for browser events.
```javascript
import React, { useEffect } from 'react';

const WindowSizeComponent = () => {
    const [windowSize, setWindowSize] = React.useState(window.innerWidth);

    useEffect(() => {
        const handleResize = () => setWindowSize(window.innerWidth);
        
        window.addEventListener('resize', handleResize);
        
        // Cleanup listener on unmount
        return () => window.removeEventListener('resize', handleResize);
    }, []); // The effect runs once when the component mounts

    return <div>Window size: {windowSize}px</div>;
};

export default WindowSizeComponent;

```
