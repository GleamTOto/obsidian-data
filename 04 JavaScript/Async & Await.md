---
aliases:
  - async/await
  - Async Functions
tags: frontend, concept, javascript, asynchronous, zettel
created: 2025-03-04T22:40
updated: 2025-03-04T22:44
---
**Created:** 2025-03-05 03:33
**Author:** GleamTOto
**Topics:** #javascript #async #promises

## Notes
Async/await is a modern JavaScript syntax that makes working with asynchronous code more intuitive by allowing you to write asynchronous code that looks and behaves more like synchronous code. It was introduced in ES2017 (ES8) and is built on top of Promises.

### Key Concepts

1. **Async Functions**
   - Functions declared with the `async` keyword
   - Always return a Promise
   - Allow the use of `await` within their body

2. **Await Operator**
   - Can only be used inside async functions
   - Pauses execution until the Promise resolves
   - Extracts the resolved value from the Promise

## Examples

### Basic Syntax
```javascript
// Async function declaration
async function fetchData() {
  // Await pauses execution until the promise resolves
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  return data;
}

// Using the async function
fetchData()
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

## Error Handling

```js
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Error fetching data:', error);
    throw error; // Re-throw to allow handling by caller
  }
}
```

## Parallel vs Sequential Execution

```js
// Sequential execution (slower)
async function sequential() {
  const result1 = await fetchData1();
  const result2 = await fetchData2();
  return [result1, result2];
}

// Parallel execution (faster)
async function parallel() {
  const promise1 = fetchData1();
  const promise2 = fetchData2();
  const [result1, result2] = await Promise.all([promise1, promise2]);
  return [result1, result2];
}
```

## Benefits over Plain Promises

1. More readable, resembles synchronous code
2. Better error handling with try/catch
3. Easier debugging (stack traces show where execution paused)
4. Simplified control flow

## References

- Source: [MDN - Async/Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- Source: [JavaScript.info - Async/Await](https://javascript.info/async-await)
- Literature: "You Don't Know JS: Async & Performance" by Kyle Simpson

## Connected Thoughts

- [[Promises]] - Async/await is built on top of Promises
- [[JavaScript Event Loop]] - Fundamental to understanding how async code works
- [[Callbacks]] - The predecessor to Promises and async/await
- [[Error Handling]] - Try/catch patterns with async/await
- For practical examples, check the [[Fetch API]] note

## Questions

- How does async/await affect the event loop compared to Promises?
- What are the performance implications of awaiting multiple Promises sequentially vs in parallel?
- How can we handle timeouts with async/await?

## Tasks

- [ ]  Create a real-world example comparing callback hell, promises, and async/await
- [ ]  Practice implementing error retry logic with async/await
- [ ]  Benchmark performance differences between different async patterns

---

## Metadata

- Status: #status/development
- Confidence: #confidence/high
- Importance: #importance/high
- Topics: #javascript #async #promises #es8
