# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook, which can lead to infinite re-renders.  The bug is caused by omitting dependencies in the `useEffect` hook, resulting in the effect running after every render. 

## Bug Description
The `MyComponent` renders infinitely because the `useEffect` hook lacks dependencies. Every time the component re-renders (which happens due to the state update), the `useEffect` also runs, triggering another re-render, resulting in an infinite loop.  This causes a significant performance issue and eventually crashes the browser.

## Solution
The solution involves correctly specifying the dependencies array in the `useEffect` hook. By including `count` in the dependencies array, the effect only runs when `count` changes, solving the infinite loop problem.