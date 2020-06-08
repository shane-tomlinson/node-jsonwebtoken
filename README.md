![JWT Logo](https://jwt.io/img/pic_logo.svg)

# jsonwebtoken


| **Build** | **Dependency** |
|-----------|---------------|
| [![Build Status](https://secure.travis-ci.org/auth0/node-jsonwebtoken.svg?branch=master)](http://travis-ci.org/auth0/node-jsonwebtoken) | [![Dependency Status](https://david-dm.org/auth0/node-jsonwebtoken.svg)](https://david-dm.org/auth0/node-jsonwebtoken) |


An implementation of [JSON Web Tokens](https://tools.ietf.org/html/rfc7519).

This was developed against `draft-ietf-oauth-json-web-token-08`. It makes use of [node-jws](https://github.com/brianloveswords/node-jws).

# Install

```bash
$ npm install jsonwebtoken
```

# Usage

See [API docs](https://shane-tomlinson.github.io/node-jsonwebtoken/).


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

# Migration notes

* [From v7 to v8](https://github.com/auth0/node-jsonwebtoken/wiki/Migration-Notes:-v7-to-v8)

# TODO

* X.509 certificate chain is not checked

## Issue Reporting

If you have found a bug or if you have a feature request, please report them at this repository's [issues section](https://github.com/auth0/node-jsonwebtoken/issues). Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## Author

[Auth0](https://auth0.com)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.
