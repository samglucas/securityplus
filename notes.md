# Security+ Class Notes

# Comparison of Cryptographic Algorithms

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

# Hashing Algorithms Comparison

| Algorithm | Real-World Example / Use Case |
| :--- | :--- |
| **Message Digest 5 (MD5)** | **File Integrity Checks:** Commonly used by software distributors to provide a "checksum" so users can verify a downloaded `.iso` or `.exe` file isn't corrupted. *(Note: Not secure against intentional tampering).* |
| **Secure Hash Algorithm 1 (SHA-1)** | **Git Version Control:** Git uses SHA-1 hashes to identify and track changes to files and commits in a repository. |
| **SHA-2 (SHA-256, SHA-512)** | **Blockchain & Mining:** SHA-256 is the engine behind Bitcoin mining and is the standard for securing modern SSL/TLS certificates. |
| **SHA-3** | **Next-Gen Security:** Often used as a high-security alternative to SHA-2 in hardware implementations and sensitive government applications because its internal "Sponge" design is resistant to different types of attacks. |
| **RIPEMD (e.g., RIPEMD-160)** | **Bitcoin Addresses:** Used in combination with SHA-256 to create shorter, manageable public wallet addresses for cryptocurrencies. |

# Network Redirection Attacks & Mitigations

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

# On-Path Techniques & Mitigations

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

# Wireless & Bluetooth attacks

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

# Intrusion Detection & Prevention Systems (IDPS)

## Detection vs. Prevention

### 1. IDS (Intrusion Detection System)
* **Description:** A "passive" monitoring system that alerts administrators when it detects potentially malicious activity or policy violations. It does not stop the traffic itself.
* **Benefit:** Provides visibility without the risk of accidentally blocking legitimate traffic (false positives).

### 2. IPS (Intrusion Prevention System)
* **Description:** An "active" system positioned in-line with network traffic. It can detect and automatically block or drop malicious packets in real-time.
* **Benefit:** Immediate mitigation of known threats and automated response.

## Detection Methodologies

### 1. Signature Database
* **Description:** Uses a library of known attack patterns (signatures) to identify threats. It is highly effective against known exploits but fails to detect "zero-day" attacks.
* **Mitigation:** Requires constant updates to the signature database to remain effective.

### 2. Heuristic (Behavioral/Anomaly) Analysis
* **Description:** Identifies threats by looking for deviations from a baseline of "normal" behavior. It is excellent for catching new or evolving threats.
* **Mitigation:** Can have a higher rate of false positives if the "normal" baseline is not well-defined.

### 3. Stateful Protocol Analysis
* **Description:** Deeply inspects protocols to ensure they are following their intended state and sequence (e.g., ensuring a TCP handshake follows the correct SYN-SYN/ACK-ACK flow).
* **Mitigation:** Prevents attacks that exploit protocol-level vulnerabilities or out-of-order packets.

## Deployment Scopes

### 1. NIDS / NIPS (Network-Based)
* **Description:** Deployed at strategic points in the network (like a span port or tap) to monitor all traffic flowing to and from all devices on that segment.
* **Constraint:** Cannot inspect encrypted traffic unless it has access to the decryption keys.

### 2. HIDS / HIPS (Host-Based)
* **Description:** Software installed directly on an endpoint (server, workstation) to monitor system calls, file integrity, and local logs.
* **Constraint:** Can be resource-intensive for the host and must be managed across every individual device.

### 3. WIDS / WIPS (Wireless)
* **Description:** Specialized systems that monitor the radio frequency spectrum for unauthorized access points (Rogue APs), jamming, or spoofing.
* **Benefit:** Essential for maintaining the "airgap" and preventing physical-proximity wireless attacks.

# Deception & Containment Techniques

### 1. Honeypot
* **Description:** A decoy system or network designed to look like a legitimate, high-value target (such as a database or file server). It exists solely to be probed, attacked, or compromised to gather intelligence on attacker methods.
* **Types:** * **Low-Interaction:** Mimics basic services to gather simple data.
    * **High-Interaction:** Runs actual operating systems and applications to observe complex attacker behavior.
* **Mitigation/Benefit:** Diverts attackers away from production systems and provides early warning of a breach.

### 2. DNS Sinkhole
* **Description:** A DNS server configured to hand out false information (usually a non-routable IP address or a loopback address) for known malicious domains.
* **How it Works:** When an infected host tries to contact its Command and Control (C2) server, the sinkhole intercepts the DNS request and redirects it, effectively "silencing" the malware.
* **Mitigation/Benefit:** Prevents data exfiltration and allows security teams to identify infected internal hosts by monitoring who is attempting to reach the sinkholed addresses.

# Email Security & Verification Technologies

### 1. S/MIME (Secure/Multipurpose Internet Mail Extensions)
* **Description:** A protocol used to digitally sign and encrypt email messages. It uses a public/private key pair to prove the sender's identity and ensure the message content hasn't been tampered with.
* **Mitigation:** Protects against eavesdropping and impersonation by providing end-to-end encryption and non-repudiation.

