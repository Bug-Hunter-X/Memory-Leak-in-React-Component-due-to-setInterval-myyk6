# React setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within a `useEffect` hook without a cleanup function. This can lead to memory leaks, as the interval continues to run even after the component unmounts.

## Bug Description

The `MyComponent` component uses `setInterval` to increment a counter every second. However, it lacks a cleanup function within the `useEffect` hook to clear the interval when the component is unmounted. This results in the interval continuing to run indefinitely, even after the component is no longer rendered, eventually causing a memory leak.

## Solution

The solution involves using the return value of `useEffect` to provide a cleanup function.  This function clears the `setInterval` before the component is unmounted, preventing the memory leak.

## How to reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Install dependencies using `npm install`.
4. Run the project using `npm start`.
5. Observe the counter incrementing. Unmount the component and the interval continues running.

## How to fix

1. Refer to the `bugSolution.js` file to understand the correct way to implement `setInterval` within `useEffect`.