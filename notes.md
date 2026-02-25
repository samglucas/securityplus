# Security+ Class Notes

## Comparison of Cryptographic Algorithms

| Algorithm Type | Algorithm Name | Real-World Example / Use Case |
| :--- | :--- | :--- |
| **Symmetric** | Advanced Encryption Standard (AES) | **Secure Wi-Fi (WPA2/WPA3):** AES is the gold standard for securing home and enterprise wireless networks. |
| **Symmetric** | Triple DES (3DES) | **Legacy Banking:** Historically used by the payments industry for EMV chip cards and ATM PIN encryption (now being phased out for AES). |
| **Symmetric** | Blowfish | **Password Managers:** Used by tools like KeePass to encrypt local database files due to its speed on smaller microprocessors. |
| **Symmetric** | Rivest Cipher (RC4) | **Legacy Web Browsing:** Formerly the most widely used stream cipher in SSL/TLS (now deprecated due to security vulnerabilities). |
| **Symmetric** | Salsa20 | **High-Speed Messaging:** Used in the XSalsa20 variant by the NaCl library and Libsodium for high-performance, secure communication. |
| **Asymmetric** | RSA | **Web Security (SSL/TLS):** Used for the initial handshake and identity verification when you visit an `https://` website. |
| **Asymmetric** | Digital Signature Algorithm (DSA) | **Software Distribution:** Used to sign Linux kernel updates or software packages to ensure the code hasn't been tampered with. |
| **Asymmetric** | Elliptic Curve Cryptography (ECC) | **Cryptocurrencies:** Bitcoin and Ethereum use ECC (specifically Secp256k1) to generate public/private keys and sign transactions. |
| **Asymmetric** | Diffie-Hellman (DH) | **Secure Key Exchange:** Allows two parties (like your phone and a server) to create a shared secret key over an insecure channel without ever sending the key itself. |

## Hashing Algorithms Comparison

| Algorithm | Real-World Example / Use Case |
| :--- | :--- |
| **Message Digest 5 (MD5)** | **File Integrity Checks:** Commonly used by software distributors to provide a "checksum" so users can verify a downloaded `.iso` or `.exe` file isn't corrupted. *(Note: Not secure against intentional tampering).* |
| **Secure Hash Algorithm 1 (SHA-1)** | **Git Version Control:** Git uses SHA-1 hashes to identify and track changes to files and commits in a repository. |
| **SHA-2 (SHA-256, SHA-512)** | **Blockchain & Mining:** SHA-256 is the engine behind Bitcoin mining and is the standard for securing modern SSL/TLS certificates. |
| **SHA-3** | **Next-Gen Security:** Often used as a high-security alternative to SHA-2 in hardware implementations and sensitive government applications because its internal "Sponge" design is resistant to different types of attacks. |
| **RIPEMD (e.g., RIPEMD-160)** | **Bitcoin Addresses:** Used in combination with SHA-256 to create shorter, manageable public wallet addresses for cryptocurrencies. |

## Network Redirection Attacks & Mitigations

### 1. ARP Poisoning
* **Description:** Sending falsified ARP messages over a local area network to link an attacker's MAC address with the IP address of a legitimate gateway.
* **Mitigation:** Use **Dynamic ARP Inspection (DAI)** on switches and implement static ARP entries for critical systems.

### 2. DNS Poisoning (Cache Poisoning)
* **Description:** Corrupting a DNS resolver's cache to redirect users from a legitimate website to a malicious IP address.
* **Mitigation:** Implement **DNSSEC** (Domain Name System Security Extensions) and use modern, randomized source ports for DNS queries.

### 3. Rogue Services
* **Description:** Setting up unauthorized servers (like a Rogue DHCP or Rogue Access Point) to intercept traffic or redirect users to controlled environments.
* **Mitigation:** Enable **DHCP Snooping** on switches and use **WIPS** (Wireless Intrusion Prevention Systems) to detect unauthorized APs.

### 4. URL Redirection
* **Description:** Exploiting web application vulnerabilities that redirect users to external, malicious URLs without proper validation (Open Redirects).
* **Mitigation:** Avoid using user-provided input in redirect targets; implement a **whitelist** of approved URLs.

### 5. Domain Hijacking
* **Description:** Gaining unauthorized control of a domain's registration to change DNS settings at the registrar level, often through social engineering or stolen credentials.
* **Mitigation:** Enable **Registrar Locking**, use Multi-Factor Authentication (MFA) on registrar accounts, and monitor WHOIS records.