### 2. SPF (Sender Policy Framework)
* **Description:** A DNS-based record that lists all authorized IP addresses and domains allowed to send email on behalf of your domain.
* **How it Works:** The receiving server checks the SPF record in the DNS of the "From" address; if the sending IP isn't on the list, the email may be marked as spam or rejected.
* **Mitigation:** Prevents unauthorized IP addresses from spoofing your domain in the "envelope" of the email.

### 3. DKIM (DomainKeys Identified Mail)
* **Description:** Adds a digital signature to the header of an email. This signature is verified using a public key located in the sender's DNS records.
* **How it Works:** It ensures that the email's content (and specific headers) remained unchanged from the moment it left the sending server until it reached the recipient.
* **Mitigation:** Prevents tampering with the email content while in transit.

### 4. DMARC (Domain-based Message Authentication, Reporting, and Conformance)
* **Description:** A policy framework that ties SPF and DKIM together. It tells the receiving mail server what to do (None, Quarantine, or Reject) if an email fails SPF or DKIM checks.
* **How it Works:** It also provides a reporting mechanism so domain owners can see who is sending mail on their behalf and if they are failing authentication.
* **Mitigation:** Provides a unified policy to stop spoofing and phishing attacks while providing visibility into mail flow.

# Load Balancers & Proxies

## Load Balancers
**Definition:** A device or software application that distributes network or application traffic across a cluster of servers. This prevents any single server from becoming a bottleneck, ensuring high availability and reliability.

### 1. Active/Active
* **Description:** Every node in the cluster is actively handling traffic simultaneously.
* **Real-World Use Case:** A global e-commerce site during a "Black Friday" event. Incoming traffic is distributed across ten different web servers to prevent any single server from crashing under the massive volume of shoppers.
* **Benefit:** Provides maximum throughput and ensures that if one server fails, the others simply continue handling the load with minimal impact on performance.

### 2. Active/Passive
* **Description:** Only one node (the primary) is actively handling traffic, while the secondary node remains on standby. The secondary only takes over if the primary fails.
* **Real-World Use Case:** A hospital's electronic health record (EHR) database. To maintain strict data consistency, only one database server handles writes at a time. If it fails, a heartbeat monitor triggers the passive server to take over within seconds.
* **Benefit:** Ensures high availability for stateful applications where having multiple active writers might cause data corruption.

## Proxy Servers
**Definition:** A server that acts as an intermediary between a client (user) and a destination (server). It intercepts requests to provide security, privacy, or performance optimization.

### 1. Forward Proxies
* **Description:** Sits between a group of internal clients and the internet. It evaluates outgoing requests and then forwards them.
* **Real-World Use Case:** A high school network. When a student tries to visit a website, the forward proxy checks a blocklist. If the site is approved, the proxy fetches the page and delivers it to the student, hiding the student's internal IP from the website.
* **Benefit:** Centralized control over web traffic and improved security by masking the internal network structure.

### 2. Transparent Proxies
* **Description:** Intercepts traffic at the network level without requiring any configuration on the client's device. The user is often unaware their traffic is being proxied.
* **Real-World Use Case:** A coffee shop Wi-Fi "Captive Portal." When you connect and try to browse the web, the transparent proxy intercepts your request and redirects you to their "Terms and Conditions" page before allowing you to proceed.
* **Benefit:** Requires zero configuration from the end-user, making it ideal for public or guest networks.

### 3. Reverse Proxies
* **Description:** Sits in front of one or more internal web servers and handles incoming requests from the internet.
* **Real-World Use Case:** A major news website using **Nginx** or **Cloudflare**. Instead of users hitting the origin database directly, they hit the reverse proxy, which serves cached versions of the articles, protecting the origin server from high traffic and DDoS attacks.
* **Benefit:** Provides an additional layer of security, SSL/TLS offloading, and improved performance through caching.

### 4. Anonymous Proxies
* **Description:** A type of forward proxy that strips the user's identifying information (IP address) from the request headers before sending it to the destination.
* **Real-World Use Case:** An investigative journalist researching a sensitive topic. They use an anonymous proxy to browse public forums so that their home or office IP address isn't logged by the site administrators, protecting their location and identity.
* **Benefit:** Enhances user privacy and bypasses basic IP-based tracking or geo-blocking.

# Network Infrastructure & Security Protocols

## The OSI Model
**Definition:** A conceptual framework used to understand how data moves through a network, divided into 7 layers.

* **Layer 7: Application** – Where the user interacts (HTTP, FTP, SMTP).
* **Layer 6: Presentation** – Data encryption and formatting (JPEG, ASCII).
* **Layer 5: Session** – Establishes/manages connections (RPC, NetBIOS).
* **Layer 4: Transport** – End-to-end communication (TCP, UDP).
* **Layer 3: Network** – Routing and logical addressing (IP, ICMP).
* **Layer 2: Data Link** – Physical addressing and switching (MAC, Ethernet).
* **Layer 1: Physical** – Cables, bits, and electrical signals.



---

## Web Security & Encryption

