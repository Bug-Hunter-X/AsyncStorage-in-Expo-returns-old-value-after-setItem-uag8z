# AsyncStorage Inconsistency in Expo

This repository demonstrates a common issue encountered when using AsyncStorage in Expo: inconsistent data retrieval after setting a value.

The problem is that `AsyncStorage.setItem` isn't synchronous; it doesn't guarantee immediate data persistence. Calling `AsyncStorage.getItem` directly after `setItem` may retrieve the old value, leading to unexpected behavior and data inconsistencies in your app.

The `bug.js` file showcases this issue. The `bugSolution.js` file demonstrates a solution using promises or async/await to ensure the data is updated before being retrieved.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `expo start` to start the Expo development server.
4. Observe the inconsistent behavior in the app.

## Solution

The solution involves using `AsyncStorage.setItem`'s promise-based return value (or async/await) to guarantee data is written before being read.

## Contributing

Feel free to contribute to this project by reporting issues or suggesting improvements.