# Spa Documentation
In this doc. we are going to know about basic spa components and their usage
## Table of Content
---
1. [🔗What is spa?](#what-is-spa)
2. [🔗 Installation](#import-components)
2. [🔗Usage of spa components](#usage-of-spa-components)
## What is spa?
---
An SPA (Single Page Application) in React is a type of web app that loads only one web page. Instead of reloading the entire page each time you click something, it updates just the parts of the page that need to change. This makes the app feel faster and more responsive.

React uses client-side routing (like React Router) to manage how different sections of the app appear based on what you click, all without reloading the page.

## Import Components
---
Import component which are required for your project
```jsx
  import { Routes, Route, Link, useNavigate } from 'react-router-dom';
```

## Usage of Spa Components
---
- **`<Routes>`** is the container for routes, matching the first path.
- **`<Route>`** defines a URL path and links it to a component.
- **`<Link>`** allows navigation between routes without page reload.
- **`useNavigate()`** is used for programmatic navigation (replacing `useHistory()`).
- **`element={<Component />}`** is the new syntax for rendering components in routes.

---

### Full Code Example:

```jsx
import React from 'react';
import { Routes, Route, Link, useNavigate } from 'react-router-dom';

// Define the components for each page
const Home = () => <h2>Home Page</h2>;
const About = () => <h2>About Page</h2>;
const Contact = () => <h2>Contact Page</h2>;

const App = () => {
  // useNavigate hook is used to navigate programmatically
  const navigate = useNavigate();

  // Function to navigate to the 'Home' page
  const goToHome = () => {
    navigate('/home'); // Navigate programmatically
  };

  return (
    <div>
      {/* Navigation links */}
      <nav>
        <Link to="/home">Home</Link> {/* Navigate to the home page */}
        <Link to="/about">About</Link> {/* Navigate to the about page */}
        <Link to="/contact">Contact</Link> {/* Navigate to the contact page */}
        <button onClick={goToHome}>Go to Home (Programmatically)</button> {/* Programmatically navigate to home */}
      </nav>

      {/* Define routing for different pages */}
      <Routes>
        <Route path="/home" element={<Home />} /> {/* Renders Home component for /home route */}
        <Route path="/about" element={<About />} /> {/* Renders About component for /about route */}
        <Route path="/contact" element={<Contact />} /> {/* Renders Contact component for /contact route */}
      </Routes>
    </div>
  );
};

export default App;
```

---
