# Security+ Class Notes

# Procedural Documentation: Runbooks vs. Playbooks

### 1. Playbooks (The "What" and "Why")
* **Definition:** A high-level, strategic document that outlines the overarching response plan for a specific scenario or threat. It focuses on the workflow, communication, and decision-making process.
* **Goal:** To provide a consistent framework for managing complex situations (like a breach) from start to finish.
* **Content:** * Identifying stakeholders (Who to call: Legal, PR, C-Suite).
    * Compliance requirements (Reporting deadlines for GDPR/HIPAA).
    * Decision gates (When to shut down a server vs. when to monitor).
* **Example:** A "Ransomware Response Playbook" that dictates the phases of containment, eradication, and recovery.

### 2. Runbooks (The "How")
* **Definition:** A granular, step-by-step technical guide for completing a specific task or resolving a specific alert. It is a "work instruction" that focuses on execution.
* **Goal:** To automate or standardize routine technical procedures to reduce human error and save time.
* **Content:** * Specific CLI commands to run.
    * Configuration settings to verify.
    * Scripts to execute.
* **Example:** A runbook for "Resetting a Locked Admin Account" or "Patching a Linux Web Server."

## Key Differences

| Feature | Runbook | Playbook |
| :--- | :--- | :--- |
| **Scope** | Narrow and technical. | Broad and strategic. |
| **Goal** | Efficiently complete a routine task. | Effectively manage a complex scenario. |
| **Audience** | Technicians and System Administrators. | Incident Responders and Management. |
| **Example** | "Steps to reset a user's password." | "Steps to respond to a data breach." |

# Business & Supply Chain Agreements

## Business Agreements
**Definition:** Formal arrangements between organizations that define how they will interact, share data, or collaborate on projects.

### 1. MOU (Memorandum of Understanding)
* **Description:** A non-binding agreement that outlines the intent of two or more parties to work together. It establishes a "meeting of the minds."
* **Use Case:** Two companies exploring a potential partnership for a new software integration before signing a formal contract.

### 2. MOA (Memorandum of Agreement)
* **Description:** A more formal version of an MOU. While it can still be non-binding, it often contains specific terms, responsibilities, and conditional agreements.
* **Use Case:** A local government and a non-profit agreeing on how to manage a community center, detailing who pays for utilities and maintenance.

### 3. ISA (Interconnection Security Agreement)
* **Description:** A technical document that specifies the security requirements for connecting two different networks or systems.
* **Use Case:** A federal agency connecting its database to a private contractor's network; the ISA defines the encryption standards and technical controls required for the link.

### 4. BPA (Blanket Purchase Agreement)
* **Description:** A simplified method of filling repetitive needs for supplies or services by establishing "charge accounts" with qualified sources.
* **Use Case:** An IT department that regularly buys Dell monitors. Instead of a new contract for every order, they use a BPA to purchase them at a pre-negotiated price as needed.

### 5. NDA (Non-Disclosure Agreement)
* **Description:** A legal contract that prohibits parties from sharing sensitive information or trade secrets disclosed during their relationship.
* **Use Case:** An employer hiring a new developer who will have access to the company’s proprietary source code.

## Supply Chain Agreements
**Definition:** Documents that govern the relationship between a buyer and a seller/vendor, focusing on performance, expectations, and procurement.

### 1. SLA (Service Level Agreement)
* **Description:** A contract that defines the specific level of service expected from a vendor, often including "uptime" percentages and response times.
* **Use Case:** A cloud provider promising "99.9% uptime." If the service goes down for more than a few minutes a month, the SLA dictates the financial credit the customer receives.

### 2. MSA (Master Service Agreement)
* **Description:** An overarching contract that governs future transactions or future agreements. It settles general terms like payment, indemnification, and dispute resolution.
* **Use Case:** A consulting firm signs an MSA with a client so that every new project (Statement of Work) doesn't need a full legal review of the "fine print."

### 3. SOW (Statement of Work)
* **Description:** A document that specifies the exact work to be performed, including deliverables, timelines, and pricing for a specific project.
* **Use Case:** An IT project to migrate 500 mailboxes to Office 365. The SOW lists exactly which mailboxes are included and the deadline for completion.

### 4. RFQ (Request for Quote)
* **Description:** A document used to invite suppliers to bid on specific products or services where price is the main factor.
* **Use Case:** A company needs 1,000 standard CAT6 ethernet cables and wants to see which vendor can provide them for the lowest cost.

### 5. RFP (Request for Proposal)
* **Description:** A document used to solicit proposals where the solution is complex and factors other than price (like technical expertise or project plan) are evaluated.
* **Use Case:** A city government looking for a vendor to build a new municipal cybersecurity operations center (SOC).

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

# Virtual Private Networks (VPN)

## VPN Connectivity Types

### 1. Full Tunnel
* **Description:** All network traffic—including internet browsing and internal resources—is routed through the encrypted VPN tunnel.
* **Real-World Use Case:** A government contractor working from a coffee shop. By using a full tunnel, the organization ensures that even "public" web traffic is filtered by the corporate firewall and protected from local eavesdropping.
* **Benefit:** Maximum security and centralized monitoring of all data.

### 2. Split Tunnel
* **Description:** Only traffic destined for the internal corporate network is sent through the VPN tunnel. Regular internet traffic (like YouTube or Netflix) goes out through the user's local internet connection.
* **Real-World Use Case:** Remote employees using bandwidth-heavy video conferencing apps like Zoom. Split tunneling prevents the corporate network from being bogged down by non-work-related traffic.
* **Benefit:** Conserves corporate bandwidth and reduces latency for the user.

### 3. Always-On VPN
* **Description:** The VPN connection is automatically established as soon as the device has an internet connection, without requiring the user to manually log in or "connect."
* **Real-World Use Case:** Corporate-managed laptops. To maintain security compliance, the device is always "inside" the corporate perimeter, allowing IT to push updates and monitor the device regardless of its location.

## VPN Technologies & Protocols

### 1. GRE (Generic Routing Encapsulation)
* **Description:** A tunneling protocol that can encapsulate a wide variety of network layer protocols inside virtual point-to-point links. 
* **Security Note:** GRE by itself is **unencrypted**. It is frequently paired with **IPSec** to provide security.
* **Use Case:** Connecting two sites to pass routing information (like OSPF or EIGRP) that standard IPSec cannot handle alone.

### 2. PPTP (Point-to-Point Tunneling Protocol) - Port 1723
* **Description:** One of the oldest VPN protocols. It uses a control channel over TCP and a GRE tunnel to operate.
* **Security Note:** Now considered **obsolete and insecure** due to vulnerabilities in its authentication (MS-CHAPv2).
* **Status:** Avoid in modern environments.

