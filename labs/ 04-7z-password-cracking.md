# Lab 04: Password Cracking an Encrypted 7-Zip Archive

**Category:** Password Attacks
**Tools:** John the Ripper, rockyou.txt, Kali Linux
**Environment:** Self-created archive, isolated VM

## Objective
Assess how vulnerable a weak password is when protecting an AES-encrypted archive.

## Steps
1. Created a password-protected 7z archive with a deliberately weak password.
2. Extracted the hash using John the Ripper's 7z2john utility.
3. Ran a dictionary attack against the hash using the rockyou.txt wordlist.

## Findings
The password was recovered in a short time despite AES encryption, because the weakness was the password itself, not the encryption algorithm.

## Takeaway
Strong encryption doesn't compensate for a weak passphrase. Long, unique, high-entropy passwords (or a password manager) are what actually provide protection.
