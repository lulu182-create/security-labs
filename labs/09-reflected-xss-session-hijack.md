# Lab 09: Reflected XSS to Session Hijacking

**Category:** Web Exploitation
**Tools:** Browser DevTools, vulnerable test web app
**Environment:** Local/self-hosted vulnerable application

## Objective
Demonstrate the real-world impact of a reflected XSS vulnerability by escalating it to full session hijacking.

## Steps
1. Identified a reflected XSS injection point in a test application.
2. Crafted a payload to execute JavaScript in the victim's browser context and read `document.cookie`.
3. Exfiltrated the session cookie (PHPSESSID) to a server I controlled via a crafted HTTP request.
4. Injected the captured cookie into a fresh browser session using DevTools.
5. Accessed the application and confirmed the server granted access without requiring credentials.

## Findings
Because the session cookie alone represented an authenticated session, possessing it was functionally equivalent to possessing the password. The server had no way to distinguish the hijacked session from the legitimate one.

## Takeaway
Showed concretely why output encoding/input sanitization (to prevent XSS in the first place) and defense-in-depth cookie flags — `HttpOnly` (blocks JavaScript access to cookies) and `Secure` (cookie only sent over HTTPS) — are both necessary. Either control alone reduces the risk; together they close this specific attack path.
