# Using React Router

1. To install react-router, follow the installation instructions [here](https://reacttraining.com/react-router/web/guides/quick-start).

2. First, use the example they provide to get familiar with:
   - `<Route>`
      - What does the `path` represent?
      - What other attributes are there?
   - `<Link>`
   - `<Router>`


3. Wrap a `<BrowserRouter>` around your top-level `<App>` render:

        ReactDOM.render(
        <BrowserRouter>
            <App />
        </BrowserRouter>, document.getElementById('root'));

4. Now to use the `<Route>` element. It simply _conditionally renders_ its children when the location matches its path.

    Keep your app _extremely_ simple:

        const One = props => (
            <div>
                <h2>Component One</h2>
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

5. Use the React DevTools to examine the props provided to component `<One>`. In particular, examine the `location` prop.

6. What happens when enter a new URL into the location bar? Try these (assuming your server is running on port 3000):

    - http://localhost:3000/foo
    - http://localhost:3001/foo/bar?baz
    - http://localhost:3001/foo/bar?param1=hello&param2=world
    - http://localhost:3001/foo/bar?baz#tab1

7. Now modify the `path` in your `<Route>`:

        render() {
            return (
            <div>
                <Route path="/foo/bar" component={One} />
            </div>
            );
        }

    Experiment by entering different URLs into the location bar. Check that the component is rendered when you expect it to be.

## Adding a `<Link>`

1. Add a `<Link>` component, for example:

        <Link to="/foo">One</Link>

    Check that this takes you to the URL you expect.

8. Now using `<Route>`, have your app route to various components you have developed, or make some new ones (like `<One>` above). It would be great if you could have URLs which direct the user to your:
    - `<TweetBox>`
    - `<ContactList>`
    - `<EditInvoice>`




### Troubleshooting

#### `npm start` fails

If you get an error, eg "sh: react-scripts: command not found", do an `npm install` again. If that doesn't work, follow [these instructions](https://stackoverflow.com/questions/39959900/npm-start-error-with-create-react-app#answer-39960890).
