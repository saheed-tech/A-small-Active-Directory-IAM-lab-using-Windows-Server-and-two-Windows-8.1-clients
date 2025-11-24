
# Active Directory Simulation – CyberTech Solutions

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **Seedorf Tech**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**CyberTech Solutions** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (IT Department)
- 1 x Windows 8 Client PC (Advertising Department)
- 1 x Windows 8 Client PC (Human Resource Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win 8)   PC2 (Win 8)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.2.15  | AD Domain Controller (DC)   |
| Windows 8 PC  | DHCP    | Client (IT)           |
| Windows 8 PC | DHCP    | Client (Advertising)              |
| Windows 8 PC | DHCP    | Client (Human Resource)              |

---

## Domain Configuration

- **Domain Name**: `seedorf.tech`
- **Server Name**: `SEEDORF`
- **Static IP**: `10.0.5.5`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
CyberTech.local
├── OU: IT Department
│   └── Users: Uthman.IT
    

├── OU: ADVERTISING Department
│   └── Users: Lateef.AD


├── OU: HUMAN RESOURCE Department
│   └── Users: Akeem.HR
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableShutdown`
- **Linked to**: OU: IT Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `Start Menu and Task Bar` > `Remove and prevent access to the Shut Down, Restart, Sleep, and Hibernate commands`
  - `Security Filtering` > `Find all` > `Uthman.IT, Lateef.AD, Akeem.HR`
  - Set **"Remove all access to shut down: Deny all access"** to **Enabled**

Result: Shut Down, Restart, Sleep, and Hibernate commands disabled for all users in the **Accounts OU**.

---

## Screenshots

- AD Domain Structure
- GPO Editor Screenshot
- PC joined to domain
- Result of denied USB access

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**Saheea A. Olasunkanmi**  
Cybersecurity Analyst  
