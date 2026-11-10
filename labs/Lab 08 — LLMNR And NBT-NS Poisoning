# Lab 08: LLMNR/NBT-NS Poisoning and Hash Cracking

**Category:** Active Directory / Internal Network Attacks
**Tools:** Responder, John the Ripper, rockyou.txt, Kali Linux
**Environment:** Isolated Windows + Kali lab network

## Objective
Demonstrate how legacy Windows name-resolution protocols (LLMNR/NBT-NS) can be abused to capture authentication hashes on a local network.

## Steps
1. Ran Responder on the Kali VM's network interface to listen for name-resolution broadcasts.
2. From the Windows victim VM, triggered a lookup for a hostname that doesn't exist (simulating a common real-world scenario, like a mistyped network share).
3. Responder answered the broadcast, posing as the requested host.
4. Windows automatically attempted NTLMv2 authentication against the "resolved" host, sending its NTLMv2 hash to my machine.
5. Captured the hash and cracked it offline using John the Ripper with the rockyou.txt wordlist.

## Findings
Recovered the plaintext password in under a minute. The core issue: when DNS fails, Windows falls back to LLMNR/NBT-NS broadcasts, which have no authentication — any host on the network can answer and intercept the resulting authentication attempt.

## Takeaway
This is a well-known and still common internal network attack. The fix is organizational hardening, not user behavior: disable LLMNR and NBT-NS via Group Policy, since there's rarely a legitimate reason to keep them enabled on a modern network.
