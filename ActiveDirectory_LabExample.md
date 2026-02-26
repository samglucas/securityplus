# Lab Title: The Journey of "Jan Doe"
**Estimated Time:** 15 Minutes  
**Environment:** Any Windows Server with AD DS (or the THM AttackBox/Target VM)

---

### Introduction
This mini-lab bridges the gap between **TryHackMe theory** and **hands-on administration**. It focuses on the "Day 1 to Day 100" journey of a user in Active Directory, simulating the real-world tasks of a Technical Training Specialist or System Administrator.

---

### Phase 1: The Identity Life Cycle (5 Mins)
*In this phase, we simulate the **Joiner-Mover-Leaver** process.*

1.  **Provisioning (Joiner):**
    * Open **Active Directory Users and Computers (ADUC)**.
    * Create a new **Organizational Unit (OU)** called `Sales_Dept`.
    * Create a new **User**: `Jan Doe` (Logon name: `jdoe`).
    * **Concept Check:** Why do we check *"User must change password at next logon"*? (Initial credential security).

2.  **Maintenance (Mover):**
    * Jan is promoted to Manager. Create a new **OU** called `Management`.
    * **Action:** Drag and drop `jdoe` from `Sales_Dept` to `Management`.
    * **Concept Check:** Discuss how moving OUs might change which **Group Policy Objects (GPOs)** apply to her.



---

### Phase 2: Account Types & Group Scopes (5 Mins)
*Understanding where a user belongs and their specific "role" in the domain.*

1.  **Account Types:**
    * Identify `jdoe` as a **User Account**.
    * Identify the `Administrator` account as a **Privileged Account**.
    * Locate any **Service Accounts** (if they exist) to show the difference in intent and management.

2.  **Group Scopes:**
    * Create a **Global Group** named `GG_Sales_Read` (Used to organize users).
    * Create a **Domain Local Group** named `DL_Folder_Modify` (Used to assign permissions to resources).
    * **Action:** Add `jdoe` to `GG_Sales_Read`, then add `GG_Sales_Read` as a member of `DL_Folder_Modify`.
    * **Concept Check:** This follows the **AGDLP** strategy (**A**ccount > **G**lobal > **D**omain **L**ocal > **P**ermission).



---

### Phase 3: Password Policies & GPOs (5 Mins)
*Enforcing the "Rules of the Road" for the entire domain.*

1.  **Group Policy Management:**
    * Open **Group Policy Management Console (GPMC)**.
    * Navigate to **Default Domain Policy** > **Edit**.
    * Path: `Computer Configuration` -> `Policies` -> `Windows Settings` -> `Security Settings` -> `Account Policies` -> `Password Policy`.

2.  **Enforcement:**
    * Change **Minimum password length** to `14` characters.
    * Change **Password complexity requirements** to `Enabled`.

3.  **The "Force" Command:**
    * Open Command Prompt/PowerShell and run:
      ```powershell
      gpupdate /force
      ```
    * **Concept Check:** Why doesn't Jan's password change immediately? (GPOs apply at next refresh/logon; existing passwords aren't retroactively broken until the next forced change).

---

### Quick Discussion Points for Students
* **Security:** Why is "Account Disabling" better than "Account Deletion" when Jan leaves the company? (*Answer: Preserves the Security Identifier (SID) and file ownership for auditing.*)
* **Efficiency:** Why use Global Groups inside Domain Local groups instead of adding Jan directly to a folder? (*Answer: Scalability and reduced administrative overhead.*)
