# AI Prompting Tips

- Assign a Persona: Tell Gemini who it should be (e.g., "Act as a Senior Network Engineer").<br>
- State the Format: Tell Gemini how to answer (e.g., "Explain it as a table," "Give me a 5-step checklist," or "Use an analogy").<br>
- The Socratic Flip: Tell Gemini, "After you explain, ask me a follow-up question to see if I understood."<br>


## Domain 1: General Security Concepts

Covers Chapter 1: Fundamentals, Threats, and Strategy.

- **The Control Categorizer**  
  "Act as a security auditor. I will give you a list of security measures. For each one, tell me if it is Technical, Operational (Administrative), or Physical, and whether its function is Preventive, Detective, or Corrective. List these in a table."

- **The CIA Triad Analyst**  
  "Explain the CIA Triad (Confidentiality, Integrity, and Availability) using the analogy of a Hospital Medical Record system. Give one example of a 'failure' for each part of the triad."

## Domain 2: Threats, Vulnerabilities, and Mitigations

Covers Chapter 1 (Modules B/C) and Chapter 3 (Organizational Security).

- **Threat Actor Profiles**  
  "Create a comparison chart of the following threat actors: Nation-State, Hacktivist, Insider Threat, and Script Kiddie. Compare them based on their Motivation, Resources (Funding), and Sophistication."

- **Social Engineering Simulator**  
  "Act as a social engineer. Describe a Business Email Compromise (BEC) attack targeting a finance department. Explain the psychological triggers (like Urgency or Authority) being used to trick the victim."


## Domain 3: Security Architecture

Covers Chapter 4 (Cryptography), Chapter 5 (Networking), and Chapter 6 (Hardening).

- **The OSI "Traffic Cop"**  
  "I am a packet of data. Explain my journey through the 7 layers of the OSI Model. For each layer, tell me one 'security threat' that could happen to me (e.g., Layer 3 IP Spoofing)."

- **The Encryption Decoder**  
  "Explain the difference between Hashing, Symmetric Encryption, and Asymmetric Encryption. Give a 'Real-World Use Case' for each one (for example: storing passwords vs. browsing the web securely)."


## Domain 4: Security Operations

Covers Chapter 7 (Authentication) and Chapter 8 (Access Control).

- **The MFA Expert**  
  "Explain the five factors of Multi-Factor Authentication (MFA): Something you know, have, are, do, and somewhere you are. Give a modern example for each (like a TOTP app or a Geofence)."

- **Access Control Architect**  
  "Compare RBAC (Role-Based Access Control) and ABAC (Attribute-Based Access Control). Explain why a large corporation might prefer ABAC over RBAC for a highly sensitive project."
  

## Domain 5: Security Program Management & Oversight

Covers Chapter 2 (Risk Management) and Chapter 13/14 (Disaster Recovery).

- **The Risk Assessment Lab**  
  "Act as a Risk Manager. I have an asset worth $10,000. The Exposure Factor (EF) is 50%, and it happens once every two years. Help me calculate the SLE, ARO, and ALE. Explain what these numbers tell a business owner."

- **Incident Response Flowchart**  
  "Walk me through the 6 steps of the Incident Response Process (Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned). For each step, give me one 'Action Item' for a team dealing with a Ransomware attack."
