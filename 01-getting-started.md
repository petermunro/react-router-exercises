# Getting started with React Router

1. Create a new app with `create-react-app`.

2. Install react-router:

        $ npm install react-router-dom --save

    (The installation instructions are [here](https://reacttraining.com/react-router/web/guides/quick-start).)

3. Wrap a `<BrowserRouter>` around your top-level `<App>` render:

        ReactDOM.render(
            <BrowserRouter>
                <App />
            </BrowserRouter>
        , document.getElementById('root'));

## Adding a Route

1. Now to use the `<Route>` element. It simply _conditionally renders_ its children when the location matches its path.

    Keep your app _extremely_ simple:

        const Home = props => (
            <div>
                <h2>Home</h2>
            </div>
        );

        const One = props => (
            <div>
                <h2>Component One</h2>
            </div>
        );

        const Two = props => (
            <div>
                <h2>Component Two</h2>
            </div>
        );

        class App extends Component {
            render() {
                return (
                    <div>
                        <Route component={One} />
                    </div>
                );
            }
        }

## Understanding `<Route>`

1. Use the React DevTools to examine the props provided to component `<One>`. It is provided three props by the parent `<Route>`. What are they?

2. In React DevTools, examine the `location` prop of component `<One>`. What happens to it when you enter a new URL into the location bar? Try these (assuming your server is running on port 3000):

    - http://localhost:3000/foo
    - http://localhost:3000/foo/bar?baz
    - http://localhost:3000/foo/bar?param1=hello&param2=world
    - http://localhost:3000/foo/bar?baz#tab1

3. Now modify the `path` in your `<Route>`:

        render() {
            return (
                <div>
                    <Route path="/one" component={One} />
                </div>
            );
        }

    Again experiment by entering different URLs into the location bar. Check that the component is rendered when you expect it to be.

## Add a route Home

1. Add a route to the `<Home>` component and set the `path`s like this:

        render() {
            return (
                <div>
                    <Route path="/" component={Home} />
                    <Route path="/one" component={One} />
                </div>
            );
        }

    Which components get rendered with the following URLs? Also check the `location` and `match` props of each:

    - http://localhost:3000/
    - http://localhost:3000/one
    - http://localhost:3000/foo
    - http://localhost:3000/one/bar

## Understanding the `location` and `match` props

1. Use the URL `http://localhost:3000/one`. Are the `location` props the same or different for components `<Home>` and `<One>`?

2. What does `location` represent?

3. Do the same again for the `match` props for each component. Again, are they the same or different?

4. What does `match` represent for each component?

## Add an `exact` prop

1. Modify the first `<Route>`s path as follows:

        render() {
            return (
            <div>
                <Route path="/" component={Home} exact />
                <Route path="/one" component={One} />
            </div>
            );
        }

    How does this change behavior? Try these URLs to verify your understanding:

    - http://localhost:3000/
    - http://localhost:3000/one


## Adding a `<Link>`

1. Add two `<Link>` components:

        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/one">One</Link>
          </li>
        </ul>

    Check that these take you to the URLs you expect, and that they render the components you expect them to.
