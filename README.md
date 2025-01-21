# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling when parsing user input.  Specifically, the provided code lacks error handling when converting the user ID (obtained from the request parameters) to an integer.  This can lead to unexpected behavior, including crashes or incorrect responses if the ID is not a valid number.

## Bug

The `bug.js` file contains the buggy code. The route handler attempts to find a user by ID, parsing the ID as an integer. However, if the ID is not a valid integer (e.g., a string or a non-numeric value), the `parseInt` function will return `NaN`, resulting in an unsuccessful user lookup.

## Solution

The `bugSolution.js` file provides a corrected version.  The solution adds error handling to check if the parsed ID is actually a number.  If not, it sends an appropriate error response.