### 3. L2TP/IPSec (Layer 2 Tunneling Protocol) - Port 1701
* **Description:** L2TP provides the "tunnel," but since it doesn't offer encryption, it is almost always paired with **IPSec** for security.
* **Use Case:** A common alternative for client-to-site VPNs when SSL VPNs are not used.

### 4. IKEv2/IPSec
* **Description:** A robust VPN protocol that excels at maintaining a connection when a user switches between networks (e.g., moving from Wi-Fi to 5G).
* **Benefit:** Extremely fast and stable; highly recommended for mobile device VPN clients.

### 5. SSL/TLS VPN - Port 443
* **Description:** Uses the standard web encryption (HTTPS) to create a VPN tunnel. It can be "clientless" (accessed via a web browser) or use a dedicated client (like AnyConnect).
* **Benefit:** Easily bypasses most firewalls since Port 443 is almost always open.

### 6. SSH Tunneling - Port 22
* **Description:** Using an SSH connection to "wrap" other protocols (like HTTP or VNC) to send them securely through an encrypted tunnel.
* **Real-World Use Case:** A developer securely accessing a database port on a remote server that is not exposed to the public internet.

# Network Hardening & Advanced Infrastructure

## Network Hardening Fundamentals
**Definition:** The process of securing a network by reducing its surface of vulnerability through configuration changes and policy enforcement.

### 1. Segmentation
* **Description:** Dividing a larger network into smaller, isolated sections (subnets or VLANs) to contain potential breaches.
* **Use Case:** Placing guest Wi-Fi on a separate VLAN from the corporate accounting servers to ensure a compromised guest device cannot "pivot" to sensitive data.

### 2. Device Hardening
* **Description:** Securing individual components (routers, switches, firewalls) by disabling unused services, changing default credentials, and updating firmware.
* **Real-World Example:** Disabling HTTP and Telnet on a core switch and requiring SSH and HTTPS for all administrative access.

### 3. Access Control
* **Description:** Implementing the principle of **Least Privilege** to ensure users and devices only have access to the specific resources required for their roles.


## Network Management Interfaces

### 1. In-Band Management
* **Definition:** Managing network devices through the same channels used for regular data traffic.
* **Risk:** If the network experiences a broadcast storm or a DoS attack, the administrator may lose access to the device to fix it.

### 2. Out-of-Band (OOB) Management
* **Definition:** Using a dedicated, physically or logically separate path for management traffic (e.g., a console port or a dedicated management VLAN).
* **Use Case:** Using a terminal server connected to the console ports of all rack equipment, allowing access even if the main data network is down.

### 3. Jump Server (Jump Box)
* **Definition:** A highly secured "intermediary" server that administrators must log into first before they can access other devices in a restricted network zone.
* **Use Case:** An admin connects via SSH to a Jump Server in the DMZ, and from there, initiates a second connection to a sensitive database server in the internal network.


## Advanced Network Structure

### 1. Deperimeterization
* **Definition:** The shift away from relying on a single "hard" outer boundary (firewall) to protect an internal network, acknowledging that the "perimeter" now extends to the cloud and mobile devices.

### 2. Software-Defined Networking (SDN)
**Definition:** An architecture that centralizes network control by decoupling the forwarding function from the control function.

* **Control Plane:** The "brains" of the network that makes decisions about where traffic is sent.
* **Data Plane (Forwarding Plane):** The "muscles" that actually move the packets based on the Control Plane's instructions.
* **Northbound API:** Interfaces used by the SDN Controller to communicate with "higher-level" applications and business logic.
* **Southbound API:** Interfaces (like OpenFlow) used by the Controller to send instructions down to the physical or virtual switches.

### 3. Microsegmentation
* **Definition:** A security technique that creates very granular zones in data centers and cloud environments to isolate workloads from one another, often down to the individual virtual machine level.

### 4. Zero Trust Architecture (ZTA)
**Definition:** A security model based on the principle of "Never Trust, Always Verify," where no user or device is trusted by default, even if they are inside the network.

* **Subject/System:** The entity (user, device, or app) requesting access.
* **Resource:** The target data or service being requested.
* **Policy Enforcement Point (PEP):** The gatekeeper (like a firewall or gateway) that actually permits or denies the connection.
* **Policy Engine (PE):** The component that makes the ultimate decision to grant access based on behavioral data and policy.
* **Policy Administrator (PA):** The component that executes the decision of the PE by communicating with the PEP to open or close the "gate."

### 5. SASE (Secure Access Service Edge)
* **Definition:** A cloud-based framework that combines network security functions (like FWaaS, CASB, and Zero Trust) with wide-area networking (SD-WAN) to support the dynamic secure access needs of organizations.
* **Real-World Use Case:** A remote workforce that accesses all corporate resources through a single cloud-native security provider, ensuring the same policy is applied whether they are at home or in the office.

# Network Hardening & Advanced Infrastructure

## Network Hardening Fundamentals
**Definition:** The process of securing a network by reducing its surface of vulnerability through configuration changes and policy enforcement.

### 1. Segmentation
* **Description:** Dividing a larger network into smaller, isolated sections (subnets or VLANs) to contain potential breaches.
* **Use Case:** Placing guest Wi-Fi on a separate VLAN from the corporate accounting servers to ensure a compromised guest device cannot "pivot" to sensitive data.

### 2. Device Hardening
* **Description:** Securing individual components (routers, switches, firewalls) by disabling unused services, changing default credentials, and updating firmware.
* **Real-World Example:** Disabling HTTP and Telnet on a core switch and requiring SSH and HTTPS for all administrative access.

### 3. Access Control
* **Description:** Implementing the principle of **Least Privilege** to ensure users and devices only have access to the specific resources required for their roles.

## Network Management Interfaces

### 1. In-Band Management
* **Definition:** Managing network devices through the same channels used for regular data traffic.
* **Risk:** If the network experiences a broadcast storm or a DoS attack, the administrator may lose access to the device to fix it.

### 2. Out-of-Band (OOB) Management
* **Definition:** Using a dedicated, physically or logically separate path for management traffic (e.g., a console port or a dedicated management VLAN).
* **Use Case:** Using a terminal server connected to the console ports of all rack equipment, allowing access even if the main data network is down.

### 3. Jump Server (Jump Box)
* **Definition:** A highly secured "intermediary" server that administrators must log into first before they can access other devices in a restricted network zone.
* **Use Case:** An admin connects via SSH to a Jump Server in the DMZ, and from there, initiates a second connection to a sensitive database server in the internal network.

## Advanced Network Structure

### 1. Deperimeterization
* **Definition:** The shift away from relying on a single "hard" outer boundary (firewall) to protect an internal network, acknowledging that the "perimeter" now extends to the cloud and mobile devices.

