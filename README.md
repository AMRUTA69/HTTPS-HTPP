# HTTP vs HTTPS Analysis

**Task 16 · Cyber Security Track · Veda Technology Internship (Level 1, Day 16)**

Compare HTTP and HTTPS and explain the security benefits of TLS, using Google Chrome and Developer Tools.

## Objective

Understand secure web communication by observing how an HTTPS site and a plain HTTP site behave in the browser.

## Tools Used

- Google Chrome
- Chrome Developer Tools (Network and Security panels)

## Test Sites

| Protocol | Site |
|----------|------|
| HTTPS | https://www.wikipedia.org |
| HTTP | http://neverssl.com (serves plain HTTP on purpose) |

## HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|---------|------|-------|
| Full name | HyperText Transfer Protocol | HTTP over TLS (Secure) |
| Default port | 80 | 443 |
| Encryption | None (plain text) | Yes (TLS) |
| Authentication | Server identity not verified | Certificate verified by a trusted CA |
| Data integrity | Data can be altered in transit | Tampering is detected |
| Browser indicator | "Not secure" warning | Secure connection indicator |
| Safe for logins/payments | No | Yes |

## Observations

### 1. HTTPS: Certificate
Chrome shows "Connection is secure" and "Certificate is valid" for Wikipedia.

### 2. HTTPS: Network request
Request URL starts with `https://`, status `200 OK`, remote address ends with `:443`.

### 3. HTTPS: TLS details
The Security panel reports a valid and trusted certificate, and a connection using **TLS 1.3, X25519 and AES_128_GCM**.

### 4. HTTP: Browser warning
Chrome marks the page as **Not secure** and warns that the site doesn't support a secure connection.

### 5. HTTP: Network request
Request URL starts with `http://`, remote address ends with `:80`, and there is no TLS.

## Security Benefits of TLS

- **Encryption:** data is unreadable to anyone intercepting it.
- **Authentication:** the server proves its identity with a trusted certificate, protecting against fake sites and man-in-the-middle attacks.
- **Integrity:** any change to data in transit is detected.

## Conclusion

Wikipedia over HTTPS used port 443, a trusted certificate and TLS 1.3 encryption. The HTTP page used port 80 with no encryption and was flagged "Not secure". HTTP is unsafe for sensitive data, so HTTPS should be used wherever user information is handled.

## Interview Questions

**What is HTTPS?**
HTTP secured with TLS, giving encrypted, authenticated and tamper-proof communication.

**What is TLS?**
Transport Layer Security, the successor to SSL, which handles the handshake, key exchange and encryption between client and server.

**Why is HTTP insecure for sensitive data?**
Everything travels in plain text, so credentials can be intercepted or modified, and the server's identity cannot be verified.

## Author

Amruta · Veda Technology Intern
