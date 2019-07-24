# Using Nested Routes

1. In `<Clients>`, add nested links like this, one each for the three clients below:

        <Link to={`${props.match.url}/acme`}>ACME Inc</Link>

    - ACME Inc
    - Baker and Sons
    - Chortleware


2. Add nested routes for these clients. Here's an example for some other components:

        const Two = props => (
        <div>
            <h2>Component Two</h2>
            <Route path="/two/account1" component={() => <h3>Account 1</h3>} />
            <Route path="/two/account2" component={() => <h3>Account 2</h3>} />
        </div>
        );

3. Add `<Link>`s to the URLs `/clients/acme` and `/clients/baker-and-sons` from _within_ component `<Clients>`, so that the links only render when displaying component `<Clients>`. Check that they work as expected.

## Using `match`

1. Now you understand the `match` prop, how could you use this so that the nested routes (`/clients/acme` and `/clients/baker-and-sons`) can remain unaware of the part of the path that has been matched so far (`/baker-and-sons`)?
