[&larr; API Documentation](/node-jsonwebtoken/)

# Errors & Codes
Possible thrown errors during verification.
Error is the first argument of the verification callback.

### TokenExpiredError

Thrown error if the token is expired.

Error object:

* name: 'TokenExpiredError'
* message: 'jwt expired'
* expiredAt: [ExpDate]

```js
jwt.verify(token, 'shhhhh', function(err, decoded) {
  if (err) {
    /*
      err = {
        name: 'TokenExpiredError',
        message: 'jwt expired',
        expiredAt: 1408621000
      }
    */
  }
});
```

### JsonWebTokenError
Error object:

* name: 'JsonWebTokenError'
* message:
  * 'jwt malformed'
  * 'jwt signature is required'
  * 'invalid signature'
  * 'jwt audience invalid. expected: [OPTIONS AUDIENCE]'
  * 'jwt issuer invalid. expected: [OPTIONS ISSUER]'
  * 'jwt id invalid. expected: [OPTIONS JWT ID]'
  * 'jwt subject invalid. expected: [OPTIONS SUBJECT]'

```js
jwt.verify(token, 'shhhhh', function(err, decoded) {
  if (err) {
    /*
      err = {
        name: 'JsonWebTokenError',
        message: 'jwt malformed'
      }
    */
  }
});
```

### NotBeforeError
Thrown if current time is before the nbf claim.

Error object:

* name: 'NotBeforeError'
* message: 'jwt not active'
* date: 2018-10-04T16:10:44.000Z

```js
jwt.verify(token, 'shhhhh', function(err, decoded) {
  if (err) {
    /*
      err = {
        name: 'NotBeforeError',
        message: 'jwt not active',
        date: 2018-10-04T16:10:44.000Z
      }
    */
  }
});
```

See also:

* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)