### 2. Software-Defined Networking (SDN)
**Definition:** An architecture that centralizes network control by decoupling the forwarding function from the control function.

* **Control Plane:** The "brains" of the network that makes decisions about where traffic is sent.
* **Data Plane (Forwarding Plane):** The "muscles" that actually move the packets based on the Control Plane's instructions.
* **Northbound API:** Interfaces used by the SDN Controller to communicate with "higher-level" applications and business logic.
* **Southbound API:** Interfaces (like OpenFlow) used by the Controller to send instructions down to the physical or virtual switches.

### 3. Microsegmentation
* **Definition:** A security technique that creates very granular zones in data centers and cloud environments to isolate workloads from one another, often down to the individual virtual machine level.

### 4. Zero Trust Architecture (ZTA)
**Definition:** A security model based on the principle of "Never Trust, Always Verify," where no user or device is trusted by default, even if they are inside the network.

* **Subject/System:** The entity (user, device, or app) requesting access.
* **Resource:** The target data or service being requested.
* **Policy Enforcement Point (PEP):** The gatekeeper (like a firewall or gateway) that actually permits or denies the connection.
* **Policy Engine (PE):** The component that makes the ultimate decision to grant access based on behavioral data and policy.
* **Policy Administrator (PA):** The component that executes the decision of the PE by communicating with the PEP to open or close the "gate."

### 5. SASE (Secure Access Service Edge)
* **Definition:** A cloud-based framework that combines network security functions (like FWaaS, CASB, and Zero Trust) with wide-area networking (SD-WAN) to support the dynamic secure access needs of organizations.
* **Real-World Use Case:** A remote workforce that accesses all corporate resources through a single cloud-native security provider, ensuring the same policy is applied whether they are at home or in the office.

# AAA Framework & Authentication Attributes

## The AAA Process
**Definition:** A framework for intelligently controlling access to computer resources, enforcing policies, auditing usage, and providing the information necessary to bill for services.

### 1. Identification
* **Definition:** The process where a user or system claims an identity.
* **Real-World Use Case:** Entering a **Username** into a login prompt or swiping an ID card. It is the "Hello, my name is..." phase.

### 2. Authentication
* **Definition:** The process of verifying the identity claimed during the identification phase.
* **Real-World Use Case:** Entering a **Password** or providing a **Fingerprint**. This proves that the "Subject" is truly who they say they are.

### 3. Authorization
* **Definition:** The process of granting or denying access to specific resources once the identity is verified.
* **Real-World Use Case:** After logging in, a user is allowed to **Read** a file but is denied permission to **Delete** it based on their job role.

### 4. Accounting
* **Definition:** The tracking of user activity and resource consumption while they are logged in.
* **Real-World Use Case:** Reviewing **Log Files** to see exactly what time a user accessed a database and what changes were made. This provides accountability and an audit trail.

## Authentication Attributes (Factors)
**Definition:** The different categories of evidence used to prove a user's identity. Using more than one category results in **Multi-Factor Authentication (MFA)**.

### 1. Something You Know (Knowledge Factor)
* **Definition:** Information that the user must remember.
* **Examples:** Passwords, PINs, or answers to security questions ("What was your first pet's name?").
* **Risk:** Can be easily shared, guessed, or stolen via social engineering.

### 2. Something You Have (Possession Factor)
* **Definition:** A physical or digital object that the user must physically possess.
* **Examples:** A **Smart Card**, a hardware token (like a YubiKey), or a One-Time Password (OTP) sent to a smartphone.
* **Risk:** The item can be physically stolen or cloned.

### 3. Something You Are (Inherence Factor)
* **Definition:** A unique physical or behavioral characteristic of the user (Biometrics).
* **Examples:** Fingerprints, Facial Recognition (FaceID), Retina scans, or Voice patterns.
* **Risk:** If biometric data is breached, it cannot be "changed" like a password.

# Passwordless Authentication & Secure Credentials

## Digital Credentials
**Definition:** A broad term for data that proves identity or authority in a digital environment, replacing the need for a manually entered password.

### 1. Static Code / Passphrase
* **Definition:** A long-term code or set of words that remains the same until manually changed.
* **Use Case:** A "Master Password" for a password manager or a recovery code for an account.
* **Security Note:** While stronger than a simple password, it is still a "Knowledge Factor" and vulnerable to theft.

### 2. Digital Certificate
* **Definition:** An electronic document used to prove the ownership of a public key. It is issued by a Trusted Certificate Authority (CA).
* **Real-World Use Case:** A corporate laptop automatically authenticating to the office Wi-Fi because it has a unique machine certificate installed in its TPM (Trusted Platform Module).

## One-Time Passwords (OTP)
**Definition:** A password that is valid for only one login session or transaction.

### 1. HOTP (HMAC-based One-Time Password)
* **Definition:** An OTP based on a counter. The code changes only when a specific action occurs (like pressing a button on a token).
* **Constraint:** If the button is pressed too many times without logging in, the token and the server can get "out of sync."

### 2. TOTP (Time-based One-Time Password)
* **Definition:** An OTP that is generated based on the current time. The code typically changes every 30 or 60 seconds.
* **Real-World Use Case:** Using the **Google Authenticator** or **Microsoft Authenticator** app to get a 6-digit code for a login.


## Physical Authentication Tools

### 1. Authentication Token (Soft vs. Hard)
* **Soft Token:** An app-based generator (like the ones mentioned in TOTP).
* **Hard Token:** A dedicated physical device that displays a rotating code on a small screen.

### 2. Security Key (FIDO2 / WebAuthn)
* **Definition:** A hardware device (like a **YubiKey**) that uses public-key cryptography to authenticate the user to a service.
* **Benefit:** Virtually immune to phishing because the key only communicates with the specific URL it was registered with.

### 3. Smart Card
* **Definition:** A physical card containing an embedded integrated circuit (chip) used for authentication and data storage.
* **Real-World Use Case:** The **CAC (Common Access Card)** used by the U.S. Department of Defense or **PIV cards** used by federal employees to log into workstations and sign emails.
# Biometric Error Types

### 1. Type 1 Error: False Rejection Rate (FRR)
* **Definition:** Occurs when a legitimate, authorized user is denied access by the biometric system. The system fails to recognize the "Subject" as themselves.
* **Impact:** This is primarily an **insult to the user** and a productivity issue. While it doesn't decrease security, it causes significant frustration and "help desk" calls.
* **Real-World Use Case:** You try to unlock your phone with your thumbprint, but because your hands are slightly damp, the phone refuses to unlock, forcing you to try again or use a PIN.

