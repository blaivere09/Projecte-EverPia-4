# COMPLETE VERSION IN ENGLISH

## Phase 1: Individual Work

### a) PHASE 1 POL

**WHAT WILL WE BACK UP?**  
- **Databases:** critical data used daily.  
- **Project Documents:** containing plans and important technical specifications.  
- **User Document Folders:** can contain important work information.  

> It is not necessary to make a complete copy of all users’ personal files (client computers). Only the "Documents" folders need to be copied.

**HOW OFTEN AND IN WHAT WAY?**  
- **Databases:** Incremental backups every 4 hours, full backup weekly.  
- **Project Documents and Personal Folders:** daily differential backup, weekly full backup.  
- **Client computers (Documents folders):** daily incremental backup or synchronization.  

**WHAT MEDIA TO USE AND WHERE TO STORE DATA**  
- **Local Media:** NAS for fast and local backups.  
- **External Media:** Cloud backup (Azure, Google Cloud, or local service) for offsite backup.  
- **External Disks:** monthly/weekly backups (SSDs, HDDs, tapes).  

**3-2-1 Rule:**  
3 copies, 2 different types of media (NAS + Cloud), 1 copy offsite (Cloud).

---

### b) PHASE 1 XAVI

**Data to Back Up (Prioritization)**  
| Data Type | Size | Criticality |
|-----------|------|------------|
| Databases (Accounting/Clients) | 20 GB | Critical, used daily |
| Project Documents | 300 GB | Important, 24-hour RPO |
| Personal Folders | 100 GB | Necessary, less critical |

- **Client Computers:** Only local Documents folders need backup.

**Frequency and Type of Backup**  
| Data Type | Backup Type | Frequency |
|-----------|------------|----------|
| Databases | Incremental | every 4h + full daily |
| Project Documents | Incremental | daily + full weekly |
| Personal Folders | Incremental | daily + full weekly |

**History:** Minimum retention 1 month → weekly/monthly archived backups.  

**Media and Location (3-2-1 Rule)**  
- Local NAS for fast backups.  
- Cloud for offsite backup.  
- External disks for archived backups.  

**3-2-1 Rule:**  
- 3 copies of data (original + 2 backups)  
- 2 different media types (NAS + Cloud)  
- 1 copy offsite (Cloud/external)  
- Most recent backup should be local (NAS) for quick restoration.

---

### c) PHASE 1 BLAI

**WHAT WILL WE BACK UP?**  
- Most important server data: databases (clients/invoices), shared files (documents/projects), server configs, virtual machines, important logs.  
- Client computers only if they contain data not on the server or difficult-to-reproduce configurations.

**HOW OFTEN AND IN WHAT WAY?**  
- **Working days (Mon-Fri):** incremental backup.  
- **Weekly (Saturday):** differential backup.  
- **Monthly:** full backup of all critical server data.

**Media and Location**  
- External drives, NAS, Cloud, tapes if needed.  
- Apply **3-2-1 rule**: 3 copies, 2 media types, 1 offsite copy.

---

### d) PHASE 1 PAU

**Backup Report**  
- Critical server data: project documents, Accounting/Clients database, users’ personal folders.  
- Client computers: only folders with temporarily stored important files.  

**Backup Type:**  
- Accounting/Clients: daily incremental  
- Entire server: weekly full  
- Documentation & personal folders: daily differential  
- Full backup of all data: monthly

**Media:**  
- NAS for centralized, fast backups  
- Cloud copy for offsite recovery

---

## PHASE 2: Work in Couples

### Pol & Pau

**1. Discussion and Consensus**  
- Agreed on data to store.  
- Only “Documents” folders will be backed up, not all personal folders.  
- Response 1 proposes more frequent backups; Response 2 suggests daily backups.  

**2. Development of Unified Proposal**  

| Element | Couple’s Proposal | Justification |
|---------|-----------------|---------------|
| Critical Data | Project Documents, Accounting/Clients Database, Personal Folders | Essential for daily operations |
| Frequency (Databases) | Daily | Allows recovery of recent changes |
| Backup Type (Databases) | Daily incremental, weekly full | Incremental for speed, full for stability |
| Media 1 (Local) | NAS | Fast office recovery |
| Media 2 (External) | Cloud | Offsite recovery, 3-2-1 rule compliance |

---

### Xavi & Blai

**1. Discussion and Consensus**  

| Aspect | Xavi | Blai | Similarities / Differences |
|--------|------|------|----------------------------|
| What to back up | Databases, project docs, personal folders | Databases, documents, server config, user accounts, permissions, VMs, logs | Agree on not backing up all client computers; Blai adds configs/logs |
| Frequency | Databases: incremental every 4h + daily full; Docs/folders: daily incremental + weekly full | Daily incremental (Mon–Fri), weekly differential (Sat), monthly full | Xavi meets 4h RPO, Blai more generic |
| Backup type | Incremental + full | Incremental + differential + full | Xavi adapts to RPO/RTO, Blai standard |
| Media & location | NAS + Cloud + external disks | External disks + NAS + Cloud + tapes | Blai adds tapes for long-term storage |

**2. Unified Proposal**  

| Element | Couple’s Proposal | Justification |
|---------|-----------------|---------------|
| Critical Data | Accounting/Clients Databases, Project Documents, Personal Folders | Essential; databases have strict RTO/RPO |
| Frequency (Databases) | Incremental every 4h + daily full | No more than 4h of work lost, fast restoration |
| Backup Type (Databases) | Incremental + Full | Incrementals fast, full backups solid restore points |
| Media 1 (Local) | NAS | Fast access & immediate restoration |
| Media 2 (External) | Cloud | Protects against physical disasters, offsite availability |

---

## Phase 3: Group Work

**Discussion and Selection**  
- Both proposals prioritize critical data (databases, project docs, personal folders).  
- Pol/Pau plan: easier daily implementation, quick recovery, low cost.  
- Xavi/Blai plan: RPO/RTO focused, long-term and diversified media, more complex and costly.

**Design of Final Policy**  
- Protect project documents, Accounting/Clients database, users’ personal folders.  
- **Backup Strategy:**  
  - Accounting/Clients: daily incremental + weekly full  
  - Documentation/personal folders: daily differential, monthly full  
- **Media:**  
  - NAS in office for fast recovery  
  - Cloud for offsite copy

---

## Final Document (Phase 3)

**Data to be Backed Up**

**Server Side:**  

| Data Type | Critical | Backup Frequency |
|-----------|---------|-----------------|
| Databases (Accounting/Clients) | ✅ | Incremental every 4h + full daily |
| Project Documents | ✅ | Daily incremental + full weekly |
| Users’ Personal Folders | ❌ | Daily incremental + full weekly |

**Client Machines:**  

| Data Type | Critical | Backup Frequency |
|-----------|---------|-----------------|
| Temporary local documents | ❌ | Not backed up (save on server) |
| Special configurations | ✅ (if any) | One-time backup if difficult to recover |

- Separate backups by **Server/Clients** and **critical/non-critical**  
- Include a **Detailed Weekly Schedule**

