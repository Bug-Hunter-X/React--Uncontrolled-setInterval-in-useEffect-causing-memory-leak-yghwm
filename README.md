# React setInterval Memory Leak

This repository demonstrates a common React bug involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.  The `bug.js` file shows the incorrect implementation, leading to a memory leak. The `bugSolution.js` provides the corrected version.

## Bug Description
The original code uses `setInterval` to update the component's state every second.  However, it lacks a cleanup function inside the `useEffect` hook's return statement. This means that when the component unmounts, the interval continues to run, leading to a memory leak. 

## Solution
The solution includes a cleanup function that uses `clearInterval` to stop the interval when the component is unmounted, effectively resolving the memory leak.