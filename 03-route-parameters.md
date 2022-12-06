# Using Route Parameters

## Updating the Routes to Specify Route Parameters

1. Now, back in `<App>`, modify the `<Routes>` as follows.

    Currently it looks something like this:

    ```javascript
    <Routes>
      <Route index element={<Home />} />
      <Route path="home" element={<Home />} />
      <Route path="clients" element={<Clients />}>
        <Route path="acme" element={<Client />} />
        <Route path="baker" element={<Client />} />
        <Route path="chortleware" element={<Client />} />
      </Route>
      <Route path="invoices" element={<Invoices />} />
      <Route path="*" element={<Home />} />
    </Routes>
    ```

    Modify it so that the `/clients` route looks like this:

    ```javascript
    <Route path="clients" element={<Clients />}>
      <Route path=":clientName" element={<Client />} />
    </Route>
    ```

2. Check that it still navigates to the `<Client>` component.

3. Notice what we have done: `:clientName` is a parameter representing the real client URL path.


## Accessing Route Parameters

We can access this path parameter from our `<Client>` component.

1. Modify `<Client>` to add the line:

    ```javascript
    const { clientName } = useParams();
    ```

2. Display the `clientName` in the rendering of this component.


