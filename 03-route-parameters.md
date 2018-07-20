# Using Route Parameters

1. Modify your components as follows, adding a new `<Account>` component and updating `<Two>`:

        const Account = props => (
          <div>
            <h3>Account {props.match.params.account}</h3>
            <p>URL: {props.match.url}</p>
            <p>Showing details for account {props.match.params.account}</p>
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
            <Route path={`${props.match.path}/accounts/:account`} component={Account} />
          </div>
        );

2. Which URLs can now reach and display the `<Account>` component? View the `match` prop for `<Account>` with different URLs.

3. Why do we have the path `${props.match.path}/accounts/:account` in component `<Two>`?

4. What happens if you omit the `account` parameter?

