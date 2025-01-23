# Uncaught Exception in Node.js HTTP Server

This repository demonstrates a common error in Node.js: unhandled exceptions within an HTTP server.  The `bug.js` file contains code that throws an exception without proper handling, causing the server to crash. The `bugSolution.js` provides a corrected version with robust error handling.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node bug.js`.
4. Access `http://localhost:3000/error` in your browser. The server will crash.
5. Run `node bugSolution.js` and try again. The server will gracefully handle the error.

## Bug Analysis

The primary issue lies in the lack of comprehensive error handling within the server's request handler.  The `throw new Error` statement lacks a `try...catch` block to manage potential exceptions.  This leads to the uncaught exception and the server's termination.

## Solution

The `bugSolution.js` demonstrates a solution implementing a `try...catch` block to gracefully handle the thrown exception.  The error is now logged to the console, and the server remains operational.