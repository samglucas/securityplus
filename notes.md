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

# Data Classification Levels

**Definition:** The process of assigning a level of sensitivity to data to determine the appropriate security controls, handling procedures, and access requirements.

### 1. Top Secret
* **Description:** The highest level of classification. Disclosure of this information would cause **exceptionally grave damage** to national security or the organization.
* **Access Requirement:** Requires the highest level of security clearance and a strict "Need to Know" basis.
* **Real-World Use Case:** Information about active intelligence sources, nuclear programs, or highly sensitive strategic defense plans.

### 2. Secret
* **Description:** Information that, if disclosed, would cause **serious damage** to national security or the organization.
* **Access Requirement:** Requires a formal security clearance and authorized access.
* **Real-World Use Case:** Significant military plans, technical descriptions of advanced weapon systems, or internal investigative reports.


### 3. Confidential
* **Description:** Information that, if disclosed, would cause **damage** or be prejudicial to the interests of the organization or national security. This is often the lowest level of "classified" data.
* **Access Requirement:** Requires authorization and is typically restricted to a specific group or department.
* **Real-World Use Case:** Personnel files, internal memos regarding sensitive business negotiations, or basic technical manuals for restricted equipment.

### 4. Unclassified
* **Description:** Data that does not meet the criteria for any of the higher levels of classification. While it is not "secret," it may still be subject to controls (like "For Official Use Only" or FOUO).
* **Access Requirement:** Generally available to the public or all employees, though internal distribution may still be restricted.
* **Real-World Use Case:** Public press releases, standard operating procedures (SOPs), and general administrative information.

## Data Labeling and Handling

* **Labeling:** Every document or file must be clearly marked with its classification level (often in the header and footer).
* **Storage:** Top Secret data might require a GSA-approved safe or a SCIF (Sensitive Compartmented Information Facility), while Unclassified data can be stored on standard encrypted drives.
* **Destruction:** Higher classification levels require stricter destruction methods, such as cross-cut shredding, pulping, or degaussing.

# Data Types, Sovereignty, and Controls

## 1. Data Types & Intellectual Property (IP)
**Definition:** Categories of information that require specific legal protections or handling due to their value or sensitivity.

* **Copyright:** Legal protection for "original works of authorship," such as software code, training manuals, and videos. It protects the *expression* of an idea, not the idea itself.
* **Patent:** A government grant giving an inventor exclusive rights to an invention (a process, machine, or manufacture) for a limited time.
* **Trade Secret:** Proprietary information that provides a competitive edge and is kept confidential (e.g., the Coca-Cola formula or a specific search algorithm).
* **Financial Information:** Sensitive data related to an organization's monetary assets, tax records, or credit card data (PCI DSS).
* **Legal Information:** Data subject to attorney-client privilege, regulatory filings, or ongoing litigation records.
* **Private Data:** Any information that can identify an individual (PII), such as SSNs, home addresses, or medical records (PHI).

## 2. Data Sovereignty
* **Definition:** The concept that digital data is subject to the **laws and regulations of the country** in which it is physically located.
* **Real-World Impact:** If a company in **Virginia** stores customer data in a data center in Germany, that data must comply with the EU's GDPR, regardless of where the company is headquartered.

## 3. Data Policies
**Definition:** High-level frameworks that dictate how an organization manages its information assets.

* **Classification:** The process of labeling data (Top Secret, Confidential, etc.) to determine its level of protection.
* **Ownership:** Identifying the "Data Owner" (usually a senior executive) who is ultimately responsible for the security and use of a specific data set.
* **Governance:** The overall management of data availability, usability, integrity, and security based on internal standards and policies.
* **Retention:** Defining how long data must be kept (e.g., "7 years for tax records") before it can be destroyed.
* **Disposal:** Outlining the approved methods for destroying data (shredding, degaussing, or wiping) once the retention period ends.

## 4. Technical & Operational Data Controls
**Definition:** The specific tools and methods used to enforce the data policies mentioned above.

### Access & Network Controls
* **Access Control:** Using permissions (ACLs) to ensure only authorized users can view or edit data.
* **Segmentation:** Dividing a network into smaller zones to prevent an attacker from moving laterally between sensitive data sets.
* **Geographic Restrictions:** Using **Geofencing** or **IP-blocking** to prevent data access from specific high-risk countries.

### Data Integrity & Protection
* **Labeling and Tagging:** Applying digital "metadata" tags to files so security tools (like DLP) can identify and protect sensitive info automatically.
* **Encryption:** Scrambling data so it is unreadable without a key. Used for **Data at Rest** and **Data in Motion**.
* **Hashing:** Creating a unique digital "fingerprint" of a file to verify its **Integrity**. If one bit changes, the hash changes.
* **Obfuscation:** Making data difficult for humans to understand (e.g., masking a credit card number: `****-****-****-1234`).
* **Digital Rights Management (DRM):** Tools that control how a user can use a file (e.g., preventing a user from printing or forwarding a sensitive email).

### Data Loss Prevention (DLP)
* **Definition:** Software that monitors for and prevents the unauthorized transfer of sensitive data outside the organization.
* **Example:** A DLP agent on a laptop blocks an employee from uploading a "Confidential" spreadsheet to a personal Dropbox account.

# Privacy, Hardware Security, and Data Destruction

## 1. Privacy-Enhancing Techniques (PETs)
**Definition:** Technical methods used to protect personal data by reducing the linkability between the data and the individual.

