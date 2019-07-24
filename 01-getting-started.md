# Getting started with React Router

## Installation and `BrowserRouter`

1. Create a new app with `create-react-app`.

2. Install react-router:

        $ npm install react-router-dom --save

    (The installation instructions are [here](https://reacttraining.com/react-router/web/guides/quick-start).)

3. In your `index.js`, import BrowserRouter:

        import { BrowserRouter as Router } from "react-router-dom";

4. Wrap a `<BrowserRouter>` around your top-level `<App>` render:

        ReactDOM.render(
            <Router>
                <App />
            </Router>
        , document.getElementById('root'));


## Setting up Navigation

1. Render a navigation element (`<nav>`) which will
   contain a list of links. Use `<Link>` from React Router to link to the following URLs:

    Link Name | URL Path
    ----------|---------
    Home      | /
    Clients   | /clients
    Invoices  | /invoices


2. In the browser, hover over or click each link in turn, and make sure the browser's URL changes.


## Setting up Basic Routing

1. We need some simple components to render for a given route.
   Create `Home`, `Clients` and `Invoices` components. For example,
   for `Home` you could use:

        const Home = props => (
            <div>
                <h2>Home</h2>
            </div>
        );

2. Now to use the `<Route>` element. It simply _conditionally renders_ its children when the location matches its path.

   Render three `<Route>` components, each one rendering one of
   the three components above, and only when its corresponding path
   matches. To do this, use the `path` and `component` props.

3. Ensure that each component is rendered when you visit its URL,
   and that `Home` is rendered _only_ when you visit `/`.