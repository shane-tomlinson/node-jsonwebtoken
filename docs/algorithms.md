[&larr; jsonwebtoken Documentation](/node-jsonwebtoken/)

# Supported algorithms

The following algorithms are currently supported.

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


See also:

* [Install](/node-jsonwebtoken/install)
* [jwt.sign](/node-jsonwebtoken/sign)
* [jwt.verify](/node-jsonwebtoken/verify)
* [jwt.decode](/node-jsonwebtoken/decode)

* [Supported algorithms](/node-jsonwebtoken/algorithms)
* [Errors & codes](/node-jsonwebtoken/errors)
* [Refreshing JWTs](/node-jsonwebtoken/refreshing-jwts)
* [Migrations](/node-jsonwebtoken/migrations)