* **Anonymization:** Permanently removing all personally identifiable information (PII) so the individual cannot be re-identified. This process is irreversible.
* **Pseudo-Anonymization:** Replacing private identifiers with "pseudonyms" (fake identifiers). Unlike anonymization, this is **reversible** if you have access to the original mapping key.
* **Tokenization:** Replacing sensitive data (like a credit card number) with a non-sensitive equivalent called a "token." The actual data is stored in a secure "vault," and the token is used for transactions.
* **Data Scrubbing:** The process of removing or modifying specific data elements (like names or addresses) from a dataset to protect privacy before sharing it for research or testing.
* **Data Masking:** Hiding original data with modified content (e.g., showing only the last four digits of a Social Security Number: `XXX-XX-1234`).

## 2. Non-Technical Privacy Controls
**Definition:** Administrative and procedural safeguards that govern how an organization handles sensitive information.

* **Privacy Impact Assessment (PIA):** A formal study conducted to identify and reduce the privacy risks of a new project or system before it is launched.
* **Data Minimization:** The principle of only collecting the specific data necessary to fulfill a task. If you don't need a user's date of birth to provide a service, don't ask for it.
* **Retention and Disposal:** Policies that dictate how long data should be kept and the specific, secure way it must be destroyed once it is no longer needed.
* **Breach Notification:** A legal and procedural requirement to notify affected individuals and regulatory bodies (like the OCR or State Attorney General) if their private data is compromised.

## 3. Privacy Notices and Agreements
* **Privacy Notice:** A public-facing document that informs users how an organization collects, uses, shares, and protects their personal information.
* **Terms and Conditions (T&C) Agreement:** A legal contract between the service provider and the user that outlines the rules for using the service, including liability and acceptable use.

## 4. Disk Encryption Methods
**Definition:** Protecting "Data at Rest" by scrambling the contents of a storage device.

* **Stacked File System:** Encryption that happens at the file or directory level. Files are encrypted before being written to the disk.
* **Block Device Encryption:** Encrypts the entire storage partition or disk as a single "block." The most common example is **Full Disk Encryption (FDE)**.
* **Self-Encrypting Drive (SED):** A hard drive or SSD with a built-in controller that automatically encrypts all data written to the media at the hardware level.

## 5. Encryption Hardware
* **Smart Card:** A physical card with an embedded microchip used for authentication and storing digital certificates or cryptographic keys.
* **Trusted Platform Module (TPM):** A dedicated chip on a computer's motherboard used to store cryptographic keys, passwords, and digital certificates securely. It provides a "Hardware Root of Trust."
* **Hardware Security Module (HSM):** A high-end, external physical device used to safeguard and manage digital keys for strong authentication and cryptoprocessing in enterprise environments.
* **Secure Enclave:** A specialized, isolated area within a processor (CPU/SoC) that handles sensitive data (like biometric info or encryption keys) separately from the main Operating System.

## 6. Secure Media Destruction
**Definition:** Physical methods used to ensure that data on decommissioned hardware can never be recovered.

* **Pulverizing:** Using heavy machinery to grind a hard drive or storage media into tiny, unrecognizable pieces or dust.
* **Pulping:** A process specifically for paper documents where the paper is mixed with water and chemicals to break down the fibers into a liquid slurry.
* **Incineration:** Using high-temperature furnaces to burn storage media (tapes, paper, or optical discs) until they are reduced to ash.

# System Hardening Framework

## 1. Least Functionality
**Definition:** The practice of configuring an information system to provide only essential capabilities and specifically prohibiting or restricting the use of unnecessary functions, ports, protocols, and services.
* **Action:** Disable unused Windows services (like Print Spooler on a File Server) or uninstall unnecessary software (like games or trialware) from a base image.
* **Benefit:** If a service isn't running, it cannot be exploited by an attacker.

### 2. Secure Configuration
**Definition:** The use of established security "baselines" to ensure a system is set up according to industry best practices rather than factory defaults.
* **Baselines:** Using **CIS (Center for Internet Security)** Benchmarks or **STIGs (Security Technical Implementation Guides)** to configure OS settings.
* **Action:** Changing default admin passwords, disabling guest accounts, and configuring session timeouts.

### 3. Application Control
**Definition:** Preventing unauthorized applications from executing on a host.
* **Allowlisting:** Only specifically approved applications are allowed to run. (High security, high administrative overhead).
* **Blocklisting:** All applications are allowed except those specifically identified as malicious. (Lower security, easier to manage).
* **Tools:** Windows AppLocker or Windows Defender Application Control (WDAC).

### 4. Hardware Assurance Features
**Definition:** Using physical hardware components to verify the integrity of the system during boot and operation.
* **Trusted Platform Module (TPM):** Stores cryptographic keys and ensures the boot process hasn't been tampered with.
* **Secure Boot:** A UEFI feature that ensures only digitally signed, "trusted" bootloaders and drivers can load during startup.
* **Hardware Root of Trust:** A secure starting point in the hardware that is inherently trusted.

## 5. Host-Level Security Controls

### Account Security
* **Least Privilege:** Users only have the permissions necessary for their job.
* **MFA (Multi-Factor Authentication):** Requiring more than just a password for access.
* **Password Complexity:** Enforcing length and character requirements via Group Policy.

### Security Software
* **EDR (Endpoint Detection and Response):** Modern security tools that monitor behavior, not just file signatures (like traditional AV).
* **HIPS/HIDS:** Host-based Intrusion Prevention/Detection Systems that monitor for suspicious system calls or changes to critical files.

### Patching (Update Management)
* **Definition:** Regularly applying security updates to the OS and third-party applications.
* **Staging:** Testing patches in a "Dev" environment before pushing them to "Production" to ensure they don't break mission-critical apps.
* **Action:** Using tools like **WSUS (Windows Server Update Services)** or **SCCM** to centralize patching.

