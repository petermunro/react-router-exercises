# Using Nested Routes

1. Add a second component:

        const Two = props => (
        <div>
            <h2>Component Two</h2>
        </div>
        );

2. Ensure this component is rendered when the URL `http://localhost:3000/two` is entered.

## Add Nested Routes

1. Add nested routes as follows:

        const Two = props => (
        <div>
            <h2>Component Two</h2>
            <Route path="/two/account1" component={() => <h3>Account 1</h3>} />
            <Route path="/two/account2" component={() => <h3>Account 2</h3>} />
        </div>
        );

2. Why are these called "nested" routes?

3. Add `<Link>`s to the URLs `/two/account1` and `/two/account2` from _within_ component `<Two>`, so that the links only render when displaying component `<Two>`. Check that they work as expected.

## Using `match`

1. Now you understand the `match` prop, how could you use this so that the nested routes (`/two/account1` and `/two/account2`) can remain unaware of the part of the path that has been matched so far (`/two`)?
