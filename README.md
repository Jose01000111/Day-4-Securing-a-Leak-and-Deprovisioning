<p align="center">
<img src="https://i.imgur.com/pqTjnLb.png" alt="osTicket logo"/>
</p>

## Day 4 – Securing a Leak and Deprovisioning

After a confidential contract leak jeopardized negotiations with Chicago, I was tasked with securing the file and deprovisioning the employee responsible for the breach.

I encrypted the contract file using EFS (Encrypting File System) and restricted access to authorized groups only. I also disabled the terminated employee’s account (Staley The Bear), removed all group memberships, and revoked access to email and systems. (Consulted ChatGPT for best practices on user deprovisioning and file encryption.)

### 🧪 Lab Tasks

#### 1. Create the Leaked Contracts File
I created a file named leaked_contracts.txt that contained sensitive contract data. To ensure its confidentiality, I stored it in a secure and access-controlled location within the system.

<p align="center">
<img src="https://i.imgur.com/34zJp6N.png" alt="osTicket logo"/>
</p>

***

<p align="center">
<img src="https://i.imgur.com/LodtLz6.png" alt="osTicket logo"/>
</p>

***

#### 2. Blocked Staley's Azure AD Account: Prevented the user from signing in.
To immediately revoke access, I blocked Staley’s Azure Active Directory account, preventing future sign-ins. I removed the user from all group memberships to cut off access to any group-based resources. I also revoked all assigned licenses and forced a sign-out from all active sessions across devices. For good measure, I used the gpupdate /force PowerShell command to apply policy changes.

<p align="center">
<img src="https://i.imgur.com/AVrfUE1.png" alt="osTicket logo"/>
</p>

***

<p align="center">
<img src="https://i.imgur.com/vu4Jzv4.png" alt="osTicket logo"/>
</p>

***

#### 3. Deprovision Staley the Bear's Account
I officially deprovisioned Staley’s account by disabling it in Azure Active Directory. I ensured the user was removed from all AD groups and performed a final forced sign-out to terminate any lingering sessions or access points

<p align="center">
<img src="https://i.imgur.com/7rmSPc2.png" alt="osTicket logo"/>
</p>

***

#### 4. Audit and Verify
I reviewed Microsoft Entra logs to confirm that the file was accessed appropriately and that all account changes were successfully logged. For assurance, I consulted ChatGPT to align the process with best practices for deprovisioning and sensitive file handling.

<p align="center">
<img src="https://i.imgur.com/DHS7QF9.png" alt="osTicket logo"/>
</p>

***

### :💻 Technology Stack

#### Azure Active Directory (Azure AD)

#### Azure Information Protection (AIP)

#### Microsoft Purview

#### Microsoft Entra

#### Windows EFS (Encrypting File System)

### 🎯 Summary of Lab Goal
#### ✅ Secure confidential data: Encrypt and restrict access to the leaked contract file.

#### ✅ Deprovision malicious insider: Disable and remove access for Staley the Bear.

#### ✅ Audit system access: Verify file access and user account changes through logs.