### Logging and Monitoring
* **Definition:** Recording system events (Logons, File Access, Errors) to detect and investigate security incidents.
* **Local Logs:** Windows Event Viewer (System, Security, Application logs) or Linux `/var/log`.
* **Centralized Logging:** Shipping logs to a **SIEM (Security Information and Event Management)** like Splunk or Azure Sentinel for real-time analysis.

# Application and Hardware Security Frameworks

## 1. Application Control
**Definition:** A security practice used to prevent unauthorized or malicious programs from executing. It is a critical part of a "Defense in Depth" strategy.

### Blacklisting (Blocklisting)
* **Definition:** A "permissive" approach where all applications are allowed to run **except** those specifically identified as malicious or unauthorized.
* **Risk:** High. It relies on the administrator knowing about every threat in advance. If a new piece of malware (Zero-Day) isn't on the list, it will run.
* **Benefit:** Low administrative overhead; users can generally install what they need without IT intervention.

### Whitelisting (Allowlisting)
* **Definition:** A "restrictive" approach where **no** applications are allowed to run except those specifically approved by the administrator.
* **Benefit:** Extremely high security. Even if an attacker successfully drops malware onto the system, it will fail to execute because it isn't on the "Allowed" list.
* **Trade-off:** High administrative overhead. IT must vet and approve every single application and update used by the organization.

## 2. Code Signing
* **Definition:** The process of digitally signing executables and scripts to confirm the software author and guarantee that the code has not been altered or corrupted since it was signed.
* **Mechanism:** Uses **Public Key Infrastructure (PKI)**. The developer signs the code with a private key, and the OS verifies it with the corresponding public key.
* **Real-World Use Case:** When you install a driver in Windows, the OS checks for a digital signature. If the signature is missing or invalid, Windows will warn the user or block the installation to prevent rootkits.

## 3. Hardware and Firmware Security Features

### Executable Space Prevention (DEP/NX Bit)
* **Definition:** A security feature that marks certain sectors of system memory as "non-executable." 
* **Mechanism:** Known as **DEP (Data Execution Prevention)** in Windows or the **NX (No-eXecute) bit** at the CPU level.
* **Goal:** To prevent **Buffer Overflow** attacks. If an attacker tries to inject malicious code into a data storage area of memory and then execute it, the CPU will block the attempt and crash the process instead.

### Secure Boot
* **Definition:** A feature of the **UEFI (Unified Extensible Firmware Interface)** that ensures the computer boots using only software that is trusted by the Original Equipment Manufacturer (OEM).
* **Process:** The UEFI firmware checks the digital signature of each piece of boot software (Option ROMs, EFI drivers, and the OS bootloader). If the signatures are valid, the PC boots; otherwise, it stops the process.
* **Goal:** To prevent **Rootkits** and **Bootkits** from loading before the Operating System even starts.

### Trusted Platform Module (TPM)
* **Definition:** A dedicated international standard for a secure cryptoprocessor—a dedicated microcontroller designed to secure hardware through integrated cryptographic keys.
* **Functions:**
    * **Platform Integrity:** It "measures" the boot process and stores the hashes. If the hardware or BIOS is tampered with, the TPM can refuse to release encryption keys.
    * **Disk Encryption:** It works with **BitLocker** to ensure the drive can only be decrypted on that specific physical machine.
    * **Secure Storage:** It stores passwords, certificates, and keys in a hardware-protected vault that is difficult to "sniff" or hack.
 
# Endpoint Security Software Stack

## 1. Antivirus (AV) / Endpoint Detection & Response (EDR)
* **Definition:** Software designed to prevent, detect, and remove malware.
* **Legacy AV:** Relies on **Signatures** (fingerprints of known malware). If the file matches a database entry, it is blocked.
* **Modern EDR:** Uses **Heuristics** and **Behavioral Analysis** to spot suspicious patterns (e.g., a Word doc suddenly launching a PowerShell script).
* **Benefit:** EDR provides deep visibility into the "root cause" of an infection, allowing admins to see exactly how a threat entered the network.

## 2. Host-Based Firewall
* **Definition:** A software application that monitors and filters incoming and outgoing network traffic based on an individual host's security policy.
* **Real-World Use Case:** **Windows Defender Firewall** or Linux **iptables/nftables**.
* **Benefit:** Provides "Micro-segmentation." Even if an attacker gets onto the local network, a host-based firewall can prevent them from "pinging" or connecting to other workstations.

## 3. Browser Protection
* **Definition:** Security extensions or built-in features (like **Microsoft Defender SmartScreen**) that protect users while they navigate the web.
* **Capabilities:** * **URL Filtering:** Blocking known malicious or phishing websites.
    * **Sandboxing:** Running browser processes in an isolated container so a malicious script cannot access the rest of the OS.
    * **Ad-Blocking:** Preventing "Malvertising" from executing code in the browser.

## 4. Email Protection (Endpoint Level)
* **Definition:** While much email security happens at the Gateway (SaaS level), endpoint agents provide a final check on attachments and links.
* **Capabilities:** * **Attachment Sandboxing:** Opening a PDF in a safe, hidden virtual environment to see if it tries to install malware.
    * **Link Rewriting:** Changing URLs in an email so they are scanned for threats every time the user clicks them.

## 5. Host-Based Intrusion Detection System (HIDS)
* **Definition:** A system that monitors the internals of a single host for suspicious activity, such as unauthorized registry changes or unusual system calls.
* **Example:** **OSSEC** or **Wazuh**.
* **Benefit:** Unlike a network IDS, a HIDS can see exactly what is happening *inside* the encrypted traffic once it reaches the host.

