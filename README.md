# React useEffect Hook Conditional Rendering Bug
This repository demonstrates a common bug in React's `useEffect` hook related to conditional rendering. The bug occurs when the conditional logic inside `useEffect` doesn't correctly handle updates to state variables, leading to unexpected behavior.

## Bug Description
The `MyComponent` function uses `useEffect` to log a message when the `count` state variable is greater than 0. However, the condition `count > 0` is only evaluated once during the initial render or when the count updates. If the count updates from a value less than or equal to 0 to a value greater than 0, the console log will not trigger during that specific update. This is because the useEffect hook checks the condition only when its dependencies change, and doesn't re-evaluate the condition at every state update.

## Solution
The solution involves ensuring the useEffect function correctly reacts to the state change when count becomes greater than 0. This can be achieved by making the logic inside the useEffect function dependent on count by directly using the count variable in a condition that is triggered in every update of the state variable.