# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications where an infinite loop is caused by an incorrectly written `useEffect` hook.  The component updates its state within the `useEffect` hook, leading to continuous re-renders and a never-ending loop.

## Bug Description

The `MyComponent` uses the `useState` hook to manage a count.  The `useEffect` hook attempts to increment the count, but because `count` is included in the dependency array, the effect is triggered every time the count changes, creating an infinite loop.

## Solution

The solution involves restructuring the `useEffect` hook so that it doesn't depend on the state variable it updates.  Typically, this might involve using a condition to trigger the effect only under specific circumstances, using a different state variable, or utilizing `useCallback` for expensive computations.

## How to reproduce

1. Clone this repository
2. `npm install`
3. `npm start`