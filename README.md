# Telecom Carrier, the frontend project.

A cloud telecom carrier needs a web application to control the available phone numbers for purchase.

Prepared with ❤️ by [Evolux Sistemas](https://www.evolux.net.br/) team.

### Briefing

The basic user story is:

> As salespeople supervisor, I can fully manage the numbers for sale in a table.

For an engineering perspective, consider this is just a CRUD. 👍

Backend workmates will provide a RESTful API for it, but they're slowed down.
You still must work and possibly demonstrate your feature working while the API is still being crafted,
and your team decided that the client side will mock such API. As a very skilled frontend engineer,
you're in charge of doing it, while your colleagues are working in other important features.

Here's the mandatory frontend stack that must play a major role in your implementation:

- React;
- Bootstrap;
- Redux.

_Hint_: as a Portuguese speaker, here's also an introductory live coding with this stack: <br/>
https://www.youtube.com/watch?v=lYy3EUEwLeY

### More technical details

The whole team agreed with a few specs and technical limitations:

- all payloads for requests and responses are JSON;
- in the beginning, the API will be very slow and take ~2s for some responses;
- there's an agreement of a data schema;
- there will be around 800 available numbers for management, consider any pagination technique.

About the schema, here's a [DID `number`](https://www.3cx.com/pbx/did/) entity example for now:

```json
{
  "id": 42,
  "value": "+55 84 91234-4321",
  "monthyPrice": "0.03",
  "setupPrice": "3.40",
  "currency": "U$"
}
```

Another hint, as you should have noticed, is that your team is international,
so do your best trying to code in English.
(Or did you think I was just a fancy challenge written in English by Brazilians for no reason?)

### Extra features

Nobody it's expecting it. 💅 But it will be nice to see:

- a state persistence for the mocked management, like Local Storage;
- a safe way to keep the listed numbers updated, like a polling; and/or
- automated tests of any kind.

Just don't overengineer it too much. Keep it simple. And don't try to rob product management role!

### Points of interest

It all depends of the level of seniority you're applying to, of course. But our main observations are:

- general computing knowledge;
- your approach to problems;
- how you're architecting the JSX components, state tree, file modules;
- basic (again, _basic_) UX details like:
  - responsive UI,
  - reactive state machine letting the user know what's happening all the time,
  - preventing users of doing dangerous operations, and
  - acessiblity issues;
- care with resource leaks;
- consistent programming paradigm usage;
- modern and idiomatic JavaScript;
- good patterns of React and Redux;
- thinking twice before introducing a new dependency;
- experience with RESTful APIs consumption; and
- good usage of Bootstrap or any other adjacent CSS tool, like Sass preprocessor or Styled Components.

Feel free to use any boilerplate, but consider we'll be using Node 12, `npm i` and `npm start` for testing (also `npm t` in case you write tests).

And we don't care about Internet Explorer that much.

Be cool and happy coding!
