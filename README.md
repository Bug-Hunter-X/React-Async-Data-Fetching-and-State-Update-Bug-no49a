# React Async Data Fetching Bug

This repository demonstrates a common bug in React components that involve asynchronous data fetching and state updates. The bug occurs when a component unmounts before an asynchronous operation completes, leading to warnings and potential crashes.  This example also shows how to correctly handle potential API errors.  The solution showcases proper error handling and lifecycle method usage to prevent these issues.

## Bug Description
The `BuggyComponent.js` file contains a React component that fetches data from an API using `useEffect`. The problem is that if the component unmounts before the API call resolves, React will throw an error because it is attempting to update the state of an unmounted component. The component also lacks error handling.

## Solution
The `FixedComponent.js` demonstrates a corrected version.  It utilizes the `useRef` hook and a cleanup function in `useEffect` to safely handle the asynchronous call and ensure that the component doesn't update state after unmounting. It also includes improved error handling to display a message to the user if the API call fails.