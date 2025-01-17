# Unresponsive Node.js Server: Blocking Event Loop

This repository demonstrates a common issue in Node.js applications: blocking the event loop with a long-running synchronous operation.  This leads to an unresponsive server, unable to handle new requests.

## The Problem

The `server.js` file contains a simple HTTP server. However, the request handler includes a `while` loop that keeps the CPU busy for 5 seconds. This synchronous operation blocks the event loop, preventing Node.js from processing other requests during this time.  The server effectively becomes unresponsive for the duration of the loop.

## The Solution

The `server-solution.js` demonstrates how to solve this by using asynchronous operations (or offloading long-running tasks) to prevent blocking the event loop.  This allows the server to remain responsive even during time-consuming tasks.