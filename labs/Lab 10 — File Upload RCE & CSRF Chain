# Lab 10: Chained Attack — File Upload RCE and CSRF

**Category:** Web Exploitation
**Tools:** DVWA (Damn Vulnerable Web Application), Apache HTTP Server
**Environment:** Local DVWA instance

## Objective
Chain two independent vulnerabilities — an unrestricted file upload and a CSRF flaw — to demonstrate combined server and account compromise.

## Part A: File upload to remote code execution
1. Identified that DVWA's upload function didn't validate file type, allowing a `.php` web shell to be uploaded.
2. Uploaded a PHP web shell; Apache executed it on access since it was a valid PHP file in a web-accessible directory.
3. Used the `?cmd=` parameter to pass commands through the shell, which PHP executed via `system()` on the underlying Linux host.
4. Achieved command execution as the web server user (`www-data`) and established a reverse shell back to my attacking machine.

## Part B: CSRF to account takeover
1. Identified that the password-change function didn't verify request origin or require re-authentication.
2. Built a CSRF payload (an `<img>` tag pointing at the password-change endpoint with new password parameters).
3. When a logged-in victim's browser loaded the payload, it automatically sent the request. The browser attached the victim's valid session cookie, so the server treated it as a legitimate, authenticated request.
4. The account password was changed without the victim's knowledge or consent.

## Findings
Two unrelated weaknesses (no upload validation, no CSRF protection) combined into full compromise of both the server (via the shell) and a user account (via CSRF). Neither flaw alone requires the other, but together they significantly widen the impact.

## Takeaway
Reinforced layered defense: validate and restrict file uploads (type, extension, execution permissions, storage location outside the webroot), and protect state-changing requests with CSRF tokens and origin checks, independent of whether the session cookie is valid.
