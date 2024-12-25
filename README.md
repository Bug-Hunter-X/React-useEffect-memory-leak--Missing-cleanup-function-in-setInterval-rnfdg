# React useEffect Memory Leak Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook and the `setInterval` function.  The bug causes a memory leak because the interval isn't cleared when the component unmounts.

## Bug Description

The `MyComponent` uses `useEffect` to start an interval that updates a counter every second. However, it's missing the crucial cleanup function that's returned from the `useEffect` to clear the interval. This results in the interval continuing to run even after the component is unmounted, leading to a memory leak.

## Bug Solution

The solution involves adding a cleanup function to the `useEffect` hook.  This function is responsible for clearing the interval before the component unmounts.