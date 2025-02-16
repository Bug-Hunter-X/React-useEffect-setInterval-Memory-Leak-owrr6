# React useEffect setInterval Memory Leak
This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example shows how forgetting to include a cleanup function within `useEffect` can lead to memory leaks when using `setInterval`. The solution demonstrates the correct way to implement `setInterval` within a cleanup function for proper resource management. 

## Problem
The `setInterval` function, when used within `useEffect` without proper cleanup, continues to run even after the component unmounts. This leads to the interval's callback function repeatedly updating state, even after the component is no longer needed. This results in memory leaks and potential performance issues. 

## Solution
The solution demonstrates the correct way to use `setInterval` within `useEffect`. The `useEffect` hook returns a cleanup function which uses `clearInterval` to stop the interval when the component unmounts. This prevents memory leaks and ensures proper resource management.