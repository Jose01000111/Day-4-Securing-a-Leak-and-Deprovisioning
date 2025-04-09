<p align="center">
<img src="https://i.imgur.com/pqTjnLb.png" alt="osTicket logo"/>
</p>

## Day 4 – Securing a Leak and Deprovisioning

After a confidential contract leak jeopardized negotiations with Chicago, I was tasked with securing the file and deprovisioning the employee responsible for the breach.

I encrypted the contract file using EFS (Encrypting File System) and restricted access to authorized groups only. I also disabled the terminated employee’s account (Staley The Bear), removed all group memberships, and revoked access to email and systems. (Consulted ChatGPT for best practices on user deprovisioning and file encryption.)

### 🧪 Lab Tasks

#### 1. Create the Leaked Contracts File
Created a file named leaked_contracts.txt containing sensitive contract data.

Stored it in a secure location on the system.

#### 2. Encrypt the File with Azure AD-integrated Protection
Used Azure Information Protection (AIP) to label and encrypt the file.

Applied a Confidential label that restricts access to only the authorized HR and Legal groups.

Confirmed the encryption and access controls were enforced via Microsoft Purview.

#### 3. Deprovision Staley the Bear's Account
Disabled staley via Azure Active Directory.

Removed Staley from all Azure AD groups.

Forced sign-out across all sessions and devices.

#### 4. Audit and Verify

Confirmed logs of file access and account changes through Microsoft Entra logs.

(Consulted ChatGPT for best practices on user deprovisioning and secure file handling.)

### ⚙️ Technology Stack
#### Azure Active Directory (Azure AD)

#### Azure Information Protection (AIP)

#### Microsoft Purview

#### Microsoft Entra

#### Windows EFS (Encrypting File System)

### 🎯 Summary of Lab Goal
#### ✅ Secure confidential data: Encrypt and restrict access to the leaked contract file.

#### ✅ Deprovision malicious insider: Disable and remove access for Staley the Bear.

#### ✅ Audit system access: Verify file access and user account changes through logs.