### 2. Type 2 Error: False Acceptance Rate (FAR)
* **Definition:** Occurs when an unauthorized person or an impostor is incorrectly identified as a valid user and granted access to the system.
* **Impact:** This is a **security breach**. This is the most dangerous type of error because it allows a threat actor to bypass authentication entirely.
* **Real-World Use Case:** A biometric door lock is poorly calibrated and allows a stranger to enter a secure data center because their facial structure was "close enough" to an authorized employee's profile.

## The Crossover Error Rate (CER)
**Definition:** The point where the False Rejection Rate and the False Acceptance Rate are equal. 

* **Significance:** The CER is the most important metric for comparing the overall accuracy of different biometric systems. 
* **The Goal:** A **lower CER** indicates a more accurate and reliable biometric system. Security administrators adjust the "sensitivity" of devices to find a balance that provides high security without causing too many false rejections.

# Trust & Identity Integration

## Attestation
**Definition:** A mechanism where a device proves its integrity and "health" to a remote system by providing a cryptographically signed report of its hardware and software state.

* **How it Works:** Usually involves a **TPM (Trusted Platform Module)**. The device sends a "quote" of its current configuration (boot loaders, OS kernel, firmware versions) to a verification server.
* **Real-World Use Case:** A "Health Check" for a laptop. If the attestation report shows the device has been tampered with or is running an outdated, insecure kernel, the network denies it access to sensitive data until it is remediated.
* **Benefit:** Ensures that you aren't just trusting a user, but also the physical health of the machine they are using.

## Single Sign-On (SSO)
**Definition:** An authentication scheme that allows a user to log in with a single set of credentials (username and password) to any of several related, yet independent, software systems.

* **How it Works:** Once authenticated to a central "Identity Provider" (IdP), the user receives a **Token**. When they try to access a different application, the application trusts that token rather than asking for a password again.
* **Real-World Use Case:** Logging into your corporate workstation and then being able to open your email, the HR portal, and the company's internal Wiki without ever seeing another login prompt.
* **Benefit:** Reduces "password fatigue" for users and provides a centralized point for IT to revoke access if an employee leaves the company.

## Federated Identities
**Definition:** An arrangement that can be made between two or more trust domains to allow users of these domains to access applications and services using the same digital identity.

* **How it Works:** It extends SSO beyond a single organization. It uses protocols like **SAML (Security Assertion Markup Language)** or **OIDC (OpenID Connect)** to pass "identity assertions" between different organizations.
* **Real-World Use Case:** "Log in with Google" or "Log in with LinkedIn" on a third-party website. The third-party site trusts Google to verify who you are, so you don't have to create a brand-new account on their system.
* **Benefit:** Simplifies user onboarding and allows organizations to collaborate securely without sharing their internal user databases.

# Authentication Protocols

## Point-to-Point Protocols (PPP)
**Definition:** Protocols originally designed to establish a direct connection between two nodes (like a computer and an ISP over a phone line or a VPN tunnel).

### 1. PAP (Password Authentication Protocol)
* **Description:** A legacy authentication method where the client sends the username and password to the server in **clear text**.
* **Status:** Obsolete and extremely insecure.
* **Risk:** Anyone sniffing the network traffic can easily capture the credentials.

### 2. CHAP (Challenge Handshake Authentication Protocol)
* **Description:** A more secure method that uses a "three-way handshake" and a shared secret. The server sends a "challenge" to the client; the client responds with a hash of the challenge and the password.
* **Benefit:** The actual password is never sent over the wire, protecting against eavesdropping.

## EAP (Extensible Authentication Protocol)
**Definition:** A framework (not a single protocol) used in wireless networks and point-to-point connections that allows for different authentication methods to be used.

### 1. EAP-TLS (EAP-Transport Layer Security)
* **Description:** One of the most secure versions of EAP. It requires **digital certificates** on both the client and the server for mutual authentication.
* **Real-World Use Case:** High-security corporate Wi-Fi (802.1X). Both the laptop and the network server must "prove" their identity to each other using certificates.
* **Benefit:** Extremely resistant to "Evil Twin" and credential-harvesting attacks.

### 2. EAP-TTLS (EAP-Tunneled Transport Layer Security)
* **Description:** Similar to EAP-TLS, but only the **server** requires a certificate. The client can authenticate using a simpler method (like a username and password) inside a secure TLS tunnel.
* **Benefit:** Easier to deploy than EAP-TLS because you don't have to manage certificates for every individual user device.

### 3. LEAP (Lightweight Extensible Authentication Protocol)
* **Description:** A Cisco-proprietary version of EAP developed to address security flaws in WEP. 
* **Status:** Deprecated. It is vulnerable to offline dictionary attacks.
* **Legacy Use Case:** Older Cisco wireless infrastructure.

### 4. EAP-FAST (EAP-Flexible Authentication via Secure Tunneling)
* **Description:** A Cisco-designed replacement for LEAP. It establishes a secure tunnel using a **PAC (Protected Access Credential)** rather than relying on certificates.
* **Benefit:** Provides a high level of security without the administrative overhead of a full PKI (Public Key Infrastructure) certificate rollout.

# Centralized AAA Protocols

### 1. RADIUS (Remote Authentication Dial-In User Service)
* **Description:** An open-standard, UDP-based protocol used to manage network access. It is the most common protocol used for 802.1X wireless authentication.
* **Mechanism:** It combines **Authentication** and **Authorization** into a single step, while keeping **Accounting** separate. It only encrypts the *password* in the packet; the rest of the packet (including the username) is sent in clear text.
* **Real-World Use Case:** A company using a RADIUS server (like Microsoft NPS or FreeRADIUS) to allow employees to log into the office Wi-Fi using their Active Directory credentials.
* **Ports:** UDP 1812 (Authentication/Authorization) and UDP 1813 (Accounting).


### 2. TACACS+ (Terminal Access Controller Access-Control System Plus)
* **Description:** A Cisco-proprietary (though widely supported) TCP-based protocol designed for device administration.
* **Mechanism:** Unlike RADIUS, it strictly separates **Authentication**, **Authorization**, and **Accounting** into three distinct processes. Most importantly, it **encrypts the entire payload** of the packet, providing better security for administrative sessions.
* **Real-World Use Case:** A Network Engineer logging into a core router via SSH. TACACS+ allows the organization to control exactly which commands the engineer is allowed to run (Authorization) and logs every command they type (Accounting).
* **Port:** TCP 49.

### 3. Diameter
* **Description:** The modern successor to RADIUS, designed to overcome its limitations. It uses TCP or SCTP for reliable transport and provides much better error handling and scalability.
* **Mechanism:** It supports "Capability Exchange," allowing it to negotiate features with other nodes. It is widely used in cellular networks (LTE/5G) and large-scale ISP environments.
* **Benefit:** Provides better security through mandatory IPsec or TLS support and is designed to handle the complex roaming requirements of modern mobile networks.
* **Port:** TCP/SCTP 3868.

