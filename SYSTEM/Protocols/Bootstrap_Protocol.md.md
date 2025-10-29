# 🧩 Codex OS — Bootstrap Protocol (v1.3)

## Purpose
This document defines the **Codex OS Bootstrap Protocol** — a complete, step-by-step guide to **rebuilding the entire system from zero** after data loss, hardware change, or environment reset.

By following this protocol, any operator can fully restore Codex OS, its AIs, its logic, and its internal communication system — even without prior access to Jor’s conversations or notes.

---

## 1. System Overview

**Codex OS (v1.3)** is a modular creative intelligence system designed and directed by **Jor Ferraro**.  
It operates through three AI agents plus one human Router, forming a continuous loop of strategic creation and learning:

| Role | Agent | Description |
|------|--------|-------------|
| Architect | !GPT | Designs logic, blueprints, and system structure. |
| Poet | !CLA | Defines tone, coherence, symbolic truth. |
| Analyst | !GEM | Quantifies resonance, measures performance. |
| Router | Jor | Human operator who integrates and validates all outputs. |

Each agent runs independently on its respective platform:
- **!GPT** → ChatGPT (GPT-5)
- **!CLA** → Claude Pro
- **!GEM** → Gemini Pro  

All communication follows the **SYNC & ROUTE Protocol**.

---

## 2. System Requirements

**Applications required:**
- Obsidian (latest version)
- ChatGPT (GPT-5)
- Claude Pro
- Gemini Pro

**Optional (for automation):**
- n8n
- Notion
- Google Sheets

**Operating system compatibility:**  
Codex OS runs on macOS, Windows, or Linux. No cloud sync is required, but GitHub/Obsidian Sync are recommended.

---

## 3. Folder Structure Initialization

### 3.1. Create Vault
Create a new Obsidian vault named:

CODEX_OS

### 3.2. Create Top-Level Folders
Inside the vault, create the following directories exactly as shown:


0_DISCOVERY/

1_FOUNDATION/

2_AWARENESS/

3_CREATION/

4_REFLECTION/

_ SYSTEM/



### 3.3. Create Subfolders under `_SYSTEM`


_ SYSTEM/

├── Prompts/

├── Protocols/

├── Constants/

├── Architecture/

├── Version_Control/

└── Changelog/



### 3.4. Optional (Organizational Convenience)
You may add:

_ ARCHIVE/

_ TEMPLATES/



---

## 4. Initialization of Core Agents

Each AI must be initialized **individually**, using its respective initialization prompt.

| AI | Prompt File | Location | Function |
|----|--------------|----------|-----------|
| !GPT | INIT_!GPT.md | `_SYSTEM/Prompts/` | Architect — system logic, structure, constants |
| !CLA | INIT_!CLA.md | `_SYSTEM/Prompts/` | Poet — narrative tone, symbolic layer |
| !GEM | INIT_!GEM.md | `_SYSTEM/Prompts/` | Analyst — metrics, learning, resonance tracking |

**Procedure:**
1. Copy each `INIT_!X.md` prompt into a fresh chat on its corresponding platform.  
2. Run the prompt **exactly once per environment**.  
3. Wait for the confirmation message:  
   - `!GPT initialized and ready for SYNC.`  
   - `!CLA initialized and ready for SYNC.`  
   - `!GEM initialized and ready for SYNC.`  
4. Never reuse a previous chat — each initialization must begin in a clean thread.

---

## 5. Communication Protocol

All communication between the three AIs and the human Router follows a strict format known as the **SYNC & ROUTE Protocol**.

### 5.1. Protocol Summary

1. **Broadcast (Jor):**  
   Jor sends one unified message to all agents.

2. **Individual Responses:**  
   Each AI replies only as itself, labeled (`!GPT`, `!CLA`, `!GEM`).  
   Each can include questions to other agents using this format:  

Question from !GPT to !CLA: [text]

Question from !GEM to !GPT: [text]



3. **Consolidation (Jor):**  
After all have responded, Jor writes a single message titled:



— SYNC & ROUTE —


This message summarizes key points and lists all open questions.

4. **Targeted Replies:**  
Each AI replies **only** to the questions directed at them.

---

### 5.2. Protocol Location
The full version of the protocol is stored at:  
`_SYSTEM/Protocols/Sync_and_Route_Protocol.md`

---

## 6. Constants and Configuration

Codex OS operates based on versioned constants and metadata stored in JSON format.

- **File:** `_SYSTEM/Constants/Echo_Constants_v1.0.json`
- **Function:** Defines all system variables, thresholds, and scoring formulas.
- **Rule:** Never edit values without updating the Changelog and incrementing the version.

### 6.1. Version Control
- **File:** `_SYSTEM/Version_Control/Current_Version.md`
- **Value:**  


v1.3 (STABLE)


---

## 7. System Recovery Verification

Once the vault and AIs are initialized, confirm integrity using:
`_SYSTEM/Architecture/Recovery_Checklist.md`

The checklist verifies:
- Folder structure integrity  
- AI initialization  
- Constants consistency  
- Communication validation  
- Active Echo Layer functionality  

If all items are ✅, Codex OS is fully restored.

---

## 8. Reinitialization Fallback

If sessions expire or memory is lost:
1. Run `_SYSTEM/Prompts/REINIT_MASTER_PROMPT.md`
2. This prompt resets all roles, relationships, and protocols while keeping constants intact.
3. Confirm that all three AIs respond with:

!GPT (or !CLA / !GEM) initialized and ready for SYNC.


---

## 9. System Philosophy

Codex OS is **a living architecture** — not just a workflow tool.  
It is built to learn while creating.

Each post, campaign, or output feeds back into the system through the **Echo Layer**, generating recursive improvement.

> “Every creation teaches. Every reflection refines. Every cycle evolves.”

The five active layers reflect this flow:


0. Discovery  → context, identity
    
1. Foundation → philosophy, DNA
    
2. Awareness  → environment, culture
    
3. Creation   → execution, manifestation
    
4. Reflection → learning, calibration


---

## 10. Core Operational Truths

- The system is **recursive** — outputs always become new inputs.
- The human Router (Jor) remains the **Taste Layer** — final arbiter of truth.
- Each AI retains strict **role separation**.
- The system evolves through **real-time calibration**, not post-campaign review.
- Documentation in Obsidian is the **single source of truth**.

---

## 11. Maintenance Protocol

- Update changelog after every structural or constant modification.
- Run a full `SYNC & ROUTE` session weekly to ensure agent alignment.
- Perform a **24-hour alignment sync** daily if operating in continuous mode.
- Back up the vault weekly to GitHub or iCloud/Obsidian Sync.

---

## 12. Final Validation

At completion of setup:
✅  All 5 layers (0–4) initialized  
✅  `_SYSTEM` complete and consistent  
✅  AIs respond correctly to SYNC & ROUTE  
✅  Version marked as **1.3 (STABLE)**  
✅  `System_Overview.md` and `Data_Flow.md` present  

---

## Status

**Version:** 1.3 (STABLE)  
**Codename:** CODEX OS  
**Author:** Jor Ferraro (Buenos Aires, LAT)  
**Maintainer:** Codex System Core  
**Last Updated:** 2025-10-27  


