# Unexpected State Updates in React

This repository demonstrates a subtle bug in React applications related to consecutive calls to the `useState` hook within a single function execution.  The bug leads to unexpected and inconsistent state updates, potentially leading to difficult-to-debug issues.

## The Problem

The core issue lies in calling `setCount` twice in rapid succession. React's state updates are asynchronous; the second call might override the first before it completes, leading to missed updates or unexpected values.

## Solution

The solution is to refactor the code to avoid making consecutive calls to `setState` within a single synchronous execution.  This can often be accomplished by using a single state update that handles the desired change in a single operation. 