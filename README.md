# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive.  The `server.js` file contains the problematic code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original `server.js` contains a `while` loop that simulates a long-running task. This loop runs synchronously within the request handler, preventing the event loop from processing other requests.  As a result, the server appears to hang and will not respond to new requests until the loop completes.

## Solution

The solution in `serverSolution.js` utilizes asynchronous operations to avoid blocking the event loop.  This allows the server to handle multiple requests concurrently, preventing unresponsiveness.