# Lab 02: Plaintext HTTP Credential Capture

**Category:** Web Security
**Tools:** Wireshark, custom HTML login form
**Environment:** Local loopback, self-built form

## Objective
Demonstrate why HTTP (unencrypted) login forms expose credentials to anyone who can observe network traffic.

## Steps
1. Built a simple HTML login page with username/password fields, submitted over plain HTTP.
2. Started a Wireshark capture on the loopback interface.
3. Submitted test credentials through the form.
4. Filtered the capture for HTTP traffic and inspected the POST request.

## Findings
The full TCP handshake and raw HTTP request were visible in the capture, including the username and password in cleartext in the POST body. No encryption meant the credentials were readable by anyone who could intercept the traffic.

## Takeaway
A direct, visual demonstration of why HTTPS (TLS) is mandatory for any form handling credentials — plaintext HTTP offers no confidentiality at all, even on a trusted-looking network.
