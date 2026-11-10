# Lab 06: Brute-Force Attack Against a Web Login Form

**Category:** Web Security
**Tools:** THC Hydra, local HTTP server (port 8080)
**Environment:** Self-hosted test server, isolated network

## Objective
Test whether a web application's login form was vulnerable to automated credential guessing, and understand what controls prevent it.

## Steps
1. Stood up a local HTTP login form on port 8080 for a test account ("securityadmin").
2. Configured Hydra with the correct POST request parameters (username/password fields, failure string).
3. Ran Hydra against the form with a password wordlist.
4. Identified the valid credential pair once Hydra matched a successful response.

## Findings
Hydra successfully brute-forced the account because the form had no rate limiting, account lockout, or CAPTCHA.

## Takeaway
Demonstrated exactly why rate limiting, lockout policies, and MFA exist — without them, login forms are trivially automatable targets.
