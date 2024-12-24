# React setInterval Memory Leak

This repository demonstrates a common error in React: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to a memory leak as the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter.  However, it fails to include a cleanup function within the `useEffect`'s return statement to clear the interval when the component unmounts.  This results in the interval continuing to run indefinitely, consuming resources and potentially leading to a memory leak.

## Solution
The `bugSolution.js` file provides the corrected version. The `useEffect` hook now includes a return function that calls `clearInterval` to stop the interval when the component is unmounted. This prevents the memory leak.