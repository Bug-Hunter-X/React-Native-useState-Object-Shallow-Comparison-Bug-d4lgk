# React Native useState Object Shallow Comparison Bug

This repository demonstrates a common but easily overlooked bug in React Native applications.  When using the `useState` hook with an object as the initial state, directly modifying properties of that object within the state update function may not always trigger a re-render. This is due to React's shallow comparison of the state object.

## Problem

The provided `bug.js` file contains a component that uses `useState` with an object.  Changing the object's properties doesn't always update the UI because React only checks if the object reference has changed, not the object's contents.

## Solution

The `bugSolution.js` file demonstrates the corrected approach. To ensure proper re-renders, always create a completely new object when updating the state using the spread syntax or by creating a new object with the updated values. This forces React to detect the change and re-render the component.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run `npx react-native run-android` (or `npx react-native run-ios`).
4. Observe the behavior of the buggy and corrected versions.
