# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the provided code attempts to parse a user ID as an integer without any checks to ensure the ID is actually numeric.

## Bug Description
The `/users/:id` route attempts to fetch a user based on the ID provided in the URL.  However, it fails to handle cases where the `id` parameter is not a valid integer. This can lead to `NaN` comparisons and potential crashes, or it might silently return an incorrect response.

## Bug Reproduction
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `node bug.js`.
4. Access the route with an invalid ID, such as `/users/abc` or `/users/123.45`.

## Solution
The solution involves adding input validation to the route handler, explicitly checking that the ID is a number before attempting to parse it and use it in a database lookup.  The updated code includes comprehensive error handling to gracefully manage invalid input.