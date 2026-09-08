# Session-Cookie Configuration Inspection

**Author:** Kaizen Almoite  
**Environment:** TryHackMe — Walking an Application

## The problem

Inspect the session attributes used by the customer dashboard.

## What I investigated

- Opened Firefox Storage on the Acme customer dashboard.
- Reviewed the session cookie and the site transport.

## What I found

- The session row shows `HttpOnly: false`, `Secure: false` and `SameSite: None`.
- The application is accessed over HTTP.
- These are configuration observations; the screenshot does not demonstrate session theft, replay, CSRF or account takeover.

## Recommendations

- Use HTTPS and appropriate cookie attributes for deployed session handling.
- Evaluate expiry, logout and authorization behavior separately from cookie inspection.

## What I learned

Cookie configuration provides a focused security observation, while exploitability requires evidence of an actual attack path.

## Evidence

![Acme customer dashboard with a session cookie displayed in Firefox Storage: HttpOnly false, Secure false, SameSite None.](screenshots/01-acme-session-cookie-attributes.png)

**Evidence:** Acme customer dashboard with a session cookie displayed in Firefox Storage: HttpOnly false, Secure false, SameSite None.

**Interpretation limit:** The lab uses HTTP. This is an attribute observation; no session replay, XSS exploit, CSRF exploit or account takeover is shown.
