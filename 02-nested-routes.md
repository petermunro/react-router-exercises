# Using Nested Routes

## Adding Secondary Navigation

1. In `<Clients>`, add nested links like this, one each for the three clients below:

    ```javascript
    <Link to={`/clients/acme`}>ACME Inc</Link>
    ```

    - ACME Inc
    - Baker and Sons
    - Chortleware

    You can of course generate these programmatically.

    > If you place your list of links inside a `<nav className="secondary">`, my `App.css` file will style them:

    ```javascript
    <nav className="secondary">
        <ul>
            <li>
                <Link to={`/clients/acme`}>ACME Inc</Link>
            </li>
            ...
    ```

2. Check that the URL changes when you click on these links.


## Adding Nested Routes

1. In your `<App>`, add nested routes for these clients. Here's an example:

    ```javascript
    <Route path="clients" element={<Clients />}>
        <Route path="acme" element={<Client />} />
    </Route>
    ```

    Add a new React component, `<Client>` to simply display a heading "Client" for every client. We will add to this later.

2. In your `<Clients>` component, add an `<Outlet />`:

    ```javascript
        ...
        </ul>
        </nav>

        <Outlet />
    </div>
    ```


    This serves as a placeholder: it displays matching "children" routes.

    Notice that in your Route definition, the Route for "acme" is a _child_ of the Route for "clients".

    But how does `<Clients>` know where to display it?

    This is what `<Outlet>` tells it. You can place one of these exactly in the HTML where you want the child component displayed.

3. Check that:

    - you can now click the "ACME Inc" link and navigate to the `<Client>` component;
    - that the URL changes accordingly;
    - that the primary navigation still takes you to Home and Invoices.


