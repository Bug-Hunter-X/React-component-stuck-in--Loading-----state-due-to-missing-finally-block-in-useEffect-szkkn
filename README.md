# React Loading State Bug

This repository demonstrates a common React bug where a component gets stuck in a loading state due to improper error handling in an asynchronous `useEffect` hook.  The issue arises from a missing `finally` block, resulting in the loading state not being updated after an error occurs.

## Bug Description
The component fetches data from an API.  If the fetch fails, the error is caught, but the loading state remains true, leaving the UI indefinitely displaying "Loading...".

## Solution
Adding a `finally` block to the `useEffect`'s `fetchData` function ensures that the `setLoading(false)` statement always executes, regardless of whether the `try` or `catch` block is executed.