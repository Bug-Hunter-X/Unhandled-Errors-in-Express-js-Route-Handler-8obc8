# Express.js Unhandled Error Example

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input and missing resources.

The `bug.js` file shows a vulnerable route. The `bugSolution.js` file provides a corrected version.

## Bug

The original code lacks error handling for:

1. **Invalid User IDs:**  If the `:id` parameter is not a valid number, `parseInt(userId)` will return `NaN`, leading to a potential error in the `find()` method.
2. **Non-Existent Users:** If no user matches the provided ID, the code silently sends a 'User not found' message.  More robust error handling might return a specific HTTP status code (e.g., 404) and a structured error response.

## Solution

The corrected code in `bugSolution.js` includes error handling for both scenarios, making the route more robust and less prone to crashes or unexpected behavior.