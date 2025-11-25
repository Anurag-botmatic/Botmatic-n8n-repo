# 🚀 DVDC AI Agents – Data Validation & Cleaning Automation Pipeline

This repository contains the core AI agents powering the **DVDC (Data Validation & Data Cleaning)** automation system.  
The pipeline uses a **multi-agent execution strategy** to maximize accuracy, consistency, and reliability across high-volume validation workloads.

---

## 🔥 Agents Overview

### 🟢 **AI Agent 4 — Production Bot (Radar User Assignment: User A)**
### 🟢 **AI Agent 2 — Production Bot (Radar User Assignment: User B)**
**Important Note:**  
**AI Agent 4 and AI Agent 2 are the *same underlying agent/model*.**  
They have identical logic, configuration, and behavior — the only difference is:

- **Agent 4 is assigned to User A in Radar**  
- **Agent 2 is assigned to User B in Radar**

This allows DVDC to:

- Run parallel validation jobs  
- Load-balance work between two user-owned agent accounts  
- Reduce rate limits or throttling issues  
- Enable redundancy & cross-verification across users  

### Their Responsibilities (Both Agents)
Both agents perform:

- High-precision data validation  
- Cleaning & normalization of messy input  
- Structural corrections  
- Business-rule validation for DVDC formats  
- Field inference & missing-data estimation  
- Providing stable outputs for downstream steps  

In the pipeline, they behave like two separate production workers, even though they share the same brain.

---

## 🟡 **All-Response-Agent — Workflow Call Agent**
The **All-Response-Agent** is a utility-focused agent responsible for:

- Fetching external data or raw responses  
- Downloading documents or reference files  
- Triggering external API calls  
- Returning unfiltered AI output for internal use  
- Preparing upstream data before validation begins  

This agent **does not perform validation** — it only collects data needed by Agents 4 & 2.

---

## 🔄 Pipeline Flow

               +------------------------+
               |   All-Response-Agent   |
               |  (Data Gathering Layer)|
               +-----------+------------+
                           |
                           v
         +-----------------+------------------+
         |                                    |
  +------+--------+                   +-------+-------+
  | AI Agent 4    |                   | AI Agent 2    |
  | (User A)      |                   | (User B)      |
  | Same Base LLM |                   | Same Base LLM |
  +------+--------+                   +--------+-------+
         |                                    |
         +-----------------+------------------+
                           |
                           v
             DVDC Validation & Cleaning Engine
                           |
                           v
                   ✅ Cleaned, Verified Data

### ✔ Why Two Agents If They Are the Same?
- Parallel processing  
- Faster batch execution  
- Safety redundancy  
- User-specific rate-limits and quotas  
- Cross-verification for sensitive fields  

---

## 📁 Use Cases
The DVDC agents automate:

- Invoice data validation  
- Vendor & customer master data cleaning  
- Address normalization  
- OCR extraction correction  
- Schema alignment  
- Detecting inconsistencies and anomalies  
- Bulk dataset cleaning for enterprise workflows  

---

## 🧩 Technical Highlights

- Dual-agent configuration with load balancing  
- All agents run via Radar user assignments  
- Multi-step validation & double-pass checks  
- Modular design for pipeline expansion  
- High throughput for batch jobs  
- Stable inference tuned for DVDC schemas  

---

## 📦 Repository Structure


---

## 🛠 Maintainers  
DVDC Automation Engineering Team  

For configuration updates, Radar user permissions, or environment access, contact the internal platform admin.

---

## 📄 License  
Internal proprietary project — not for external distribution.

---
