[&larr; jsonwebtoken Documentation](/node-jsonwebtoken/)

## Refreshing JWTs

First of all, we recommend you to think carefully if auto-refreshing a JWT will not introduce any vulnerability in your system.

We are not comfortable including this as part of the library, however, you can take a look at [this example](https://gist.github.com/ziluvatar/a3feb505c4c0ec37059054537b38fc48) to show how this could be accomplished.
Apart from that example there are [an issue](https://github.com/auth0/node-jsonwebtoken/issues/122) and [a pull request](https://github.com/auth0/node-jsonwebtoken/pull/172) to get more knowledge about this topic.

See also:

* [Install](/node-jsonwebtoken/install)
* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)

* [Supported algorithms](/node-jsonwebtoken/algorithms)
* [Errors & codes](/node-jsonwebtoken/errors)
* [Refreshing JWTs](/node-jsonwebtoken/refreshing-jwts)
* [Migrations](/node-jsonwebtoken/migrations)