## 6. File Integrity Monitoring (FIM)
* **Definition:** A security control that alerts administrators when critical system files (like `C:\Windows\System32` or `/etc/passwd`) are modified.
* **Mechanism:** It creates a **Baseline Hash** of important files. If the hash changes, it means the file was altered, potentially by a Rootkit or an unauthorized user.
* **Compliance:** Required by standards like **PCI DSS** to ensure the integrity of systems handling credit card data.

## 7. Data Loss Prevention (DLP) - Endpoint
* **Definition:** Software that prevents sensitive data from leaving the endpoint through unauthorized channels.
* **Real-World Use Case:** An agent that blocks a user from copying a file labeled "Confidential" to a USB thumb drive or pasting sensitive "PII" into a web form.
* **Action:** Can be configured to **Audit** (log the event), **Block** (stop the action), or **Encrypt** (force the file to be protected before it leaves).

# Endpoint Detection and Response Frameworks

## 1. EPP (Endpoint Protection Platform)
* **Definition:** A preventative security suite designed to detect and block known threats at the device level before they can execute.
* **Focus:** **Prevention.** It acts as the "first line of defense."
* **Capabilities:** Combines traditional Antivirus (AV), personal firewalls, and data encryption into a single agent.
* **Limitation:** Primarily effective against "known" malware signatures; it often struggles with sophisticated, fileless, or zero-day attacks.

## 2. EDR (Endpoint Detection and Response)
* **Definition:** A tool that provides continuous monitoring and recording of endpoint data (processes, registry changes, network connections) to detect and respond to advanced threats.
* **Focus:** **Detection and Visibility.** It assumes a breach *will* happen and provides the "flight recorder" data to investigate it.
* **Capabilities:** * **Behavioral Analysis:** Spots suspicious patterns (e.g., Word launching PowerShell).
    * **Threat Hunting:** Allows admins to search across all workstations for a specific file hash or IP address.
    * **Containment:** Can remotely isolate an infected laptop from the network with one click.

## 3. MDR (Managed Detection and Response)
* **Definition:** A service-based offering where a third-party provider (an MSSP) manages an organization's EDR/XDR tools and monitors alerts 24/7.
* **Focus:** **Personnel and Expertise.**
* **Real-World Use Case:** A mid-sized company in **Chesapeake** that has the budget for security software but lacks a 24/7 internal Security Operations Center (SOC) team. 
* **Benefit:** Provides "human-in-the-loop" analysis to filter out false positives and provide expert remediation guidance during an incident.

## 4. XDR (Extended Detection and Response)
* **Definition:** A cross-layered security approach that integrates data from endpoints, networks, cloud servers, and email into a single "data lake" for correlated analysis.
* **Focus:** **Integration and Correlation.** * **The "X" Factor:** Unlike EDR, which only sees the workstation, XDR can see that a malicious email (Email Security) was opened, which led to a process running (Endpoint), which then tried to connect to a suspicious IP (Network).
* **Benefit:** Reduces "siloed" views and automates response across different security products simultaneously.

# Mobile Device Management & Security

## 1. Mobile Device Connections
* **Wi-Fi:** High-speed local networking. Security focus: Using **WPA3-Enterprise** and avoiding unsecured public hotspots.
* **Cellular:** Wide-area connectivity (LTE/5G). Generally more secure than public Wi-Fi but subject to "Stingray" (IMSI catcher) eavesdropping.
* **Bluetooth:** Short-range wireless. Vulnerable to **Bluejacking** (sending unsolicited messages) and **Bluesnarfing** (stealing data).
* **USB:** Physical connection for charging and data transfer. Security focus: Preventing **Juice Jacking** by using "USB Data Blockers."

## 2. Mobile Deployment Models

| Model | Ownership | Control | Description |
| :--- | :--- | :--- | :--- |
| **COBO** | Corporate | Maximum | **Corporate Owned, Business Only.** The device is strictly for work; no personal apps allowed. |
| **COPE** | Corporate | High | **Corporate Owned, Personally Enabled.** The company owns it, but the user can use it for personal tasks. |
| **BYOD** | User | Low | **Bring Your Own Device.** The user uses their personal phone for work. High privacy for the user, high risk for the company. |
| **CYOD** | User/Corp | Medium | **Choose Your Own Device.** The company provides a list of approved devices the user can choose from, making management easier. |

## 3. MDM & Unified Management Categories
* **MCM (Mobile Content Management):** Secures the specific **files** and documents accessed on the device (e.g., a secure PDF viewer).
* **MAM (Mobile Application Management):** Controls which **apps** can be installed and how they handle data (e.g., preventing "Copy/Paste" from Outlook to a personal Notes app).
* **MIM (Mobile Identity Management):** Ensures only authorized users can access the device and its services (Certificates, Biometrics, MFA).
* **EMM (Enterprise Mobility Management):** A suite that combines MDM, MAM, and MCM into one platform.
* **UEM (Unified Endpoint Management):** The modern evolution that manages **everything** (Laptops, Mobile, IoT, Tablets) from a single console.

## 4. Mobile Data Protection

### Storage Segmentation & Containerization
* **Definition:** Creating a "Work Profile" or encrypted container that separates corporate data from personal data on the same physical device.
* **Benefit:** If an employee leaves, the company can perform a **Selective Wipe** (deleting only work data) without touching the user's personal photos.

### Encryption Methods
* **File-Based Encryption (FBE):** Different files are encrypted with different keys. Allows the phone to perform basic functions (like alarms) while the rest of the data is still locked.
* **Full Device Encryption (FDE):** Encrypts the entire storage disk. The device cannot boot or function until the user enters their passcode.
* **microSD HSM:** Using a specialized microSD card that acts as a **Hardware Security Module** to store encryption keys and perform cryptographic operations physically.