### 4. Kerberos
* **Description:** A ticket-based authentication protocol used to prove identity over non-secure networks. It is the default authentication protocol for Windows Active Directory.
* **Mechanism:** Uses a trusted third party called a **Key Distribution Center (KDC)**. Instead of sending passwords, it issues "Tickets." A **Ticket Granting Ticket (TGT)** allows a user to request **Service Tickets** for specific resources.
* **Real-World Use Case:** A user logging into their Windows workstation and automatically gaining access to a shared file server or an email server without being prompted for credentials again (Single Sign-On).
* **Port:** TCP/UDP 88.

# Modern Identity & Authorization Protocols

## SAML (Security Assertion Markup Language)
* **Definition:** An XML-based open standard for exchanging authentication and authorization data between an **Identity Provider (IdP)** and a **Service Provider (SP)**.
* **Use Case:** Logging into a web application (like Salesforce or Zoom) using your company’s Active Directory credentials.
* **Mechanism:** It uses a "trust relationship." The user authenticates with the IdP, which then hands the user a digital "passport" (SAML Assertion) to show to the SP.

## OAuth 2.0 and OpenID Connect (OIDC)
* **OAuth 2.0 (Authorization):** A framework that allows a third-party application to access a user's data without ever seeing their password (e.g., giving a printing app permission to access your Google Drive files).
* **OpenID Connect (Authentication):** A simple identity layer built on top of the OAuth 2.0 protocol. It allows clients to verify the identity of the end-user based on the authentication performed by an Authorization Server.

## The Four Roles of OAuth/OIDC
To understand how these work, you have to look at the four specific players involved in the transaction:

### 1. Resource Owner (The User)
* **Definition:** The person who owns the data and has the power to grant access to it.
* **Example:** You, the user, wanting to share your contact list with a new social app.

### 2. Client Application
* **Definition:** The application making the request to access the user's data.
* **Example:** A mobile app, a website, or a background service.

### 3. Resource Server
* **Definition:** The server hosting the protected user data (the "Resource").
* **Example:** Google Contacts, a Dropbox folder, or a GitHub repository.

### 4. Authorization Server
* **Definition:** The server that authenticates the Resource Owner and issues **Access Tokens** to the Client Application after getting the user's consent.
* **Example:** The Google or Microsoft "Sign-In" screen that asks: *"Do you want to allow [App] to access your files?"*

## Comparison: SAML vs. OAuth/OIDC

| Feature | SAML | OAuth / OIDC |
| :--- | :--- | :--- |
| **Format** | XML | JSON / Tokens |
| **Primary Goal** | Enterprise SSO | Web/Mobile App Authorization |
| **Complexity** | High (Harder to configure) | Low (Developer-friendly) |
| **Transport** | Browser-heavy (HTTP POST) | API-centric |

# Access Control Models & Permission Types

## Access Control Models

### 1. Discretionary Access Control (DAC)
* **Definition:** A model where the **owner** of the resource (file, folder, or object) has total control over who is granted access and what privileges they have.
* **Real-World Use Case:** A user on a Windows or Linux machine creating a document and then right-clicking it to "Share" it with a specific colleague.
* **Security Note:** This is the most flexible model but the least secure, as it relies on individual users to maintain security.

### 2. Mandatory Access Control (MAC)
* **Definition:** A strict, non-discretionary model where access is based on **security labels** (e.g., Secret, Top Secret) and "clearance" levels. Only the system administrator can define access.
* **Real-World Use Case:** Military or high-security government databases where a user cannot share a "Top Secret" file with someone else, even if they created it.
* **Benefit:** Prevents data from being shared or leaked by end-users.

### 3. Role-Based Access Control (RBAC)
* **Definition:** Access is granted based on the user's **job function** or role within the organization rather than their individual identity.
* **Real-World Use Case:** A "Manager" role has access to payroll data, while a "Technician" role does not. When a new employee is hired as a Technician, they are simply added to that group to receive the correct permissions.
* **Benefit:** Simplifies administration in large organizations.

### 4. Rule-Based Access Control (RBAC/RuBAC)
* **Definition:** Access is granted or denied based on a set of **predefined rules** or conditions, regardless of the user's identity.
* **Real-World Use Case:** A firewall rule that says "Allow all traffic from the internal network to the internet on Port 443" or a router ACL.
* **Mechanism:** Often follows an "If/Then" logic.

### 5. Attribute-Based Access Control (ABAC)
* **Definition:** The most flexible and complex model, where access is granted based on a combination of **attributes** (User attributes, Resource attributes, and Environmental conditions).
* **Real-World Use Case:** "Allow the Manager to access the Financial Database (Resource) only if they are using a Corporate Laptop (Device) and are connecting from the Office (Location) during Business Hours (Time)."

## Permission Types

### 1. Explicit Allow
* **Definition:** A permission that is specifically granted to a user or group.
* **Example:** Manually adding "Sam Lucas" to have "Read" access to a folder.

### 2. Explicit Deny
* **Definition:** A permission that is specifically set to block access. In almost all systems, an **Explicit Deny overrides an Explicit Allow**.
* **Example:** Blocking a specific user from a folder even if they are part of a group that normally has access.

### 3. Inherited Allow
* **Definition:** A permission that a user receives because it was set on a **parent object** (like a folder) and passed down to the child objects (like files).
* **Example:** If you have access to the "Projects" folder, you automatically get access to the "2026_Report.docx" file inside it.

### 4. Inherited Deny
* **Definition:** A restriction that is passed down from a parent object to all its children.
* **Example:** If the "Private" folder is set to deny access to the "Contractors" group, every file inside that folder will also deny them access by default.

# Identity Lifecycle & Account Management

## The Identity Lifecycle
**Definition:** The formal process of managing a digital identity through its various stages within an organization.

### 1. Provisioning (Onboarding)
* **Definition:** The creation of a new user account and the granting of initial permissions based on the user's role.
* **Real-World Use Case:** A new hire starts in the HR department. The IT team creates their Active Directory account and automatically maps them to the "HR-Staff" folder and the payroll software.

### 2. Maintenance (Modification)
* **Definition:** Updating an account throughout its life as the user's status changes (e.g., name changes, department transfers, or temporary access grants).
* **Real-World Use Case:** An employee is promoted to Manager. Their account is moved to a new Organizational Unit (OU) to receive elevated "Privileged User" permissions.

### 3. Deprovisioning (Offboarding)
* **Definition:** The process of disabling or deleting an account and revoking all access when a user leaves the organization.
* **Security Note:** This must happen immediately to prevent **"Orphaned Accounts"** that disgruntled former employees or attackers could use to gain back-door access.

