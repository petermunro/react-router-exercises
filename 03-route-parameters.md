# Using Route Parameters

1. Modify your components as follows, adding a new `<Account>` component and updating `<Clients>`:

        const Account = props => (
          <div>
            <h3>Clients {props.match.params.client}</h3>
            <p>URL: {props.match.url}</p>
            <p>Showing details for account {props.match.params.client}</p>
          </div>
        );


        const Clients = props => (
          <div>
            <h2>Component Two</h2>
            <Route path={`${props.match.path}/clients/:client`} component={Client} />
          </div>
        );

2. Which URLs can now reach and display the `<Client>` component? View the `match` prop for `<Client>` with different URLs.

3. Why do we have the path `${props.match.path}/clients/:client` in component `<Clients>`?

4. What happens if you omit the `client` parameter?

