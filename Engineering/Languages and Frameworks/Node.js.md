# Streams
- Always attach an error handler ([source](https://dev.to/logrocket/17-common-nodejs-errors-and-how-to-solve-them-8g1#unhandled-exceptions-streams)). Otherwise, it will crash the application. One method:
```js
readStream.on('error', (err) => {
  console.error('An error occurred:', err.message);
});
```
- 