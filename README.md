# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler can cause the server to become unresponsive.  The `bug.js` file shows the problematic code, while `bugSolution.js` presents a solution using asynchronous operations.

## Bug

The `bug.js` file contains a simple HTTP server. The request handler includes a `while` loop that keeps the CPU busy for 5 seconds. This blocks the Node.js event loop, preventing the server from responding to other requests during that time.

## Solution

The `bugSolution.js` demonstrates how to resolve the issue by using asynchronous operations (e.g., `setTimeout` or promises) to avoid blocking the event loop.  By offloading the long-running task to a separate thread or using asynchronous programming techniques, the server remains responsive.