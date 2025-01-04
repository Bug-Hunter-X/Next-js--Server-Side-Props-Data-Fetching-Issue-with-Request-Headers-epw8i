# Next.js Server-Side Props Data Fetching Issue

This repository demonstrates a common but often overlooked issue in Next.js applications related to data fetching using `getServerSideProps` or `getStaticProps` when relying on request headers (e.g., cookies for authentication).  The problem arises when the necessary headers are not properly passed to the data fetching functions, leading to unexpected behavior.

The `bug.js` file shows the incorrect implementation which fails to pass the authentication cookies; `bugSolution.js` provides the correct implementation.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the incorrect behavior in `bug.js` and the correct behavior in `bugSolution.js`. 

## Solution

The solution involves ensuring that the request headers (including cookies) are correctly propagated to the data fetching function.  This typically involves utilizing the `context` object provided to `getServerSideProps` or `getStaticProps`.