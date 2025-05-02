# Nested Routing

### Introduction
Time is important for everyone. In order to make our website faster and save our team, We need a one page website. That's makes our work easier without loading data repeatedly.
So, for making our website one page we have to add nested route in [React Routing System](React_Route.md).

*Nested routs are used under a base route. It gives data from the route without interrupting or reloading website*

### Adding nested route -

-   We have to add a child object named `children`
-   Now we can add `path` and `elements` like before as the parent route.
    *Example*

```jsx
const router = createBrowserRouter([
	{
		path: "/",
		element: <Root></Root>,
		children: [
			{
				path: "/",
				element: <Home></Home>,
			},
			{
				path: "/listed_books",
				element: <h1>this is listed book section</h1>,
			},
			{
				path: "/pages_to_read",
				element: <h1>wishlist</h1>,
			},
			{
				path: "/sign_in",
				element: <h2>sign in page</h2>,
			},
			{
				path: "/sign_up",
				element: <h1>sign up page</h1>,
			},
		],
	},
]);
```
### Dependencies
- In order to show data to our project we have to use a component named `Outlet`
- We will use it between static web behavioral sections like - **navbar** and **footer**
- We can import it from `react-router-dom`
```jsx
import { Outlet } from 'react-router-dom';
```
* Usage of `Outlet`
```jsx
const Root = () => {
    return (
        <div className="max-w-6xl mx-auto">
            <Navbar></Navbar>
            <Outlet></Outlet>
            <Footer></Footer>
        </div>
    );
};
```
