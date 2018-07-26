# Evolux Frontend Developer test

A cloud telecom carrier needs a webapp to display all of its available phone numbers for purchase. The backend developers from the company will provide an API endpoint that delivers a paginated list of availabe numbers. As usual in the development world, said API is still bein crafted and you, the frontend developer, will mock this API endpoint to avoid getting blocked. After the mocks are done, the interface can fetch from it and display the numbers available for purchase.

The frontend stack the company uses is:

- Webpack (with Webpack Dev Server for local development and API mocking)
- React
- Redux

## The first task, mocking the API endpoint

- Create a /numbers endpoint in the webpack-dev-server that return available phone numbers. ([click here](https://webpack.js.org/configuration/dev-server/#devserver-before) to learn how to mock endpoints in webpack-dev-server)
- The carrier currently has 1000 (one thousand) available phone numbers. They are all the numbers in the range of '555 000 000' to '555 000 999'.
- Each number has a cost value. the cost value varies from $1.00 to $1.99;
- The formula for how much a number will cost is adding its last two digits to the starting price of $1.00. IE.: the number '555 000 342' costs $1.42.


The mocked data needs to be generated dynamically depending on the query paramaters values sent. As explained below:
  - The endpoint accepts two query parameters: 'page' and 'perPage';
  - if a request is made with page: 1 and perPage: 10, the response will contain 10 numbers, from '555 000 000' to '555 000 009'.
  - if a request is made with page: 10 and perPage: 100, the response will contain 100 numbers, from '555 000 899' to '555 000 999'.

## The API Spec
### [GET] /numbers
Returns a list of all phone numbers available for purchase.
#### Query Parameters
##### page [integer]
The current page to be returned. defaults to 1.
##### perPage [integer]
How many numbers will be returned at once. defaults to 100.

#### Request Example
```
/numbers?page=1&perPage=3
```

#### Response Example
```json
{
  "meta": {
    "page": 1,
    "perPage": 3,
    "totalPages": 334
  },
  "data": [
    {
      "number": 555 000 000,
      "cost": 1
    },
    {
      "number": 555 000 001,
      "cost": 1.01
    },
    {
      "number": 555 000 002,
      "cost": 1.02
    }
  ]
}
```

## The second task, displaying the numbers in the UI

- Use React to display the list (both the phone number and their cost).
- The default amount of numbers per page will be 100. You decide if the user gets to change this value or not.
- The data is paginated. the user needs to be able to navigate between pages (going to the next and to the previous is enough).
- Use Redux to manage the application state.
- The UI should not allow the user to perform actions that wouldn't work. I.E.: The 'previous page' button should be disabled if the page being displayed is the first one.
- The UI should not allow the user to perform actions that would cancel an ongoing API request.
- You can use any CSS method/framework you want.

## What will be evaluted in the test

- Your ability to write modern and idiomatic Javascript
- Your ability to mock API endpoints
- Your ability to solve problems with logic (by implementing the dynamic data mock)
- Your ability to sync the UI state with the application state
- Your ability to create UIs with a minimum aesthetic appeal.
