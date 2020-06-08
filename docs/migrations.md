[&larr; API Documentation](/node-jsonwebtoken/)

# Migrations

## v7 to v8
Here you can find some notes to help you understand how to migrate to v8 from v7:

* [JOI validation library has been removed](https://github.com/auth0/node-jsonwebtoken/pull/348). The errors raised for input validation on `sign` function have changed, previously we raised `ValidationError`, now it is a plain `Error`. Error messages have also changed.
  * Keep in mind the new validation on objects (`options`, `options.headers` and optionally `payload`) have changed a bit by using [lodash](https://lodash.com/docs/4.17.4#isPlainObject). Now it is checked that those are objects, that's it, with [JOI some other validations/allowances were applied](https://github.com/hapijs/joi/blob/v6.10.1/API.md#object).

* [Package size has been reduced](https://github.com/auth0/node-jsonwebtoken/pull/347). This can only affect you if you depended on some of the deleted files (non functional files).

* [`process.nextTick()` execution before calling the verification callback has been removed](https://github.com/auth0/node-jsonwebtoken/pull/302). If you pass a callback function it will get called right away, if you expected the next tick behavior, you may want to call nextTick in your code.

* [`maxAge` verification option expects seconds or a string describing a time span (i.e: `'2 days'`)](https://github.com/auth0/node-jsonwebtoken/pull/349). It accepted milliseconds in v7, which did not make sense since JWTs times are expressed in seconds.

* Unintentionally removed support for Streams on payload for signing.%

See also:

* [Install](/node-jsonwebtoken/install)
* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)

* [Supported algorithms](/node-jsonwebtoken/algorithms)
* [Errors & codes](/node-jsonwebtoken/errors)
* [Refreshing JWTs](/node-jsonwebtoken/refreshing-jwts)
* [Migrations](/node-jsonwebtoken/migrations)