## Account Types

### 1. User Account
* **Description:** A standard account used by an individual employee for daily tasks (email, document editing).
* **Permission Level:** Follows the principle of **Least Privilege**.

### 2. Privileged Account
* **Description:** Accounts with elevated permissions, such as System Administrators, Network Admins, or Database Admins.
* **Security Note:** These accounts should **never** be used for daily tasks like web browsing or checking personal email, as they are high-value targets for attackers.

### 3. Shared / Generic Account
* **Description:** An account used by more than one person (e.g., `guest`, `reception`, or `training`).
* **Security Risk:** Extremely dangerous because they lack **Accountability**. If a file is deleted by a shared account, you cannot prove which specific person did it.

### 4. Guest Account
* **Description:** A restricted account for temporary users (contractors or visitors).
* **Best Practice:** Should be disabled by default and have a strictly limited lifespan.

### 5. Service Account
* **Description:** An account used by an application or a service (like a backup tool or an antivirus scanner) to perform automated tasks without human intervention.
* **Real-World Use Case:** An "SQL-Service" account that allows the web server to pull data from the database. These accounts often have passwords that **never expire** to prevent breaking the application.

# Identity Proofing Methods

### 1. Static KBA (Knowledge-Based Authentication)
* **Definition:** Verification based on "shared secrets" that a user previously provided to the system.
* **Mechanism:** The user selects from a list of pre-set security questions during account setup.
* **Real-World Use Case:** "What was the name of your first grade teacher?" or "What is your mother's maiden name?"
* **Security Note:** This is considered **weak** today because much of this information can be found via social media or public records (OSINT).

### 2. Dynamic KBA
* **Definition:** Verification based on questions generated in real-time from third-party data sources (like credit bureaus or government records) that the user has not pre-configured.
* **Real-World Use Case:** When applying for a loan online, the system asks: *"Which of the following addresses have you lived at in the last 10 years?"* or *"What was the monthly payment on your 2018 auto loan?"*
* **Benefit:** Much harder to bypass than static KBA because the "answers" aren't stored in a single user profile; they are pulled from a vast web of public and private data.

### 3. Out-of-Band (OOB) Proofing
* **Definition:** Verifying an identity using a communication channel that is completely separate from the one being used to request access.
* **Mechanism:** If you are signing up for a service on a laptop, the "proof" is sent to a different device or medium (like a physical piece of mail or a voice call to a registered landline).
* **Real-World Use Case:** A bank mailing a physical letter containing a unique activation code to a customer's verified home address. The customer must then log in and enter that code to "proof" they actually live at that location.
* **Benefit:** Provides a high level of assurance because it requires the user to have physical access to a secondary, pre-verified communication method.

# Active Directory Management

## 1. Active Directory Groups
**Definition:** Collections of user accounts, computer accounts, and other groups that can be managed as a single unit.

### Security Groups
* **Definition:** Used to assign permissions to shared resources (files, folders, printers).
* **Real-World Use Case:** Creating a group called "Accounting_FullAccess" and adding all accounting employees to it. You then give that *group* permission to the Payroll folder.
* **Benefit:** When a new person joins the department, you simply add them to the group instead of manually updating folder permissions.

### Distribution Groups
* **Definition:** Used solely for email distribution lists. They **cannot** be used to assign permissions to resources.
* **Real-World Use Case:** An "All-Staff" email list. Sending an email to this group forwards it to every member, but you cannot use "All-Staff" to secure a file share.

### Organizational Unit (OU)
* **Definition:** A container within a domain used to organize objects (users, computers, groups) and, most importantly, to **apply Group Policy Objects (GPOs)**.
* **Real-World Use Case:** Creating an OU for "Chesapeake_Laptops" and another for "VirginiaBeach_Laptops." This allows you to apply different security settings based on the physical location of the devices.

## 2. Group Scopes
**Definition:** Determines the extent to which a group is applied within a forest or domain.

| Scope | Definition / Usage |
| :--- | :--- |
| **Domain Local** | Used to assign permissions to resources (like a printer) within a **single domain**. |
| **Global** | Used to organize users who share a similar function. These can be used in any domain in the forest. |
| **Universal** | Used to grant permissions to similar resources across **multiple domains** in a forest. |

## 3. Group Policy Objects (GPO)
**Definition:** A feature of Active Directory that allows administrators to manage the working environment of user and computer accounts centrally.

### Scripts
* **Definition:** Allows admins to run specific scripts (PowerShell, VBScript, or Batch) at **Startup/Shutdown** for computers or **Logon/Logoff** for users.
* **Use Case:** Automatically mapping a network drive (e.g., the S: drive) every time a user logs in.

### Software Settings
* **Definition:** Used to centrally manage software installation, updates, or removals across the network.
* **Use Case:** Automatically "pushing" the latest version of a VPN client or Google Chrome to every laptop in the "Chesapeake" OU.

### Account Policies
* **Definition:** Defines security settings related to user accounts, specifically **Password Policies** and **Account Lockout Policies**.
* **Use Case:** Enforcing a rule that passwords must be at least 14 characters long and users are locked out after 5 failed attempts.

### Restricted Groups
* **Definition:** A policy that allows an administrator to control who belongs to a sensitive local group on a workstation or server (like the local **Administrators** group).
* **Benefit:** Prevents "Privilege Creep" by automatically removing any unauthorized users added to the local admin group by a user.

### Folder Redirection
* **Definition:** Redirects the path of known user folders (like "Documents" or "Desktop") to a centralized network location.
* **Benefit:** If a user’s laptop hard drive fails, their files are safe because they were actually being saved to a secure server in the data center.

### Administrative Templates (.admx)
* **Definition:** Registry-based settings that provide a graphical interface for configuring thousands of OS and application settings.
* **Real-World Use Case:** Using a template to disable the use of USB flash drives or to set the company logo as the mandatory desktop wallpaper for all employees.

# The Group Policy Hierarchy (LSDOU)

**Definition:** When multiple GPOs are configured, Windows processes them in a specific order. The **last policy applied wins** (overwrites previous settings), unless "Enforcement" is turned on.

### 1. Local GPO
* **Definition:** Settings stored directly on the individual computer. These apply to everyone who logs into that specific machine, regardless of the domain.
* **Processing Order:** **1st** (First applied, easiest to overwrite).
* **Real-World Use Case:** A standalone computer in a lab that isn't joined to a domain but needs a specific banner message at login.

### 2. Site GPO
* **Definition:** GPOs linked to a physical "Site" (a collection of IP subnets) in Active Directory.
* **Processing Order:** **2nd**.
* **Real-World Use Case:** A company with offices in **Chesapeake** and **Virginia Beach**. You might use a Site GPO to ensure computers in the Chesapeake office connect to the local printer in that building.

