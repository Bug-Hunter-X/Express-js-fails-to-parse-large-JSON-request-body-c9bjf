# Express.js Large JSON Payload Parsing Issue

This repository demonstrates a bug in an Express.js application where parsing large JSON request bodies fails.  The server receives the request but `req.body` remains empty.

## Bug Description

The Express.js application, when receiving POST requests with large JSON payloads, does not correctly parse the body.  `req.body` is empty, leading to unexpected behavior and potential errors.

## Solution

The issue is resolved by increasing the `json()` body limit using the `limit` option:
```javascript
app.use(express.json({ limit: '50mb' })); // Adjust limit as needed
```
This allows the server to handle larger JSON payloads without issues.