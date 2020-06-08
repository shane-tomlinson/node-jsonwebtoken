[&larr; jsonwebtoken Documentation](/node-jsonwebtoken/)

# jwt.sign(payload, secretOrPrivateKey, [options, callback])

(Asynchronous) If a callback is supplied, the callback is called with the `err` or the JWT.

(Synchronous) Returns the JsonWebToken as string

`payload` could be an object literal, buffer or string representing valid JSON. 
> **Please _note_ that** `exp` or any other claim is only set if the payload is an object literal. Buffer or string payloads are not checked for JSON validity.

> If `payload` is not a buffer or a string, it will be coerced into a string using `JSON.stringify`.

`secretOrPrivateKey` is a string, buffer, or object containing either the secret for HMAC algorithms or the PEM
encoded private key for RSA and ECDSA. In case of a private key with passphrase an object `{ key, passphrase }` can be used (based on [crypto documentation](https://nodejs.org/api/crypto.html#crypto_sign_sign_private_key_output_format)), in this case be sure you pass the `algorithm` option.

`options`:

* `algorithm` (default: `HS256`)
* `expiresIn`: expressed in seconds or a string describing a time span [zeit/ms](https://github.com/zeit/ms). 
  > Eg: `60`, `"2 days"`, `"10h"`, `"7d"`. A numeric value is interpreted as a seconds count. If you use a string be sure you provide the time units (days, hours, etc), otherwise milliseconds unit is used by default (`"120"` is equal to `"120ms"`).
* `notBefore`: expressed in seconds or a string describing a time span [zeit/ms](https://github.com/zeit/ms). 
  > Eg: `60`, `"2 days"`, `"10h"`, `"7d"`. A numeric value is interpreted as a seconds count. If you use a string be sure you provide the time units (days, hours, etc), otherwise milliseconds unit is used by default (`"120"` is equal to `"120ms"`).
* `audience`
* `issuer`
* `jwtid`
* `subject`
* `noTimestamp`
* `header`
* `keyid`
* `mutatePayload`: if true, the sign function will modify the payload object directly. This is useful if you need a raw reference to the payload after claims have been applied to it but before it has been encoded into a token.



> There are no default values for `expiresIn`, `notBefore`, `audience`, `subject`, `issuer`.  These claims can also be provided in the payload directly with `exp`, `nbf`, `aud`, `sub` and `iss` respectively, but you **_can't_** include in both places.

Remember that `exp`, `nbf` and `iat` are **NumericDate**, see related [Token Expiration (exp claim)](#token-expiration-exp-claim)


The header can be customized via the `options.header` object.

Generated jwts will include an `iat` (issued at) claim by default unless `noTimestamp` is specified. If `iat` is inserted in the payload, it will be used instead of the real timestamp for calculating other things like `exp` given a timespan in `options.expiresIn`.

Synchronous Sign with default (HMAC SHA256)

```js
var jwt = require('jsonwebtoken');
var token = jwt.sign({ foo: 'bar' }, 'shhhhh');
```

Synchronous Sign with RSA SHA256
```js
// sign with RSA SHA256
var privateKey = fs.readFileSync('private.key');
var token = jwt.sign({ foo: 'bar' }, privateKey, { algorithm: 'RS256' });
```

Sign asynchronously
```js
jwt.sign({ foo: 'bar' }, privateKey, { algorithm: 'RS256' }, function(err, token) {
  console.log(token);
});
```

Backdate a jwt 30 seconds
```js
var older_token = jwt.sign({ foo: 'bar', iat: Math.floor(Date.now() / 1000) - 30 }, 'shhhhh');
```

#### Token Expiration (exp claim)

The standard for JWT defines an `exp` claim for expiration. The expiration is represented as a **NumericDate**:

> A JSON numeric value representing the number of seconds from 1970-01-01T00:00:00Z UTC until the specified UTC date/time, ignoring leap seconds.  This is equivalent to the IEEE Std 1003.1, 2013 Edition [POSIX.1] definition "Seconds Since the Epoch", in which each day is accounted for by exactly 86400 seconds, other than that non-integer values can be represented.  See RFC 3339 [RFC3339] for details regarding date/times in general and UTC in particular.

This means that the `exp` field should contain the number of seconds since the epoch.

Signing a token with 1 hour of expiration:

```javascript
jwt.sign({
  exp: Math.floor(Date.now() / 1000) + (60 * 60),
  data: 'foobar'
}, 'secret');
```

Another way to generate a token like this with this library is:

```javascript
jwt.sign({
  data: 'foobar'
}, 'secret', { expiresIn: 60 * 60 });

//or even better:

jwt.sign({
  data: 'foobar'
}, 'secret', { expiresIn: '1h' });
```

See also:

* [Install](/node-jsonwebtoken/install)
* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)

* [Supported algorithms](/node-jsonwebtoken/algorithms)
* [Errors & codes](/node-jsonwebtoken/errors)
* [Refreshing JWTs](/node-jsonwebtoken/refreshing-jwts)
* [Migrations](/node-jsonwebtoken/migrations)