### 3. Domain GPO
* **Definition:** GPOs linked at the very top of the domain. These affect every user and computer account in the entire domain.
* **Processing Order:** **3rd**.
* **Real-World Use Case:** Enforcing a **Password Policy** (e.g., 14 characters minimum) that must be identical for every single employee in the organization.

### 4. Organizational Unit (OU) GPO
* **Definition:** GPOs linked to a specific OU. This is the most common way to manage settings for specific departments.
* **Processing Order:** **4th**.
* **Real-World Use Case:** Linking a GPO to the "Marketing" OU that allows them to use specialized design software, while the "Accounting" OU remains restricted.

### 5. Child OU GPO
* **Definition:** GPOs linked to a sub-OU nested inside a parent OU. 
* **Processing Order:** **5th** (Last applied, highest precedence).
* **Real-World Use Case:** You have a parent OU for "IT Department" and a Child OU for "IT Admins." You apply a general policy to the parent, but use the Child OU GPO to grant the Admins extra tools or access that the rest of the department doesn't get.

## Important GPO Override Concepts

* **Inheritance:** By default, settings from the Domain or Parent OU "flow down" to the Child OUs.
* **Block Inheritance:** An administrator can stop parent GPOs from reaching a Child OU. (Useful for highly sensitive or "exception" groups).
* **Enforced (No Override):** A setting at a higher level (like the Domain) can be "Enforced," meaning it will apply even if a Child OU tries to block it or change it.
* **Loopback Processing:** A special mode used for kiosks or lab computers where the **Computer's** GPOs take priority over the **User's** GPOs.

# Host Attack Surfaces & Malware Analysis

## 1. Host Attack Surfaces
**Definition:** The sum total of all points where an unauthorized user can try to enter data to or extract data from an environment.

* **Applications:** Third-party software (browsers, office suites) that may have coding flaws or "Zero-Day" vulnerabilities.
* **Operating System Services:** Background processes (like Print Spooler or Remote Registry) that run with high privileges and can be exploited.
* **Firmware:** The low-level software programmed into hardware (BIOS/UEFI). Attacks here are persistent even if the OS is reinstalled.
* **Drivers:** Software that allows the OS to communicate with hardware. Malicious or "signed" but vulnerable drivers can grant kernel-level access.
* **Hardware Interfaces:** Physical entry points like USB ports, Thunderbolt, or even DMA (Direct Memory Access) attacks via expansion cards.


## 2. Software Vulnerabilities & Risks

* **Malware:** Malicious software designed to infiltrate or damage a computer system.
* **Open Service Ports:** Unnecessary ports (like Port 21 for FTP or Port 23 for Telnet) left open, providing a doorway for attackers.
* **Unpatched Software:** Known vulnerabilities (CVEs) that have fixes available but haven't been applied by the administrator.
* **Unauthorized Systems/Software:** "Shadow IT" where users install their own apps or bring their own devices (BYOD) without security oversight.

## 3. Malware Types
**Definition:** The "delivery vehicle" or method used to infect a system.

| Type | Description |
| :--- | :--- |
| **Virus** | Malicious code that requires **human interaction** (opening a file) to replicate and spread. |
| **Worm** | **Self-replicating** malware that spreads across a network automatically without human intervention. |
| **Trojan** | Malicious software disguised as a legitimate or harmless program (e.g., a "free" game). |
| **Bloatware / Grayware** | Unwanted software pre-installed on devices that consumes resources or tracks user behavior without being "malicious" in the traditional sense. |
| **Drive-by-Download** | Malware that installs automatically when a user simply visits a compromised website, often exploiting browser vulnerabilities. |
| **Logic Bomb** | Malicious code that stays dormant until a specific condition is met (e.g., a specific date or a user being deleted from payroll). |
| **Removable Device** | Malware spread via USB sticks or external drives (e.g., the Stuxnet worm). |

## 4. Malware Payloads
**Definition:** The actual "harmful" action the malware performs once it has successfully infected the host.

* **Backdoor:** A secret way to bypass normal authentication, allowing an attacker to regain access later.
* **Command and Control (C2):** The centralized infrastructure (server) used by attackers to send instructions to infected hosts.
* **Botnet:** A collection of "zombie" computers controlled by a C2 server, often used for DDoS attacks or spamming.
* **Ransomware:** Encrypts the victim's files and demands payment (usually in cryptocurrency) for the decryption key.
* **Spyware / Keylogger:** Secretly records user activity, keystrokes (to steal passwords), and screenshots.
* **Adware:** Automatically displays or downloads advertising material, often slowing down the system.

## 5. How Malware Hides (Evasion Techniques)

### Polymorphic Malware
* **Definition:** Malware that constantly changes its own code (its "signature") every time it replicates to evade traditional antivirus detection.
* **Analogy:** A criminal who gets a different face-lift and new fingerprints after every crime.

### Stealth Malware
* **Definition:** Malware that actively hides its presence by intercepting OS requests. For example, it might report a file's size is "0 bytes" when the AV tries to scan it.

### Fileless Malware
* **Definition:** Malware that exists only in **RAM (System Memory)** and uses legitimate tools (like PowerShell or WMI) to carry out attacks.
* **Benefit to Attacker:** It leaves no trace on the hard drive, making it invisible to standard file-based scanners.

### Rootkit
* **Definition:** A collection of tools that grants an attacker administrative (root) access while hiding their presence from the OS and security tools.
* **Real-World Impact:** Often replaces core OS files with "poisoned" versions that hide the attacker's processes and network connections.

# Virtualization, Cloud, and Operational Technology

## 1. Virtualized Architecture
**Definition:** The process of creating a software-based (virtual) representation of something, such as virtual applications, servers, storage, and networks.

### Type 1 Hypervisor (Bare Metal)
* **Description:** The hypervisor software runs directly on the host's hardware to manage guest operating systems.
* **Real-World Use Case:** Enterprise data centers using **VMware ESXi** or **Microsoft Hyper-V** on physical rack servers.
* **Benefit:** High performance and efficiency since there is no middle-man OS.

### Type 2 Hypervisor (Hosted)
* **Description:** The hypervisor runs as an application on top of an existing operating system (like Windows or macOS).
* **Real-World Use Case:** A developer using **Oracle VirtualBox** or **VMware Workstation** on their laptop to test a Linux distribution.
* **Benefit:** Easy to set up and use for testing or lab environments.

### Containers
* **Description:** A lightweight form of virtualization that packages an application and its dependencies together. Unlike VMs, containers share the host's OS kernel.
* **Real-World Use Case:** Using **Docker** or **Kubernetes** to deploy microservices that start up in seconds and use very little memory.

