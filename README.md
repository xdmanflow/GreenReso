# GreenReso – IS Security Project

> Academic project | Information Systems Design & Cybersecurity  
> Completed: November 2025

---

## Context

**GreenReso** is a French IoT company (40 employees, 3 sites) specializing in intelligent sensors for energy optimization in office buildings. The company operates a SaaS platform called **GreenPilot** and works with local authorities, public institutions, and CAC 40 companies.

This project was carried out as part of an IT infrastructure design exercise. The goal was to professionalize GreenReso's Information System to improve **security**, **document structuring**, and **employee experience** — while respecting digital sobriety principles.

---

## Objectives

- Design a secure and structured IS architecture
- Centralize document storage with role-based access (NTFS + Active Directory)
- Automate HR processes (account creation, folder provisioning)
- Raise cybersecurity awareness across all employee profiles
- Align the IS with DDRS (digital sobriety) principles

---

## Deliverables

### 1. Infrastructure Diagram (`Diagramme de l'architecture.pdf`)
A logical network view of GreenReso's target IS architecture, including:
- Active Directory, File Server, DNS
- Network segmentation by department
- Distribution of workstations across sites

### 2. Cybersecurity Awareness Guide (`GreenReso_Cybersecurity_Awareness_Guide.docx`)
A non-technical document aimed at all GreenReso employees, covering:
- Common digital threats (phishing, data leaks, weak passwords...)
- Simple, actionable good practices
- Designed for use during onboarding or team meetings

### 3. Final Technical Report (`Final Report of the IS Security Project.pdf`)
A comprehensive technical document detailing:
- Active Directory structure (OUs, Security Groups, GPOs)
- Naming conventions (accounts, machines, groups)
- Planned PowerShell scripts (account creation, folder tree with NTFS rights)
- Share tree and access rights matrix

---

## IS Architecture Overview

| Component | Solution |
|---|---|
| Directory Service | Windows Server – Active Directory |
| File Sharing | File Server with NTFS permissions |
| User Management | AD Groups per department |
| Cloud Collaboration | Google Workspace (Drive, Meet, Gmail) |
| Platform Hosting | External provider (outsourced) |
| OS Migration | Windows 8 → Windows 11 (2-year roadmap) |

---

## Access Rights Matrix

| Group | Common | Management | HR | Accounting | Sales | Support |
|---|---|---|---|---|---|---|
| Management | RW | RW | RW | RW | RW | RW |
| HR | RW | | RW | R | | |
| Accounting | RW | | R | RW | R | |
| Sales | RW | | | | RW | R |
| Support | RW | | | R | | RW |

---

## Key Security Measures

- **Password policy** enforced via GPO
- **Automatic workstation lock** after inactivity
- **USB storage banned** (replaced by secure network shares)
- **Restricted system settings** access for standard users
- **Regular cybersecurity awareness** campaigns

---

## PowerShell Scripts (planned)

- `New-GreenResoUser.ps1` — HR-facing script to create AD accounts, assign groups, and provision personal folders
- `New-FolderTree.ps1` — Automatically creates department folder structure with correct NTFS permissions

---

## Contributors

| Name | Role |
|---|---|
| Manil Doudou | Developer |
| Maxime Moysset | Developer |
| Youcef Djarir | Developer |
| Quentin Chabres | Developer |

---

## License

Copyright © 2026 **GreenReso**. All rights reserved.

This software is proprietary and confidential. Unauthorized copying, distribution, modification, or use of this software, in whole or in part, is strictly prohibited without prior written consent from GreeReso.
