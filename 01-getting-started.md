# Getting started with React Router

## Installation and `BrowserRouter`

1. Create a new app with `create-react-app`.

2. Install react-router:

    ```bash
    $ npm install react-router-dom
    ```

3. In your `index.js` (or `index.tsx`), import BrowserRouter:

    ```javascript
    import { BrowserRouter } from "react-router-dom";
    ```

4. Wrap a `<BrowserRouter>` around your top-level `<App>` render:

    ```js
    ReactDOM.render(
        <Router>
            <App />
        </Router>
    , document.getElementById('root'));
    ```

    5. For the CSS, I've created a simple [index.css](css/index.css) and an [App.css](css/App.css) which you can use.


## Setting up Navigation

1. In your `<App>` component, render a navigation element (`<nav>`) which will contain a list of links. Use `<Link>` from React Router to link to the following URLs:

    Link Name | URL Path
    ----------|---------
    Index     | /
    Home      | /home
    Clients   | /clients
    Invoices  | /invoices
    Unknown   | /unknown

   Here's an example:

    ```javascript
    <Link to="/home">Home</Link>
    ```

    > We will use the first and last items to test specific features.

2. In the browser, click or hover over each link in turn, and make sure the browser's URL changes. Also note any messages in the browser console.


## Setting up Basic Routing

1. We need some simple components to render for a given route.
   Create `Home`, `Clients` and `Invoices` components. For example, for `Home` you could use:

    ```javascript
    export const Home = () => (
        <div>
            <h2>Home</h2>
        </div>
    );
    ```

2. Now to use the `<Route>` element. It simply _conditionally renders_ its children when the location matches its path.

   In your `<App>` component, below your `<nav>`, render a `<Routes>` component containing three `<Route>` components, each one rendering the corresponding component for one of the paths `/home`, `/clients` and `/invoices`.
   
   It should do this only when its corresponding path matches. To do this, use the `path` and `element` props like this:

    ```javascript
    <Routes>
        ...
        <Route path="home" element={<Home />} />
        ...
    </Routes>
    ```
   

3. Ensure that each component is rendered when you visit its URL, and that `Home` is rendered _only_ when you visit `/home`.

## Adding an Index Route

If you navigate to `/` you will see a console error.

An __Index Route__ lets you specify what to render when there is no subsequent path.

Insert an Index Route into your list of routes. It's the same as the `"home"` route, but replace the `path="home"` with `index`.

Check that it works if you navigate to `/`.


## Adding a "No Match" Route

To capture URLs that are missing or no longer exist, add a __No Match Route__. It's a bit like a "404 Not found" page.

It's the same as the other `<Route>`s, but the path is simply a `"*"`.

You can have it take you to Home or to a custom component of your choice.