## 5. Mobile Application Security

* **Application Allow Lists:** Only pre-approved apps from the corporate store can be installed.
* **Secrets Management:** Ensuring that API keys or passwords aren't "hardcoded" into mobile apps but are retrieved securely from a vault.
* **Encrypted Protocols:** Mandating the use of **HTTPS (TLS)** and **VPNs** for all app communications to prevent Man-in-the-Middle attacks.
* **Push Notifications:** Managing how much data is displayed in a notification on a locked screen (e.g., "New Message" vs. showing the actual content).
* **App Permissions:** The "Gatekeeper" of mobile security. Restricting apps from accessing the Microphone, Camera, or Contacts unless strictly necessary.
* **Containerization:** Running apps in an isolated environment so they cannot interact with other apps or the host OS directly.

# Application Exploits & Memory Vulnerabilities

## 1. Core Application Exploits
* **Privilege Escalation:** Gaining a higher level of access (e.g., from a standard User to an Administrator/Root) by exploiting a bug or configuration flaw.
* **Directory Traversal (Path Traversal):** An attack that exploits insufficient security validation of user-supplied input file names to access files and directories stored outside the intended folder (e.g., using `../../etc/passwd`).
* **Arbitrary Code Execution (ACE):** The ability of an attacker to execute any commands or code of their choice on a target machine.
* **Resource Exhaustion:** A DoS attack that consumes a server's resources (CPU, RAM, or Disk Space) until it becomes unresponsive (e.g., a "Zip Bomb").

## 2. OWASP Top 10
**Definition:** A standard awareness document for developers and web application security. It represents a broad consensus about the most critical security risks to web applications.
* **Key Risks include:** Broken Access Control, Cryptographic Failures, Injection, and Insecure Design.

## 3. Manipulation Techniques
* **Input Manipulation:** Altering data sent to an application to change its behavior (e.g., changing a "Price" field in a web form).
* **Header Manipulation:** Tampering with HTTP headers (like Cookies or Referrer) to bypass authentication or perform **Session Hijacking**.
* **Memory Manipulation:** Directly modifying the data stored in RAM to alter the execution flow of a program.
* **Injection:** Trickery where an attacker sends "data" that the application mistakenly interprets as a "command."

## 4. Memory Vulnerabilities
* **Buffer Overflow:** Sending more data to a memory buffer than it can hold, causing the excess to spill into adjacent memory. This can overwrite the "Return Address" to point to malicious code.
* **Integer Overflow:** Occurs when an arithmetic operation attempts to create a numeric value that is outside of the range that can be represented (e.g., adding 1 to a maximum value and having it "wrap around" to zero).
* **Dereferencing:** An attack where a program attempts to read a memory address that is null or invalid, often causing a crash or allowing for code execution.
* **Memory Leak:** A failure in a program to release discarded memory, causing performance degradation and eventual system failure.

