## Detailed instructions

1. Create a new React app:

        $ create-react-app my-react-router-app
        $ cd my-react-router-app
        $ npm install
        $ npm start

2. Install React Router:

        $ npm install react-router-dom --save

3. At the top of `index.js`, import `BrowserRouter`:

        import { BrowserRouter } from 'react-router-dom';

4. Further down in `index.js`, wrap your top-level render in `<BrowserRouter>`:

        ReactDOM.render((
          <BrowserRouter>
            <App/>
          </BrowserRouter>
        ), document.getElementById('root'));

5. Test that your app renders. Also make sure in React devtools that `<BrowserRouter>` renders.

6. In `App.js`:

   1. Import:

          import { Link, Route } from 'react-router-dom';


   2. Now to have something to route to... Copy and import the [TweetBox](https://github.com/petermunro/react-component-exercises/blob/master/10-a-twitter-sms-input-component.md) you developed in the React class (or its [solution](https://gist.github.com/petermunro/1fb53b22cc0de003157f47fcf45ffd08)).

   3. We need to give it a prop (`onSend`), but the `<Route>` component doesn't let us.
   Ao add a `TweetBoxWrapper` class:

           class TweetBoxWrapper extends Component {
             render() {
               return <TweetBox onSend={this.handleSend} />;
             }

             handleSend(message) {
               console.log(`Sending ${message}...`);
             }
           }

    3. In the `App`, render this:

            render() {
              return (
                <div>
                  <nav>
                    <Link to="/tweet">Tweet</Link>
                  </nav>
                  <div>
                    <Route path="/tweet" component={TweetBoxWrapper} />
                  </div>
                </div>
              );
            }
