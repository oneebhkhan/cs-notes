Short for Open Authorization. It is a standard authorization framework for token-based authorization on the internet.

OAuth is an _authorization_ protocol and not an _authentication protocol_. 

**Typical OAuth 2.0 implementation:**
![[oauth-flow.png | 450]]
OAuth allows resource owners (account owners) to authorize third-party client applications to access server resources without providing their credentials.

OAuth acts as an intermediary on behalf of the end user, providing the third-party service with an access token that authorizes specific account information to be shared.

### OAuth 2.0
OAuth 2.0 access tokens are "short-lived" -- from session-based to a couple weeks -- but utilize **refresh tokens** to acquire a new access token rather than have the user go through the entire process again to reauthorize the application.

Critics of OAuth 2.0 say it is more complex, less interoperable, less useful, more incomplete and most likely to result in insecure implementations.  However, it has <mark style="background: #ABF7F7A6;">still become widely adopted throughout the industry</mark>.