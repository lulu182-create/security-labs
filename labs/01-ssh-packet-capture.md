# Lab 01: SSH Connection Analysis & Packet Capture

**Category:** Networking Fundamentals
**Tools:** OpenSSH, Wireshark/tcpdump, Ubuntu VM (VirtualBox)
**Environment:** Host (Windows) to isolated Ubuntu VM, local network only

## Objective
Establish an SSH connection between a Windows host and an Ubuntu VM, and observe the connection at the packet level to understand how the SSH handshake works.

## Steps
1. Configured SSH on the Ubuntu VM and confirmed it was listening on port 22.
2. Verified host reachability with `ping`.
3. Initiated an SSH session from the Windows host to the VM.
4. Ran `tcpdump` on the VM to capture live traffic during the connection.
5. Reviewed the capture to identify the TCP three-way handshake and the SSH key exchange.

## Findings
Watched the full handshake sequence in real time (SYN, SYN-ACK, ACK) followed by the SSH protocol version exchange and key negotiation. Confirmed that SSH traffic, unlike Telnet, is encrypted after the handshake, so no credentials or session data were visible in plaintext.

## Takeaway
Reinforced how TCP and SSH negotiate a connection, and why SSH is the standard replacement for unencrypted remote access protocols like Telnet.
