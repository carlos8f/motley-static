# motley-static
Static file serving middleware with in-memory cache for Motley

```js
module.exports = function container (get, set) {
  var Buffet = new get('vendor.buffet').Buffet
  var buffet = new Buffet(get('conf.middleware.static.paths'), get('conf.middleware.static'))
  set('@middleware.static.buffet', buffet)
  return buffet.middleware(get('conf.middleware.static'))
}
```