### VDI (Virtual Desktop Infrastructure)
* **Description:** Hosting a desktop operating system within a virtual machine on a centralized server.
* **Real-World Use Case:** A call center where employees use "Thin Clients" to log into a virtual Windows desktop hosted in the company data center.

## 2. Virtual Machine Vulnerabilities

### VM Hopping
* **Definition:** An attack where a threat actor gains access to one virtual machine and then manages to "hop" or pivot to another VM sharing the same physical host.
* **Risk:** If a public-facing web server VM is compromised, the attacker might try to hop to a database VM on the same hardware.

### VM Escape
* **Definition:** The most dangerous VM vulnerability, where an attacker breaks out of the guest VM and gains access to the **Hypervisor** or the physical host itself.
* **Mitigation:** Keeping hypervisors patched and using "Sandboxing" techniques.

## 3. Operational Technologies (OT)
**Definition:** Hardware and software that detects or causes a change through the direct monitoring and/or control of physical devices.

* **ICS (Industrial Control Systems):** Used in utilities and manufacturing. Includes **SCADA** (Supervisory Control and Data Acquisition) for large-scale processes like power grids.
* **BAS (Building Automation Systems):** Centralized control of a building's heating, ventilation, air conditioning (HVAC), lighting, and security systems.
* **Vehicle Control:** Embedded systems within cars or drones that manage engine timing, braking (ABS), and autonomous navigation.
* **IoT (Internet of Things):** Small, internet-connected devices like smart thermostats, cameras, or light bulbs. Often lack robust security features.

## 4. Cloud Service Models (The "Shared Responsibility" Model)

| Model | Definition | You Manage... | Vendor Manages... |
| :--- | :--- | :--- | :--- |
| **IaaS** | Infrastructure as a Service | OS, Apps, Data, Runtime | Servers, Storage, Networking |
| **PaaS** | Platform as a Service | Your Applications & Data | OS, Middleware, Hardware |
| **SaaS** | Software as a Service | Just your user settings | Everything (The whole app) |

### Real-World Examples:
* **IaaS:** Spinning up a virtual server in **Microsoft Azure** or **AWS EC2**.
* **PaaS:** Deploying code to **Google App Engine** or **AWS Elastic Beanstalk** without worrying about the underlying OS.
* **SaaS:** Using **Microsoft 365**, **Salesforce**, or **Gmail**.

# Cloud Deployment Models

**Definition:** A configuration of environmental parameters such as the storage size, accessibility, and proprietorship of the infrastructure.

### 1. Public Cloud
* **Description:** The cloud infrastructure is made available to the general public or a large industry group and is owned by an organization selling cloud services.
* **Real-World Use Case:** A startup using **Microsoft Azure** or **AWS** to host their website. They share the same physical hardware with thousands of other customers (multi-tenancy), though their data is logically isolated.
* **Benefit:** High scalability and a "pay-as-you-go" cost model with no hardware to maintain.


### 2. Private Cloud
* **Description:** The cloud infrastructure is operated solely for a single organization. It may be managed by the organization or a third party and may exist on-premises or off-premises.
* **Real-World Use Case:** A large bank that builds its own data center using **OpenStack** or **VMware Cloud Foundation**. Only the bank’s employees and internal applications can access these resources.
* **Benefit:** Maximum control, security, and data sovereignty; ideal for strict regulatory compliance.

### 3. Community Cloud
* **Description:** The infrastructure is shared by several organizations that have shared concerns (e.g., mission, security requirements, policy, and compliance considerations).
* **Real-World Use Case:** Several local police departments in **Hampton Roads** sharing a specialized cloud environment to host a joint criminal database. They split the costs and ensure the environment meets specific law enforcement security standards.
* **Benefit:** Shared costs and collaborative security tailored to a specific vertical or industry.


### 4. Hybrid Cloud
* **Description:** A composition of two or more distinct cloud infrastructures (Private, Community, or Public) that remain unique entities but are bound together by standardized technology.
* **Real-World Use Case:** A company that keeps its sensitive customer database on a **Private Cloud** (on-premises) for security but uses a **Public Cloud** (like Azure) to handle web traffic "bursts" during a high-volume sale.
* **Benefit:** Provides the "best of both worlds"—flexibility of the public cloud with the security of the private cloud.

# Information Life Cycle & Data States

## 1. The Information Life Cycle
**Definition:** The entire period of time that a piece of information exists, from its initial creation to its final disposal.

### Creation / Acquisition
* **Definition:** The phase where data is first generated (e.g., typing a document) or collected from an external source (e.g., a customer filling out a web form).
* **Security Focus:** Classification. This is the best time to tag data as "Public," "Internal," or "Confidential."

### Use / Storage
* **Definition:** The phase where data is actively being used by employees to perform tasks or is stored on a hard drive, server, or cloud bucket for future use.
* **Security Focus:** Access control and encryption. Ensuring only authorized users can see or modify the data.

### Retention / Archival
* **Definition:** Data that is no longer needed for daily operations but must be kept for legal, regulatory, or historical reasons.
* **Security Focus:** Integrity and long-term availability. Moving data to cheaper, "cold" storage (like Azure Archive Storage) while ensuring it remains uncorrupted.

### Wiping / Disposal
* **Definition:** The final phase where data is permanently destroyed so it can never be recovered.
* **Security Focus:** Sanitization. Using methods like **Purging**, **Degaussing**, or **Physical Destruction** (shredding drives) to prevent data remanence.


## 2. States of Data
**Definition:** The different modes in which data exists within a network. Each state requires a specific type of protection.

### Data in Motion / Transit
* **Definition:** Data that is currently traveling over a network (e.g., an email being sent or a file being uploaded to the cloud).
* **Primary Protection:** **TLS/SSL**, **VPNs**, and **IPsec**. We protect this data using **Transport Encryption** to prevent sniffing (Man-in-the-Middle attacks).

### Data at Rest
* **Definition:** Data that is physically stored on a persistent storage medium (e.g., a hard drive, a USB stick, or a database).
* **Primary Protection:** **Full Disk Encryption (FDE)**, **AES-256**, and **Database Encryption**. We protect this data so that if the physical drive is stolen, the data remains unreadable.

### Data in Use / Data in Processing
* **Definition:** Data that is currently loaded into **System Memory (RAM)**, CPU caches, or registers and is being actively acted upon by an application.
* **Primary Protection:** **Address Space Layout Randomization (ASLR)**, **Process Isolation**, and **Trusted Execution Environments (TEE)**.
* **Security Note:** This is the most difficult state to protect because the data must be "decrypted" in RAM for the CPU to read it.
