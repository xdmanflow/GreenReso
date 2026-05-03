# GreenReso – IS Security Project

> Information System design & cybersecurity project developed for **GreenReso** — built for enterprise-grade infrastructure and data security.

---

## Table of Contents

- [About the Project](#about-the-project)
- [Project Roadmap](#project-roadmap)
- [Deliverables](#deliverables)
- [IS Architecture Overview](#is-architecture-overview)
- [Access Rights Matrix](#access-rights-matrix)
- [Key Security Measures](#key-security-measures)
- [Technical Requirements](#technical-requirements)
- [Project Structure](#project-structure)
- [Team & Contributions](#team--contributions)

---

## About the Project

GreenReso is a French IoT company founded in 2019 in Nantes, with 40 employees across 3 sites and 5 departments. It designs and manages smart sensors to optimize office energy consumption, growing at 25% annually. Its SaaS platform, GreenPilot, provides real-time energy monitoring for clients including public institutions and major corporations. Despite this growth, its Information System was poorly structured (no centralized user management, weak security practices, manual backups). After a data leak, the company launched a project to professionalize its IT infrastructure—focusing on security, document organization, and employee experience, while aligning with digital sustainability principles.

### Project Scope

| Item | Details |
|------|---------|
| Company | GreenReso |
| Founded | 2019 — Nantes, France |
| Employees | 40 across 5 departments |
| Sites | 3 locations |
| Platform | GreenPilot (outsourced hosting) |
| Annual Growth | 25% |

---

## Project Roadmap

| Deliverable | Focus | Status |
|-------------|-------|--------|
| **Deliverable 1** | Infrastructure diagram — logical network view, servers, segmentation | ✅ Completed |
| **Deliverable 2** | Cybersecurity awareness document for non-IT employees | ✅ Completed |
| **Deliverable 3** | Technical mock-up — AD, GPOs, PowerShell scripts, share tree | ✅ Completed |

---

## Deliverables

### Deliverable 1 — Infrastructure Diagram 
A logical network view of GreenReso's target IS architecture, including:

- Active Directory, File Server, DNS
- Network segmentation by department
- Distribution of workstations across the three sites
- Main servers and their roles

### Deliverable 2 — Cybersecurity Awareness Guide 

A non-technical document aimed at all GreenReso employees, covering:

- Clear presentation of common digital threats (phishing, weak passwords, data leaks...)
- Simple, actionable countermeasures for every employee profile
- Designed for use during onboarding sessions or team meetings

### Deliverable 3 — Final Technical Report 

A comprehensive technical document detailing:

- Active Directory structure (OUs, Security Groups, GPOs)
- Naming conventions for accounts, machines, and groups
- PowerShell automation scripts (account creation, NTFS folder provisioning)
- Share tree and full access rights matrix

---

## IS Architecture Overview

| Component | Solution |
|-----------|----------|
| Directory Service | Windows Server — Active Directory |
| File Sharing | File Server with NTFS permissions |
| User Management | AD Security Groups per department |
| Cloud Collaboration | Google Workspace (Drive, Meet, Gmail) |
| Platform Hosting | External provider (outsourced) |
| OS Migration | Windows 8 → Windows 11 (2-year roadmap) |

---

## Access Rights Matrix

| Group | Common | Management | HR | Accounting | Sales | Support |
|-------|--------|------------|----|------------|-------|---------|
| **Management** | RW | RW | RW | RW | RW | RW |
| **HR** | RW | | RW | R | | |
| **Accounting** | RW | | R | RW | R | |
| **Sales** | RW | | | | RW | R |
| **Support** | RW | | | R | | RW |

> `RW` = Read & Write — `R` = Read only — *(empty)* = No access

---

## Key Security Measures

| Measure | Description |
|---------|-------------|
| Password Policy | Enforced via Group Policy Objects (GPO) |
| Workstation Lock | Automatic lock after inactivity period |
| USB Ban | Removable storage banned; replaced by secure network shares |
| System Access | Standard users restricted from system settings |
| Awareness | Regular cybersecurity awareness campaigns for all profiles |
| Backups | Automated and structured backups replacing manual external drives |

---

## Technical Requirements

| Constraint | Requirement |
|------------|-------------|
| Directory Service | Windows Server — Active Directory |
| Architecture | Organizational Units (OUs) per department |
| Group Policy | GPOs for security, lock screens, USB restriction |
| Scripting | PowerShell — all scripts written in English |
| Naming Convention | Standardized for accounts, groups, and machines |
| OS | Windows 11 target (migration from Windows 8 over 2 years) |
| Versioning | Git / GitHub |

---

## Project Structure

```
greenreso/
├── Final Infrastructure Diagram.pdf                 # Network & IS architecture diagram
├── Final Report of the IS Security Project.pdf      # Full technical report
├── GreenReso_Cybersecurity_Awareness_Guide.docx     # Awareness document for employees
└── README.md
```

---

## Team & Contributions

This project was developed by the following team:

| Name | Role |
|------|------|
| Manil Doudou | Developer |
| Maxime Moysset | Developer |
| Youcef Djarir | Developer |
| Quentin Chabres | Developer |

### Workflow Guidelines

- All work branches must be created from `main` or `develop`
- Branch naming: `feature/<feature-name>`, `fix/<issue-name>`
- Commit messages must be clear, concise, and written in English
- Pull Requests require peer review before merging
---

## License

Copyright © 2026 **GreenReso**. All rights reserved.

This software is proprietary and confidential. Unauthorized copying, distribution, modification, or use of this software, in whole or in part, is strictly prohibited without prior written consent from GreenReso.
