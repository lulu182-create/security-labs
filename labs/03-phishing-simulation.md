# Lab 03: Phishing Page Simulation

**Category:** Social Engineering
**Tools:** Zphisher (Kali/VirtualBox)
**Environment:** Local VM, locally hosted page, test credentials only

## Objective
Understand how credential-harvesting phishing pages work from the attacker's side, to better recognize and defend against them.

## Steps
1. Ran Zphisher in a VirtualBox Ubuntu VM.
2. Selected a cloned login-page template and hosted it locally.
3. Generated an access link and submitted test (non-real) credentials as a simulated victim.
4. Reviewed the captured data: submitted credentials and the simulated victim's IP address, logged automatically to a local file.

## Findings
The tool captured username, password, and IP address instantly on submission, with no indication to the "victim" that the page was fake. This showed how convincing a cloned login page can look, and how little a victim needs to do (just type and submit) for credentials to be captured.

## Takeaway
Reinforced practical defenses: checking the URL bar before entering credentials, enabling MFA so a stolen password alone isn't enough, and treating unsolicited login links with suspicion.

**Note:** Performed entirely in an isolated lab with test accounts I created for this purpose. No real credentials, real victims, or public-facing infrastructure were used.
