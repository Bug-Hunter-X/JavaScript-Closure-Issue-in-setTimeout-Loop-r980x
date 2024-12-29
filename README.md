# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related issue in JavaScript when using `setTimeout` within a loop.  The expected behavior is to log the numbers 0 through 9 with a one-second delay between each. However, due to how closures work in JavaScript, the loop completes before the `setTimeout` callbacks execute, resulting in all callbacks logging the final value of `i` (which is 10). 

The `bug.js` file contains the problematic code, while `bugSolution.js` provides a corrected version.

## How to reproduce

1. Clone this repository.
2. Open `bug.js` in your preferred JavaScript environment.
3. Run the code. Observe the unexpected output.
4. Open `bugSolution.js` and run that code. Observe the correct output.

## Solution

The solution involves creating a new variable within the loop that captures the value of 'i' at each iteration using an immediately invoked function expression (IIFE).  This creates a new scope for each iteration, ensuring that the correct value is used in each callback.