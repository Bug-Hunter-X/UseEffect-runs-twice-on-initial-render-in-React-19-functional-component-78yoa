# React 19 useEffect Double Execution Bug

This repository demonstrates a subtle bug in React 19 where the `useEffect` hook runs twice during the initial render of a functional component using the `useState` hook.  The bug is specific to certain scenarios and might not be immediately apparent.

## Bug Description

The `useEffect` hook, when used with a dependency array, is expected to run only when a dependency changes. However, in this example, the effect runs twice on mount, even though the dependency (`count`) hasn't changed yet.

## Reproduction

1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs; you'll see 'Component rendered:' logged twice before any interaction.

## Solution

The solution involves understanding how React's state updates and renders happen internally. The provided solution uses a ref to ensure that the effect only executes once after the initial render.  This is a common workaround to prevent this double execution.