## 5. Race Conditions
* **Definition:** A vulnerability where the outcome depends on the sequence or timing of uncontrollable events (e.g., checking a file's permissions and then opening it, but an attacker swaps the file in the millisecond between those two actions).

## 6. SQL Injection (SQLi)
**Definition:** Inserting malicious SQL queries into input fields to manipulate a backend database.

### SQLi Techniques
* **Unfiltered Escape Characters:** Using characters like the single quote (`'`) to "break out" of a data field and start a command.
* **Improper Input Types:** Sending text into a field that expects a number to trigger an error or bypass logic.
* **Stacked Queries:** Ending a legitimate query with a semicolon (`;`) and then adding a second, malicious command (e.g., `; DROP TABLE Users`).
* **Blind Injection:** Asking the database "True/False" questions when the app doesn't show direct errors (e.g., "If the admin password starts with 'A', wait 10 seconds").
* **Signature Evasion:** Using encoding (like Hex or URL encoding) to hide SQL keywords from firewalls.

## 7. Other Injection Targets
* **NoSQL Injection:** Targeting non-relational databases like MongoDB.
* **LDAP Injection:** Manipulating Active Directory or OpenLDAP queries to bypass login screens.
* **XML Injection (XXE):** Exploiting how an application parses XML input to read local files or scan internal networks.
* **Command Injection:** Injecting OS-level commands (like `ls` or `dir`) into a web application to interact with the server's shell.
* **Process Injection:** Masking malicious code by "injecting" it into the memory space of a legitimate, running process (like `explorer.exe`).

## 8. Client-Side Attacks
* **Browser Add-ons / Malicious Add-ons:** Extensions that steal passwords, inject ads, or track browsing history.
* **Cookies:** Attackers can steal session cookies to impersonate a user (Session Hijacking) or perform **Cross-Site Request Forgery (CSRF)**.
* **Attachments:** Common delivery methods for malware via email (Word docs with Macros or PDFs with embedded scripts).

# Web Vulnerabilities & Secure Development

## 1. XSS (Cross-Site Scripting) Techniques
**Definition:** An attack where malicious scripts are injected into otherwise benign and trusted websites. The script executes in the **victim's browser**, not on the server.

* **Stored (Persistent) XSS:** The most dangerous type. The script is permanently stored on the target server (e.g., in a database, a forum post, or a comment field). Every user who views that page executes the script.
* **Reflected (Non-Persistent) XSS:** The script is "reflected" off a web server to the victim. It is usually delivered via a crafted link in an email or chat message.
* **DOM-Based XSS:** The vulnerability exists in the client-side code rather than the server-side code. The attack modifies the "Document Object Model" environment in the victim's browser.

## 2. Request Forgeries
* **CSRF (Cross-Site Request Forgery):** An attack that forces an authenticated user to execute unwanted actions on a web application in which they are currently logged in.
* **Mechanism:** It tricks the browser into sending a forged HTTP request (like "Transfer $1000 to Attacker") to a site where the user has an active session cookie.
* **Analogy:** A criminal tricking a bank teller into processing a check because the signature (the session cookie) looks legitimate.

## 3. Software Development Life Cycle (SDLC)
**Definition:** A structured process used by organizations to design, develop, and test high-quality software.

1. **Initiation:** Defining the project goals and security requirements.
2. **Development / Acquisition:** Writing the code or purchasing software components.
3. **Implementation / Assessment:** Testing the code (Unit, Integration, and Security testing) and deploying it.
4. **Operations and Maintenance:** Patching, monitoring, and updating the software in production.
5. **Disposal:** Securely retiring the software and archiving or destroying associated data.

## 4. Software Development Models
* **Waterfall:** A linear, sequential model where each phase must be completed before the next begins. Hard to change requirements once started.
* **Agile:** An iterative approach focusing on continuous delivery, small "sprints," and constant feedback. Security must be integrated into every sprint.

## 5. DevSecOps & Modern Infrastructure
**Definition:** Integrating security practices into the DevOps continuous integration/continuous deployment (CI/CD) pipeline.

* **Automated Processes:** Using scripts to automatically scan code for vulnerabilities during every build.
* **Baselining:** Establishing a known "good" state for systems so unauthorized changes can be detected.
* **Immutable Systems:** Instead of patching a running server, you replace it entirely with a new, pre-configured image.
* **Infrastructure as Code (IaC):** Managing and provisioning infrastructure (servers, networks) through machine-readable definition files (like Terraform or Ansible).
* **Software-Defined Security:** Using code to dynamically update firewall rules or access logs in response to threats.

## 6. Secure Coding Methods
**Definition:** Best practices for writing code that is resistant to the exploits we've discussed.

* **Input Validation:** Ensuring data is in the correct **format** (e.g., a zip code should only be numbers).
* **Input Sanitation:** Cleaning data to remove dangerous characters (e.g., stripping `<script>` tags).
* **Error and Exception Handling:** Ensuring the app fails gracefully. Never show "Verbose" errors (like database connection strings) to the end-user.
* **Memory Management:** Manually clearing sensitive data from RAM once it is no longer needed.
* **Code Commentary:** Using comments to explain logic, but ensuring no sensitive info (passwords, API keys) is left in the comments.

### Input Validation: Client-Side vs. Server-Side
* **Client-Side (Browser):** Great for user experience (instant feedback), but **cannot be trusted** for security because an attacker can bypass the browser entirely.
* **Server-Side (Backend):** The **only** reliable place for security validation. All data coming from a user must be treated as "untrusted."

# Application Resiliency & Change Management

## 1. Forgery Prevention
**Definition:** Technical measures taken to ensure that requests or data are legitimate and haven't been "faked" by an attacker.
* **CSRF Tokens:** Using unique, cryptographically strong "anti-forgery tokens" for every user session. The server checks for this token before processing a request (like a password change).
* **SameSite Cookie Attributes:** Configuring cookies so they aren't sent during cross-site requests, effectively neutralizing many CSRF attacks.

## 2. Software Diversity
* **Definition:** Using different operating systems, application versions, or coding languages across an environment.
* **Benefit:** It prevents a single "Zero-Day" exploit from taking down the entire organization. If all your servers are identical, one exploit kills them all; if they are diverse, the attacker has to work much harder.

## 3. Application Testing Methods
**Definition:** Different approaches to finding bugs and security holes before software is released.

* **Static Code Analysis (SAST):** Reviewing the **source code** without actually running the program. It looks for "bad patterns" like hardcoded passwords or unsafe functions.
* **Dynamic Code Analysis (DAST):** Testing the application while it is **running**. It involves sending malformed data (Fuzzing) to the app to see if it crashes or leaks data.
* **Stress Testing:** Pushing the application to its limits (and beyond) to see how it handles extreme loads and to identify **Resource Exhaustion** points.

## 4. Code Quality & SDKs
* **Code Quality:** Maintaining clean, readable, and well-documented code. Poor code quality often leads to "Technical Debt" and hidden security vulnerabilities.
* **Software Development Kits (SDKs):** Using pre-made sets of tools and libraries provided by vendors (like the Azure SDK or AWS SDK). 
    * **Risk:** If the SDK itself is compromised or outdated, every application built with it becomes vulnerable (Supply Chain Attack).

## 5. Sandboxing
* **Definition:** Running an application in an isolated, restricted environment where it cannot access the host's files or network unless explicitly permitted.
* **Real-World Use Case:** A web browser running each tab in a separate sandbox so a malicious site in Tab A cannot steal cookies from your bank in Tab B.

## 6. Hardening Applications
**The Four Pillars of Application Hardening:**
1. **Harden the Underlying Host and Network:** Ensure the OS is patched, the firewall is tight, and unnecessary services are disabled.
2. **Securely Configure the Application:** Change default admin credentials, disable debug modes, and use secure protocols (HTTPS).
3. **Thoroughly Test Before Deploying:** Use SAST, DAST, and User Acceptance Testing (UAT) in a "Staging" environment.
4. **Maintain Security Over Time:** Monitor logs for attacks and apply patches as soon as the vendor releases them.

## 7. Software Change Management
**Definition:** The formal process of ensuring that changes to the software environment are documented, tested, and authorized to prevent downtime or security gaps.

* **Change Request Management:** The initial phase where a developer or user proposes a change, explaining the "Why," the "How," and the "Rollback Plan."
* **Change Control:** The formal approval process by a **Change Advisory Board (CAB)**.
* **Version Control (e.g., Git):** Tracking every single change to the source code, allowing developers to see who changed what and "revert" to a previous version if a bug is found.
* **Release Management:** The planning and execution of moving code from the Dev environment to Production.
* **Configuration Management:** Ensuring that the settings and parameters of the software are consistent and documented across all servers.

# Automation, Orchestration, and Change Management

## 1. Automation vs. Orchestration
* **Automation:** Completing a single task without human intervention (e.g., a script that backups a database at midnight).
* **Orchestration:** The automated arrangement and coordination of **multiple** automated tasks to execute a complex workflow (e.g., spinning up a web server, configuring its firewall, and adding it to a load balancer simultaneously).

## 2. Scripting Environments
| Language | Primary Use Case |
| :--- | :--- |
| **Shell Scripts (Bash)** | The standard for Linux/Unix administration and automation. |
| **Batch Files (.bat)** | Legacy Windows scripting for simple command-line tasks. |
| **PowerShell** | The modern, object-oriented standard for Windows and Azure administration. |
| **Python** | Versatile, readable, and widely used for security tools and automation. |
| **Ruby** | Often used in configuration management tools like Chef and Puppet. |
| **JavaScript** | Primarily for web-based automation and server-side logic (Node.js). |

## 3. Security Automation
* **SCAP (Security Content Automation Protocol):** A suite of specifications for standardizing the format in which security software communicates information about software flaws and security configurations.
* **SIEM (Security Information & Event Management):** Collects and analyzes log data to provide real-time reporting and historical analysis.
* **SOAR (Security Orchestration, Automation, and Response):** Takes SIEM a step further by using **Playbooks** to automatically respond to incidents (e.g., if a SIEM sees a brute force attack, SOAR automatically blocks the IP at the firewall).

## 4. Resource Provisioning
* **Network Provisioning:** Automated setup of VLANs, subnets, and routing tables.
* **Server Provisioning:** Using tools like **Terraform** to deploy virtual machines or containers.
* **User Provisioning:** Automatically creating accounts and setting permissions when a new employee is hired.
* **Deprovisioning:** The critical security step of revoking all access when a user leaves the organization to prevent "Orphaned Accounts."

## 5. The CI/CD Pipeline (Automated Development)
* **Continuous Integration (CI):** Developers frequently merge their code changes into a central repository where automated builds and tests are run.
* **Continuous Delivery:** Code changes are automatically prepared for a release to production.
* **Continuous Deployment:** Every change that passes all stages of your production pipeline is released to your customers automatically.
* **Continuous Validation/Monitoring:** Automated checks to ensure the app remains healthy and secure after deployment.

## 6. Technology Integration: SOAP vs. REST
* **SOAP (Simple Object Access Protocol):** An older, highly structured protocol that uses XML. It is very strict and preferred for high-security financial transactions.
* **REST (Representational State Transfer):** The modern standard for web APIs. It is lightweight, uses JSON, and is easier to scale for cloud applications.

## 7. Change Management & ITSM
**Definition:** The structured approach to transitioning individuals, teams, and organizations from a current state to a desired future state.

### The Change Management Process:
1. **Identification:** Recognizing the need for a change.
2. **Change Request:** Submitting a formal proposal with a rollback plan.
3. **Approval:** Review by a **Change Advisory Board (CAB)**.
4. **Implementation:** Executing the change in a controlled manner.
5. **Follow-up:** Verifying that the change worked and didn't break other systems.

### Modern Deployment Strategies:
* **Rolling Updates:** Updating one server at a time until the whole cluster is on the new version.
* **Blue-Green Updates:** Running two identical environments. You update the "Green" environment while users stay on "Blue." Once verified, you switch the traffic to Green.
* **Canary Testing:** Releasing the new version to a small, specific group of users first to catch bugs before a full rollout.

## 8. Risks of Automation & Guardrails
* **Risks:** "Automating a mess creates an automated mess." Errors can propagate across thousands of servers in seconds if a script is buggy.
* **Guardrails:** Implementing **Limiters** (e.g., "don't delete more than 10% of servers at once") and **Manual Checkpoints** in automated workflows to prevent catastrophic failures.

# Asset and Configuration Management

## 1. Inventory Management
**Definition:** The process of tracking every piece of hardware and software within an organization. You cannot secure what you do not know exists.
* **Hardware Inventory:** Tracking physical assets (Laptops, Servers, Routers) using Serial Numbers, Asset Tags, and MAC addresses.
* **Software Inventory:** Maintaining a list of installed applications and licenses to ensure compliance and to identify "Shadow IT" (unauthorized software).
* **Security Value:** Essential for vulnerability management; if a new critical bug is found in a specific laptop model, you need to know exactly how many you have and where they are.

## 2. Configuration Management (CM)
**Definition:** The process of maintaining a system’s settings and performance in a known, consistent state throughout its life. 
* **Baselines:** Creating a "Golden Image" or a standard set of security settings that every new server must follow.
* **Configuration Management Tools:**
    * **Ansible:** Uses "Playbooks" (YAML) to push configurations. It is **Agentless**, meaning you don't need to install software on the target.
    * **Puppet / Chef:** Uses an **Agent-based** model where the client periodically checks a central server for updates.
    * **Terraform:** Focuses on **Infrastructure as Code (IaC)** to provision the actual hardware/cloud resources.

## 3. The CMDB and SCM
* **CMDB (Configuration Management Database):** A centralized repository that stores information about all **Configuration Items (CIs)**—including hardware, software, and the *relationships* between them. 
    * *Example:* The CMDB shows that "Server A" runs "SQL Database B," which supports "Payroll App C."
* **SCM (Software Configuration Management):** A subset of CM that focuses specifically on the evolution of software. It tracks changes to code, documentation, and requirements.

## 4. Version Control
* **Definition:** A system that records changes to a file or set of files over time so that you can recall specific versions later.
* **Centralized (SVN):** One central server holds all the files.
* **Distributed (Git):** Every user has a full copy of the repository history on their local machine.
* **Key Terms:**
    * **Commit:** Saving your changes to the history.
    * **Branch:** Creating a separate "path" to test a new feature without breaking the main code.
    * **Merge:** Combining a branch back into the main project.
    * **Rollback:** Returning to a previous "known good" state after a change causes a failure.

## 5. Planning Patch Management
**Definition:** A systematic approach to testing and deploying software updates (patches) to fix bugs and security vulnerabilities.

### The Patch Management Workflow:
1. **Monitoring:** Subscribing to vendor alerts (like Microsoft Security Bulletins) to know when a patch is released.
2. **Assessment:** Determining if the patch is relevant to your environment. (Does this Linux patch apply to our specific distro?)
3. **Staging/Testing:** **Crucial Step.** Installing the patch in a "lab" environment that mimics production to ensure it doesn't cause crashes or compatibility issues.
4. **Deployment:** Pushing the patch to production servers, often using a **Rolling Update** to maintain availability.
5. **Verification:** Scanning systems after the patch to confirm it was installed correctly and the vulnerability is gone.

# Business Continuity & Disaster Recovery (BCDR)

## 1. The Planning Framework
* **Business Continuity Plan (BCP):** A high-level, proactive strategy for maintaining business operations during a disruption.
* **Business Impact Analysis (BIA):** The process of identifying **Mission Essential Functions** and the potential impact of their loss.
* **Disaster Recovery Plan (DRP):** A technical, reactive plan containing specific steps to restore IT systems and data after a disaster.
* **ISCP (Information System Contingency Plan):** Technical procedures for recovering specific systems.
* **COOP (Continuity of Operations):** A US government term for ensuring essential functions continue during an emergency.
* **Succession Planning:** Identifying and developing internal people with the potential to fill key leadership positions if they become unavailable.

## 2. Recovery Objectives
To create a BCP/DRP, you must define your "Time" and "Data" limits:
* **RTO (Recovery Time Objective):** The maximum amount of time a system can be down before the business suffers unacceptable consequences. (e.g., "The web server must be back up in 4 hours.")
* **RPO (Recovery Point Objective):** The maximum amount of data loss measured in time. (e.g., "We can lose up to 1 hour of data; therefore, we must back up every 60 minutes.")

## 3. High Availability & Power
* **Fault Tolerance:** The ability of a system to continue operating even if one or more components fail (e.g., redundant power supplies).
* **UPS (Uninterruptible Power Supply):** A battery backup that provides immediate power for a short time to allow for a graceful shutdown or to bridge the gap until a **Generator** kicks in.
* **Redundant Power Distribution:** Using two different power circuits (A-side and B-side) to ensure that a single tripped breaker doesn't take down a rack.

## 4. Scalability & Redundancy
* **Vertical Scaling (Scaling Up):** Adding more "horsepower" (CPU, RAM) to an existing server.
* **Horizontal Scaling (Scaling Out):** Adding more servers to a cluster to share the load.
* **Elasticity:** The ability of a system (usually in the cloud) to scale up and down automatically based on demand.
* **Load Balancing vs. Clustering:**
    * **Load Balancing:** Distributes traffic across multiple servers.
    * **Clustering:** A group of servers working together so they appear as a single system, providing high availability.

## 5. Alternate Processing Sites
| Site Type | Readiness | Cost | Description |
| :--- | :--- | :--- | :--- |
| **Hot Site** | Minutes/Hours | Highest | A fully functional, mirrored data center with live data. |
| **Warm Site** | Hours/Days | Medium | Has hardware and some connectivity, but backups must be restored. |
| **Cold Site** | Days/Weeks | Lowest | An empty room with power/HVAC. No hardware or data present. |
| **Mobile Site** | Variable | Medium | A trailer or container outfitted as a data center that can be moved. |

## 6. Testing the Plan
* **Checklist/Read Through:** A simple review of the document for accuracy.
* **Tabletop Exercise (TTX):** Stakeholders gather in a room to discuss their response to a hypothetical scenario.
* **Simulation:** A hands-on drill where staff perform their recovery tasks in a non-production environment.
* **Parallel Test:** Restoring systems at an alternate site while the main site is still running.
* **Full Interruption:** Shutting down the main site to see if the recovery site actually works. (High risk!)

## 7. Data Backup & Storage
### The 3-2-1 Rule
* **3** total copies of your data (1 primary, 2 backups).
* **2** different media types (e.g., Disk and Tape).
* **1** copy offsite (e.g., Cloud or a physical vault).

### Backup Types
* **Full:** A complete copy of all data.
* **Differential:** Backs up everything changed since the **last Full backup**. (Faster to restore).
* **Incremental:** Backs up everything changed since the **last backup of any type**. (Faster to back up).
* **Snapshot / Image:** A point-in-time capture of a virtual machine or entire drive.

### Storage Replication
* **RAID:** Redundancy at the disk level to protect against drive failure.
* **Synchronous Replication:** Data is written to two locations at the same time. No data loss, but slower performance due to latency.
* **Asynchronous Replication:** Data is written to the primary site, then sent to the secondary site shortly after. Better performance, but risks slight data loss if the primary site fails before the sync.
