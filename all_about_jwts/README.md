# All About JWT's

Json Web Tokens

[jwt.io](https://jwt.io/)

[base64encode.org](https://www.base64encode.org/)

[RFC-7519](https://tools.ietf.org/html/rfc7519)

[OWASP](https://www.owasp.org/index.php/Main_Page)

[100% Stateless with JWT (JSON Web Token) by Hubert Sablonnière](https://www.youtube.com/watch?v=67mezK3NzpU)

## Context
- Cookies 
- Uses plain text
- Easy to spoof

## Compare Session ID & JWT
- Session IDs
   * Referencial
   * Stateful
   * Store ID in database (extra query)
   * Memory (network issues)
   * Complex for Service-based architecture
- JWTs
   * Self-Contained 
   * Stateless
   * Allow/restrict access for a specified period of time

## Parts of JWT
- Header
```json
{
   "alg": "HS256",
   "typ": "JWT"
}
```
- Payload
```json
{
   "sub": <subject>,
   "iat": <timestamp>,
   "exp": <timestamp>,
   "nbf": <timestamp>,
   "jti": "token id",
}
```
    * Claims 
    * Registerd Claims
    * Private Claims
- Signature
```
HMACSHA256(
   base64UrlEncode(header) + "." +
   base64UrlEncode(payload) + "." +
   secret
)
```

## Security Considerations
- OWASP Does not recommand localStorage 
    * Safe against CSRF attacks
    * vulnerable to XSS attacks
- Store in secure cookie
- Include CSRF token in JWT and store CSRF id in local storge
- Token Revocation



