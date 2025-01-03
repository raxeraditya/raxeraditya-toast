## Beautiful Toast

A beautiful, modern toast component for React applications with TailwindCSS.

### Installation

```bash
npm install raxeraditya-toast
```

### Usage

1. First, ensure you have TailwindCSS set up in your project and add the following to your tailwind.config.js:

```js
module.exports = {
  content: [
    // ... your content configuration
    "./node_modules/raxeraditya-toast/**/*.{js,ts,jsx,tsx}",
  ],
};
```

2. Import and use the toast component:

```tsx
import { useNotification } from "@raxeraditya-toast";

//Postions
// "bottom-left"
// "bottom-right"
// "top-left"
// "top-right"
// Use NotificationComponent in your JSX to display notifications:
const { NotificationComponent, triggerNotification } =
  useNotification("top-left");

// Trigger notifications using the triggerNotification function:
triggerNotification({
  type: "success",
  message: "This is a success message!",
  duration: 3000,
});

//Animations
// You can specify an animation type for the notifications. The available animations are:

// "fade"
// "pop"
// "slide"
triggerNotification({
  type: "success",
  message: "This is a success message with a pop animation!",
  duration: 3000,
  animation: "pop",
});
```

3. Add the Toaster component to your app:

```tsx
useNotification(position: PositionType)

// example
import React from "react";
import useNotification from "react-toast-popup";

function App() {
  const { NotificationComponent, triggerNotification } =
    useNotification("top-left");

  const handleButtonClick = () => {
    triggerNotification({
      type: "success",
      message: "This is a success message!",
      duration: 3000,
    });
  };

  return (
    <div className="App">
      {NotificationComponent}
      <h1>Toast Component</h1>
      <button onClick={handleButtonClick}>Show Success</button>
    </div>
  );
}

export default App;
```

### License

MIT
