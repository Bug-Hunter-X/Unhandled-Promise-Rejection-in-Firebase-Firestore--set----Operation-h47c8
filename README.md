# Unhandled Promise Rejection in Firebase Firestore `set()` Operation

This repository demonstrates a common yet easily overlooked error in Firebase Firestore: neglecting to handle promise rejections in asynchronous operations.  Specifically, this example focuses on the `set()` method, showing how a missing `.catch()` block can lead to silent failures and data inconsistencies.

The `bug.js` file contains the erroneous code, while `bugSolution.js` presents the corrected version with proper error handling.

## How to Reproduce

1.  Ensure you have a Firebase project set up and properly configured.
2.  Clone this repository.
3.  Run `bug.js`. Observe that any errors during the `set()` operation (e.g., network issues, permission errors) will go unnoticed.
4.  Run `bugSolution.js`. Note that errors are now caught and handled gracefully.

## Solution

Always include a `.catch()` block after asynchronous Firebase operations to properly handle potential errors.  This ensures that your application can gracefully handle failures, providing users with informative messages and preventing data loss or corruption.