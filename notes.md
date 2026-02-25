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
