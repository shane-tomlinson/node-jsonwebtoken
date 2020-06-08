[&larr; API Documentation](/node-jsonwebtoken/)

# jwt.decode(token [, options])

(Synchronous) Returns the decoded payload without verifying if the signature is valid.

> __Warning:__ This will __not__ verify whether the signature is valid. You should __not__ use this for untrusted messages. You most likely want to use `jwt.verify` instead.

> __Warning:__ When the token comes from an untrusted source (e.g. user input or external request), the returned decoded payload should be treated like any other user input; please make sure to sanitize and only work with properties that are expected


`token` is the JsonWebToken string

`options`:

* `json`: force JSON.parse on the payload even if the header doesn't contain `"typ":"JWT"`.
* `complete`: return an object with the decoded payload and header.

Example

```js
// get the decoded payload ignoring signature, no secretOrPrivateKey needed
var decoded = jwt.decode(token);

// get the decoded payload and header
var decoded = jwt.decode(token, {complete: true});
console.log(decoded.header);
console.log(decoded.payload)
```

See also:

* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [Errors & codes](/node-jsonwebtoken/errors)
