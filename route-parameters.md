# Using Route Parameters

Earlier, you created a `<ContactListContainer>` which retrieved
and displayed a set of contacts.

However, the new requirement is to render a single `<Contact>`:

    URL Path      | URL Path
    --------------|---------
    /contacts     | render a list of contacts
    /contacts/1   | render contact 1
    /contacts/2   | render contact 2, etc

1. Implement navigation.

2. Implement a component that, given a contact id,
   renders the corresponding contact.

3. Implement routing according to the table above.