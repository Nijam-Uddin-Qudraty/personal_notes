# React route

### Table of content
1. [React Route](#whats-react-route)
2. [CreateBrowserRouter](#why-createbrowserrouter)
3. [Works of CreateBrowserRouter](#how-createbrowserrouter-works)
4. [Installation](#installation)
5. [Usage](#usage-of-createbrowserrouter)

### What's react route?
- React route is used for creating URLs.
- It loads data without **reloading the page** or **server reloading**.
- It changes visible data using the URL.

**NOTE**: Basically, using React routes' base component `Route` is not a good practice. So, we'll use a new approach with `createBrowserRouter()` and `RouterProvider`.

---

### Why `createBrowserRouter()`?

- React routes need to provide routes separately and manually.
- Instead of routing manually, `createBrowserRouter()` creates a structured route configuration in an array format.
- It helps organize routes in a declarative manner, without needing to write a lot of extra code.

---

### How `createBrowserRouter()` works?

- It creates an array in JavaScript to store routes.
- It usually requires a base object named `path` and `element`.
  > `path` is used for creating the routing path.  
  > `element` is used for rendering data to the path when called.

#### Example:

```jsx

const router = createBrowserRouter([
  { path: "/", // Route url
  element: <Home /> //Routes component
  }
]);

```

---

So, now we got a basic idea of how `createBrowserRouter()` works. Let’s see how we can install it for our React projects.

### 🛠️ Installation

First of all, we have to install `react-router-dom` in our working folder.

To install react-router, use the following command:

```bash
npm install react-router-dom
```

For Yarn:

```bash
yarn add react-router-dom
```

After installing the router, we have to import the necessary components.

It requires **`createBrowserRouter`** and **`RouterProvider`**. Let's import them:

```jsx
import { createBrowserRouter, RouterProvider } from 'react-router-dom';
```

---

### Usage of `createBrowserRouter()`

We need to use **`createBrowserRouter()`** to define and structure routes.

The router is passed an array with route objects. Here's how we define the routes:

```jsx
const router = createBrowserRouter([
  { path: "/", element: <HomePage /> },    // <HomePage /> is a component
  { path: "/about", element: <AboutPage /> } // <AboutPage /> is a component
]);
```

**Note**: We can use components directly in `element`, and it's recommended to avoid using raw HTML tags directly for better practices.

After creating routes, we have to show the output using **`RouterProvider`**.

```jsx
function App() {
  return (
    <RouterProvider router={router} />
  );
}
```

---

### Code overview:
```jsx
import React from 'react';
import { createBrowserRouter, RouterProvider } from 'react-router-dom';
import HomePage from './pages/HomePage';
import AboutPage from './pages/AboutPage';

const router = createBrowserRouter([
  { path: "/", element: <HomePage /> },
  { path: "/about", element: <AboutPage /> },
]);

function App() {
  return <RouterProvider router={router} />;
}

export default App;
```

