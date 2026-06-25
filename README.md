![Azure](https://img.shields.io/badge/Microsoft-Azure-0078D4?logo=microsoftazure&logoColor=white)
![AZ-305](https://img.shields.io/badge/Studying-AZ--305-0078D4)
![IaC](https://img.shields.io/badge/Approach-Architecture%20First-2EA44F)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

# azure-lab-projects

Practical Azure labs built while preparing for the **Microsoft Certified: Azure Solutions Architect Expert (AZ-305)** certification.

Every project starts with a real business scenario, walks through the architectural decisions that solve it, and ends with a working deployment in Azure. The goal is to think like an architect, not click like an operator.

---

## How to read this repo

Each project follows the same structure:

1. **Scenario**: a realistic business problem with constraints (budget, compliance, team size, SLA).
2. **Design decisions**: multiple options analysed, the chosen one justified, the others ruled out with technical reasoning.
3. **Architecture diagram**: the resulting solution drawn in Excalidraw.
4. **Implementation**: built in Azure with screenshots of the key resources.
5. **Key learning**: the non-obvious insight that came out of the project.
6. **Cleanup**: every lab is destroyed after the screenshots are taken (cost discipline).

---

## Projects

| # | Project | Area (AZ-305) | Focus | Status |
|---|---------|--------------|-------|--------|
| 01 | [RBAC and Key Vault: Secure Access by Design](./01-rbac-keyvault-secure-access) | Identity & Governance | Least privilege, data plane vs management plane | ✅ Completed |
| 02 | [Network Design by Isolation](./02-network-design-by-isolation) | Infrastructure (Networking) | VNets, NSGs, Private Endpoints, Bastion | ✅ Completed |
| 03 | [Storage Design by Lifecycle](./03-storage-design-by-lifecycle) | Data Storage | Tiering, redundancy, lifecycle policies | ✅ Completed |

---

## Repository structure

```
azure-lab-projects/
├── 01-rbac-keyvault-secure-access/
│   ├── README.md
│   ├── images/
│   └── notes.md
├── 02-network-design-by-isolation/
├── 03-storage-design-by-lifecycle/
└── README.md
```

Every project folder is self-contained and follows the same internal layout.

---

## Stack

| Component | Role |
|-----------|------|
| Microsoft Azure | Cloud platform |
| Microsoft Entra ID | Identity and access management |
| Azure RBAC | Authorization model |
| Azure Key Vault | Secrets, keys and certificates |
| Azure Storage | Blob, File, Queue, Table |
| Azure Virtual Network | Network isolation and segmentation |
| Azure Bastion | Secure administrative access without public IPs |
| Azure SQL Database | Managed relational database |
| Excalidraw | Architecture diagrams |
| Markdown | Documentation |

---

## Topics covered across the portfolio

- Identity and access control with Entra ID and RBAC
- Secret management and data plane separation
- Network segmentation, peering, and private connectivity
- Storage tiering, redundancy, and lifecycle automation
- Cost-aware architecture and resource cleanup discipline

---

## Author

**Adrian Tamargo**, Sysadmin transitioning to Cloud/DevOps Engineering.

[GitHub](https://github.com/AdrianStudio) · [LinkedIn](https://linkedin.com/in/adrian-daniel-tamargo-miller-35a017355)
