
# Interview Preparation

## Mission One: Initial Predictions

These are my predictions before implementing the Employee Explorer.

### 1. Where will each of the three requests run?

- **Employee Profile:** I expect this request to run in a Server Component because the employee information is needed when the page loads.
- **Recent Posts Preview:** I expect this request to run in an asynchronous Server Component inside its own Suspense boundary.
- **Explore All Posts:** I expect this request to run in a Client Component after the user clicks the button.

### 2. What should remain visible while the server posts preview loads?

I expect the employee profile to remain visible while the recent posts preview is loading. Only the posts section should display its Suspense fallback until the posts are ready.

### 3. Will wrapping a click-handler fetch in Suspense automatically display its fallback?

I expect that it will not. A fetch request started inside a click handler does not automatically activate Suspense. I think the loading state will need to be managed separately in the Client Component.

### 4. If an HTTP response has status 503, will fetch automatically throw?

I expect that fetch will not automatically throw for an HTTP 503 response. It will return a Response object, so I will need to check the response status or `response.ok` and handle the error myself.
