# Backbone Cache Sync

A server-side adapter that caches Backbone.fetch requests using [Redis](https://github.com/mranney/node_redis). Requires [backbone-super-sync](https://github.com/artsy/backbone-super-sync).

## Example

````javascript
REDIS_URL = "redis://redistogo:t0k3n@crestfish.redistogo.com:1337/";
DEFAULT_CACHE_TIME = 3600;
NODE_ENV = "production";
var Backbone = require('backbone');
Backbone.sync = require('backbone-super-sync');
cacheSync = require('backbone-cache-sync');
cacheSync(Backbone.sync, REDIS_URL, DEFAULT_CACHE_TIME, NODE_ENV);

model = new Backbone.Model({id: 'bar'});
model.urlRoot = '/foo';
model.fetch({cache: true});
````

## Contributing

Please fork the project and submit a pull request with tests. Install node modules `npm install` and run tests with `make test`

## License

MIT