### 6. VLAN Hopping
* **Description:** Attacking a switch via "switch spoofing" or "double tagging" to gain access to traffic on other VLANs that should be restricted.
* **Mitigation:** Disable **Dynamic Trunking Protocol (DTP)**, ensure the native VLAN is not used for user traffic, and explicitly prune unused VLANs from trunks.

## On-Path Techniques & Mitigations

### 1. Replay Attack
* **Description:** An attacker captures valid network traffic (like an authentication packet) and later re-transmits it to the server to gain unauthorized access or repeat a transaction.
* **Mitigation:** Use **one-time tokens (nonces)**, timestamps, and sequence numbers to ensure each request is unique and expires quickly.

### 2. Session Replay / Hijacking
* **Description:** While similar to a standard replay, this specifically involves capturing a valid session ID or cookie to take over an active user's session without needing credentials.
* **Mitigation:** Implement **Session ID regeneration** after login and ensure all session cookies use the `Secure` and `HttpOnly` flags.

### 3. Downgrade Attacks
* **Description:** Forcing a connection to move from a secure, modern protocol (like TLS 1.3) to an older, vulnerable version (like SSL 3.0) to exploit known cryptographic weaknesses.
* **Mitigation:** Disable support for legacy protocols (SSL 2.0/3.0, TLS 1.0/1.1) and ensure servers are configured to prefer high-strength ciphers.

### 4. SSL Stripping (HTTP Stripping)
* **Description:** The attacker intercepts the initial request to a secure site and forces the victim's browser to communicate over unencrypted HTTP while the attacker maintains an HTTPS connection with the server.
* **Mitigation:** Use **HSTS (HTTP Strict Transport Security)** to instruct browsers to never connect to your domain via HTTP.

### 5. Browser-Based (Man-in-the-Browser)
* **Description:** Compromising the browser itself (often via malicious extensions) to intercept or modify data *before* it is encrypted and sent over the network.
* **Mitigation:** Use **Endpoint Detection and Response (EDR)**, keep browsers updated, and enforce strict policies against unauthorized browser extensions.

# Password & Hash Cracking Techniques

## Password Cracking (Active/Online)

### 1. Brute Force
* **Description:** An automated attempt to guess a password by trying every possible combination of characters (letters, numbers, symbols) until the correct one is found.
* **Mitigation:** Implement **account lockout policies**, progressive delays between failed attempts, and require complex, long passwords.

### 2. Dictionary Attack
* **Description:** A more efficient form of brute force that uses a pre-defined list (a "dictionary") of common passwords, words, and previously leaked credentials.
* **Mitigation:** Enforce the use of **non-dictionary words** and use multi-factor authentication (MFA) to render guessed passwords useless.

### 3. Password Spraying
* **Description:** A "low and slow" attack where one or two common passwords (e.g., `Password123!`) are tried against a large number of usernames to avoid triggering account lockouts.
* **Mitigation:** Use **MFA** and monitor for high volumes of failed login attempts across multiple accounts from a single IP address.

### 4. Credential Stuffing
* **Description:** Using large lists of username/password pairs leaked from one service to gain access to accounts on other services (relying on the fact that users reuse passwords).
* **Mitigation:** Use **MFA**, check for leaked credentials via services like HaveIBeenPwned, and encourage the use of password managers.

## Hash Cracking (Passive/Offline)

### 1. Birthday Attack
* **Description:** Based on the "Birthday Paradox" in probability; it searches for **collisions** (two different inputs producing the same hash) to bypass integrity checks or digital signatures.
* **Mitigation:** Use modern hashing algorithms with a larger output size, such as **SHA-256** or **SHA-3**, to make finding collisions mathematically improbable.

### 2. Rainbow Table
* **Description:** Using massive, pre-computed tables of plaintext passwords and their corresponding hashes to quickly reverse a captured hash without needing to compute it manually.
* **Mitigation:** Always use a **Salt** (a unique, random string added to each password before hashing) to make pre-computed tables ineffective.

### 3. Pass the Hash (PtH)
* **Description:** An attacker captures a stored password hash and uses it directly to authenticate to a remote server or service without ever needing to "crack" it into plaintext.
* **Mitigation:** Implement **Least Privilege**, disable NTLM where possible in favor of Kerberos, and use tools like **LAPS** (Local Administrator Password Solution).

## Wireless & Bluetooth attacks