### 1. SSL/TLS & HTTPS
* **SSL (Secure Sockets Layer):** The deprecated predecessor to TLS.
* **TLS (Transport Layer Security):** The modern standard for encrypting data between a client and a server.
* **HTTPS (Port 443):** Secure web browsing; HTTP traffic wrapped inside a TLS tunnel.
* **Cipher Suites:** A set of algorithms (key exchange, encryption, hashing) used to negotiate a secure connection.

### 2. SSH (Secure Shell) - Port 22
* **Description:** A cryptographic network protocol for operating network services securely over an unsecured network.
* **Use Case:** A System Administrator remotely logging into a Linux server terminal to perform maintenance.

## IPsec (Internet Protocol Security)
**Definition:** A suite of protocols used to secure IP communications by authenticating and encrypting each IP packet.

* **IKE (Internet Key Exchange):** Manages the "handshake" to set up secure keys between two parties.
* **AH (Authentication Header):** Provides data integrity and origin authentication, but **does not** provide encryption.
* **ESP (Encapsulating Security Payload):** Provides encryption, integrity, and authentication.
* **Use Case:** Setting up a Site-to-Site VPN to connect a branch office to the main headquarters.

## Common Network Services

| Service | Protocol | Port | Definition / Use Case |
| :--- | :--- | :--- | :--- |
| **DHCP** | UDP | 67/68 | Automatically assigns IP addresses to devices on a network. |
| **DNS** | TCP/UDP | 53 | Resolves human-readable names (google.com) to IP addresses. |
| **NTP** | UDP | 123 | Synchronizes the clocks of devices across a network for accurate logging. |
| **LDAP** | TCP/UDP | 389/636 | A directory service protocol used for centralized authentication (e.g., Active Directory). |

## Remote Access Protocols

* **Telnet (Port 23):** Unencrypted remote terminal access. **Use Case:** Legacy equipment maintenance (Avoid in production).
* **RDP (Port 3389):** Microsoft's Graphical User Interface (GUI) for remote desktop access.
* **VNC (Port 5900):** A platform-independent GUI remote access system.
* **HTTP/HTTPS:** Web-based consoles (like a router's admin page).

## Secure File Sharing

* **SMB (Server Message Block) - Port 445:** Primarily used by Windows for sharing files and printers. Modern versions (SMB 3.0+) support encryption.
* **NFS (Network File System) - Port 2049:** Primarily used in Linux/Unix environments to mount remote drives as if they were local.

## Secure Email Protocols

* **SMTP (Port 25/587):** Used for **sending** email from a client to a server.
* **SMTPS (Port 465):** Secure version of SMTP using TLS encryption.
* **POP3 (Port 110/995):** Downloads email from a server to a local client (typically deletes from server).
* **IMAP (Port 143/993):** Syncs email across multiple devices while keeping it stored on the server.

# Wi-Fi Encryption & Authentication Standards

## Wireless Encryption Generations

### 1. WPA (Wi-Fi Protected Access)
* **Description:** A temporary security protocol created to replace the highly vulnerable WEP. It introduced **TKIP** (Temporal Key Integrity Protocol) to dynamically change encryption keys.
* **Status:** Deprecated and insecure.

### 2. WPA2
* **Description:** The long-standing standard for Wi-Fi security. It replaced TKIP with **CCMP** (Counter Mode with Cipher Block Chaining Message Authentication Code Protocol), which uses **AES** encryption.
* **Vulnerability:** Susceptible to offline dictionary attacks and the **KRACK** (Key Reinstallation Attack) vulnerability if not patched.

### 3. WPA3
* **Description:** The modern standard that addresses WPA2's weaknesses. It mandates the use of **Protected Management Frames (PMF)** and replaces the vulnerable 4-way handshake with more robust methods.
* **Benefit:** Provides individualized data encryption even on open networks and resists brute-force attacks.

## Authentication Methods

### 1. PSK (Pre-Shared Key)
* **Description:** Also known as **WPA Personal**. Every user on the network uses the same passphrase to connect.
* **Use Case:** Home networks or small offices where managing individual user accounts is not feasible.

### 2. SAE (Simultaneous Authentication of Equals)
* **Description:** The core upgrade in **WPA3-Personal**. It uses a "Dragonfly" key exchange that is resistant to offline dictionary attacks.
* **Benefit:** Even if a user chooses a weak password, SAE makes it significantly harder for an attacker to crack it.

### 3. SAE-PK (SAE Public Key)
* **Description:** An extension of SAE that uses public-key cryptography to prevent "Evil Twin" attacks.
* **Use Case:** Verifying that the Access Point the client is connecting to is the legitimate one and hasn't been spoofed.

### 4. WPA Enterprise / 802.1X Mode
* **Description:** Instead of a shared password, users authenticate with their own credentials (username/password or certificates) via a **RADIUS** server.
* **Real-World Use Case:** A corporate office where employees log into the Wi-Fi using their Active Directory credentials. This allows for individual auditing and easy revocation of access.

### 5. Captive Portal
* **Description:** A web page that is displayed to newly connected users before they are granted broader access to the internet.
* **Real-World Use Case:** Airport or hotel Wi-Fi where you must enter a room number, email address, or accept "Terms of Service" before the internet starts working.
* **Security Note:** Often used in conjunction with an **Open** or **Transparent Proxy**.
