# micro-router

Route matcher for HTTP requests.

## Install

```sh
npm i micro-router
```

## Usage

Every route function is called with `(request, response, params, queryParams)`.

- `request/response`: values come from the http server.
- `params`: Object. Keys are items in the path, like `{id}`.
- `queryParams`: `URLSearchParams` object from the request URL

Node.JS example:

```ts
import router from 'micro-router'
import { createServer } from 'http';

const routes = {
  'GET /user/{id}': onUserGet,
  'DELETE /user/:id': onUserRemove,
  'POST /auth': onAuthenticate,
};

const fn = router(routes);

createServer(fn).listen(1234);
```
