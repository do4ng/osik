# osik

osik is a nodejs backend framework centered on performance and weight.

Inspired by koa, only middleware is supported by default, but the handler of this framework is inspired by express, not koa. The concept of middleware is similar to express.

---

```ts
const { osik } = require('osik');

const app = osik();

app.use((req, res, next) => {
  res.body = 'Hello World!';
});

app.listen(3000);
```

## Features

- ⚡ Fast
- 📦 Light
- 🚀 Async/Await
- ⚒️ Middleware

## Installation

Install using [npm](https://npmjs.com/package/osik):

```
npm install osik
```

## async/await

osik supports async/await by default.

```ts
app.use(async (req, res, next) => {
  await next();
  console.log('2');
});

app.use(async (req, res) => {
  await new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, 1000);
  });

  console.log('1');

  res.body = 'Hello World!';
});
```

result:

```
$ node index.js
1
2
```

## License

MIT
