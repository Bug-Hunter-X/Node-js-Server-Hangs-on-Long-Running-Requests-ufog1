# Node.js Server Hang on Long-Running Requests

This repository demonstrates a common issue in Node.js applications: how long-running requests can cause the server to become unresponsive.  The `bug.js` file shows a server that hangs when a request takes longer than a few seconds.  The `bugSolution.js` file provides a solution using asynchronous operations to prevent this behavior.

## Problem

Node.js is single-threaded.  If a single request keeps the event loop busy for a long time (like a complex computation or a slow database query), the server won't be able to handle any other incoming requests.

## Solution

The solution lies in using asynchronous programming techniques (like Promises or async/await) to avoid blocking the event loop.  This allows other requests to be processed concurrently even while a long-running task is in progress. 