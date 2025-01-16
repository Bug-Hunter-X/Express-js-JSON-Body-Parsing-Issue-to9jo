# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue in Express.js applications where the server fails to correctly parse the JSON request body. This typically occurs when the `Content-Type` header in the request is missing or set incorrectly. 

The `bug.js` file contains the problematic code.  The `bugSolution.js` file shows the corrected code.

## Bug
The server does not correctly parse the JSON request body because it relies on the `express.json()` middleware, which only parses the request body if the `Content-Type` header is set to `application/json`. If this header is missing or incorrect, the `req.body` will be empty.

## Solution
The `Content-Type` header is added to the request. Alternatively, an error handler could be added to catch the error when the `Content-Type` header is not set correctly, so that a meaningful error message can be returned to the client.