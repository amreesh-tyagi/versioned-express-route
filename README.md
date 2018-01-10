# Versioned Express Routes

This middleware allows express routes to be mounted by version and provides a method
to route between version paths and accept headers. The latter is based on the assumption
that a version property will exist on the request object. 

This middleware will mount paths from a directory that match the supported versions
you specify. Each mounted directory's `index.js` should return either a router or valid
middleware. For example, if the middleware is used with the base path `routes` and
supported versions `v1`, `v2`, then the routers from `routes/v1/index.js` and
`routes/v2/index.js` would be mounted.

## Usage

```javascript
var versionRoutes = require('express-versioned-routes');

app.use('/', versionRoutes(
  path.join(__dirname, 'routes'),
  ['v1', 'v1.1', 'v2']
));
```
Ref: A fork(with a fix) of https://github.com/elliotttf/express-versioned-routes
