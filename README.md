# React useEffect Cleanup Function Not Called on Unmount

This repository demonstrates a common issue in React where the cleanup function within `useEffect` is not called when the component unmounts.  The problem arises when the component is unmounted quickly, such as when navigating away from a route, before the asynchronous operation within `useEffect` completes.

## Problem

The provided code uses `useEffect` to log the count and perform a cleanup action. However, under certain circumstances (e.g., rapid route changes), the component might unmount before the cleanup function runs.

## Solution

A solution is provided in `bugSolution.js` that addresses this issue.  The provided solution demonstrates how to handle potential race conditions by implementing an additional check in the cleanup function or by using the `isMounted` pattern.