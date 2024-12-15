# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook:  forgetting to include dependencies in the dependency array, leading to an infinite loop.  The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem

The `useEffect` hook in `bug.js` is designed to log a message whenever the component renders. However, because `count` (which changes when the button is clicked) is missing from the dependency array, the effect runs on every render, creating a cycle of re-renders and triggering the console log endlessly. This issue isn't always apparent, as it depends on the complexity of the component and may not manifest until a certain point.  This is a subtle error that can be very difficult to find in larger projects.

## Solution

The `bugSolution.js` file corrects this by adding `count` to the dependency array.  Now, the effect only runs when the `count` state variable changes, preventing the infinite loop.