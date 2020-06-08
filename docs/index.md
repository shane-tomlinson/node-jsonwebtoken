![JWT Logo](https://jwt.io/img/pic_logo.svg)

# jsonwebtoken API Documentation

* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)
* [Errors & codes](/node-jsonwebtoken/errors)

## Algorithms supported

Array of supported algorithms. The following algorithms are currently supported.

alg Parameter Value | Digital Signature or MAC Algorithm
----------------|----------------------------
HS256 | HMAC using SHA-256 hash algorithm
HS384 | HMAC using SHA-384 hash algorithm
HS512 | HMAC using SHA-512 hash algorithm
RS256 | RSASSA-PKCS1-v1_5 using SHA-256 hash algorithm
RS384 | RSASSA-PKCS1-v1_5 using SHA-384 hash algorithm
RS512 | RSASSA-PKCS1-v1_5 using SHA-512 hash algorithm
PS256 | RSASSA-PSS using SHA-256 hash algorithm (only node ^6.12.0 OR >=8.0.0)
PS384 | RSASSA-PSS using SHA-384 hash algorithm (only node ^6.12.0 OR >=8.0.0)
PS512 | RSASSA-PSS using SHA-512 hash algorithm (only node ^6.12.0 OR >=8.0.0)
ES256 | ECDSA using P-256 curve and SHA-256 hash algorithm
ES384 | ECDSA using P-384 curve and SHA-384 hash algorithm
ES512 | ECDSA using P-521 curve and SHA-512 hash algorithm
none | No digital signature or MAC value included

## Refreshing JWTs

First of all, we recommend you to think carefully if auto-refreshing a JWT will not introduce any vulnerability in your system.

We are not comfortable including this as part of the library, however, you can take a look at [this example](https://gist.github.com/ziluvatar/a3feb505c4c0ec37059054537b38fc48) to show how this could be accomplished.
Apart from that example there are [an issue](https://github.com/auth0/node-jsonwebtoken/issues/122) and [a pull request](https://github.com/auth0/node-jsonwebtoken/pull/172) to get more knowledge about this topic.