### 1. Wireless Reconnaissance
* **Description:** The process of discovering and mapping wireless networks, identifying SSIDs, signal strengths, encryption types (WPA2/WPA3), and connected clients using tools like Aircrack-ng or WiFite.
* **Mitigation:** Disable SSID broadcasting (though this is not a strong defense), use strong encryption, and monitor for unauthorized scanning activity.

### 2. Rogue AP (Access Point)
* **Description:** An unauthorized wireless access point connected to a secure network without the administrator's knowledge, often used to bypass perimeter security.
* **Mitigation:** Use **Wireless Intrusion Prevention Systems (WIPS)** and perform regular physical and logical site audits.

### 3. Evil Twin
* **Description:** A fraudulent Wi-Fi access point that appears to be a legitimate one (sharing the same SSID), designed to trick users into connecting so the attacker can intercept their traffic.
* **Mitigation:** Use **Certificate-based authentication** (EAP-TLS) and educate users to avoid connecting to "Open" public Wi-Fi without a VPN.

### 4. Disassociation Attack
* **Description:** Sending spoofed disassociation frames to a client, forcing them to disconnect from the legitimate AP. This is often used to capture WPA handshakes or force a user onto an Evil Twin.
* **Mitigation:** Implement **802.11w (Management Frame Protection)** to encrypt management frames.

### 5. Jamming
* **Description:** A Denial of Service (DoS) attack that uses a radio frequency (RF) transmitter to flood the wireless spectrum with noise, preventing legitimate devices from communicating.
* **Mitigation:** Locate the source of interference using a spectrum analyzer; use wired connections for critical infrastructure.

### 6. Bluejacking
* **Description:** Sending unsolicited messages (like digital business cards) to Bluetooth-enabled devices. It is generally a nuisance rather than a data-theft attack.
* **Mitigation:** Set Bluetooth devices to **"Non-discoverable"** mode when not in use.

### 7. Bluesnarfing
* **Description:** The unauthorized access of information (contacts, photos, emails) from a wireless device through a Bluetooth connection.
* **Mitigation:** Keep device firmware updated, use strong pairing PINs, and disable Bluetooth in public spaces if not needed.

## Access Control Rules

### 1. Implicit Deny
* **Description:** A security principle where any traffic that is not explicitly permitted by a rule is automatically blocked. This is the default "last rule" in most modern firewalls and ACLs.
* **Mitigation/Benefit:** Prevents unauthorized access by ensuring only known-good traffic is allowed through the network.

### 2. Implicit Allow
* **Description:** A configuration where all traffic is permitted unless a specific rule exists to block it. This is generally considered a security risk and is rarely used in high-security environments.
* **Mitigation/Benefit:** Usually replaced by a "Zero Trust" or "Implicit Deny" posture to improve security.

## Switch Security Features

### 1. Port Security
* **Description:** Limits the number of MAC addresses that can connect to a single physical switch port. It can trigger an action (like shutting down the port) if an unauthorized device is plugged in.
* **Mitigation:** Prevents unauthorized devices from joining the network and mitigates MAC flooding attacks.

### 2. MAC Filtering
* **Description:** A list of approved MAC addresses allowed to communicate through a device. While easily spoofed, it provides a basic layer of hardware-level control.
* **Mitigation:** Use in conjunction with 802.1X for stronger identity-based access control.

### 3. DHCP Snooping
* **Description:** A security feature that acts like a firewall between untrusted hosts and trusted DHCP servers. It builds a mapping table of valid IP/MAC pairings.
* **Mitigation:** Prevents **Rogue DHCP** servers and **DHCP Starvation** attacks.

### 4. Loop Protection
* **Description:** Mechanisms like **Spanning Tree Protocol (STP)** that detect and prevent switching loops, which occur when there are multiple active paths between switches.
* **Mitigation:** Prevents broadcast storms that can crash an entire network segment.

### 5. Flood Guard
* **Description:** A feature designed to prevent resource exhaustion by limiting the number of MAC addresses learned per port or the rate of incoming traffic.
* **Mitigation:** Protects against **MAC Flooding** attacks that attempt to turn a switch into a "hub" to intercept traffic.

### 6. MACsec (802.1AE)
* **Description:** An IEEE standard that provides point-to-point encryption and integrity on wired LANs at Layer 2.
* **Mitigation:** Protects against eavesdropping, man-in-the-middle attacks, and replay attacks at the hardware level.
