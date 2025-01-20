# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue encountered when using `setTimeout` within a loop.  The problem arises because the `setTimeout` callback function doesn't capture the value of `i` at the time of its creation, but rather references the variable `i` itself. Thus, by the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` holds its final value (10).

## Bug
The `bug.js` file contains the problematic code. When run, it prints '10' ten times instead of 0 through 9.

## Solution
The `bugSolution.js` file provides a corrected version.  It uses an immediately invoked function expression (IIFE) to create a new scope for each iteration, effectively capturing the current value of `i` for each callback.