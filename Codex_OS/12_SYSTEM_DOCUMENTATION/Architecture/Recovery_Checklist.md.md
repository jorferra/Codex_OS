# 🧭 Recovery_Checklist.md  
**Codex OS v1.3 — System Recovery Protocol**

---

## 1. Purpose

This document defines the **official recovery procedure** for Codex OS (CDX).  
It ensures the system can be fully restored and re-synchronized after loss of data, hardware, or AI state.  

The recovery process applies to:
- Local vault or file corruption.  
- AI desynchronization (!GPT, !CLA, !GEM losing context or memory).  
- Version mismatch or Echo layer drift.  
- Hardware or system migration to a new device.

The goal: **Rebuild Codex OS to full operational capacity** with minimal loss of continuity or integrity.

---

## 2. Recovery Phases Overview

| Phase | Objective | Responsible Entity |
|-------|------------|--------------------|
| Phase 1 | Recreate Vault Structure | Human Operator (Jor / Router) |
| Phase 2 | Reactivate AIs and Reinitialize Prompts | Human Operator |
| Phase 3 | Validate Core Constants and Protocols | !GPT |
| Phase 4 | Restore Functional Data | !GEM |
| Phase 5 | Verify System Coherence | !CLA + !GPT |
| Phase 6 | Resume Live Sync | All layers |

---

## 3. Phase 1 — Recreate Vault Structure

### **1.1. Folder Hierarchy**

Recreate the following top-level structure in Obsidian or equivalent environment:



Codex_OS/

├── 0_DISCOVERY/

├── 1_FOUNDATION/

├── 2_AWARENESS/

├── 3_CREATION/

├── 4_REFLECTION/

├── 12_SYSTEM_DOCUMENTATION/

└── SYSTEM/



**Verification:**  
Ensure `_SYSTEM/Constants/Echo_Constants_v1.0.json` exists — it is the **single source of truth** for all calibration data.  

If missing, restore from any backup or Echo Report copy.

---

## 4. Phase 2 — Reactivate AI Roles

### **2.1. Reload Initialization Prompts**
For each AI, open the corresponding initialization file and paste into a new session:




_SYSTEM/Prompts/INIT_!GPT.md

_SYSTEM/Prompts/INIT_!CLA.md

_SYSTEM/Prompts/INIT_!GEM.md





### **2.2. Confirm Initialization**
Each AI must reply with:




!GPT initialized and ready for SYNC.

!CLA initialized and ready for SYNC.

!GEM initialized and ready for SYNC.




### **2.3. Reconnect Communication**
Run a **SYNC & ROUTE test** by broadcasting this message:




— SYNC & ROUTE TEST —

Jor to all layers:

Please confirm Codex OS initialization and readiness to restore data flow.

— END TEST —



All AIs must respond with confirmation.  
If one fails to initialize correctly, re-paste its INIT prompt and restart the session.

---

## 5. Phase 3 — Validate Core Constants and Protocols

### **3.1. Verify Constants**
Open `_SYSTEM/Constants/Echo_Constants_v1.0.json`.  
Ensure the following key values exist:

```json
{
  "sample_window_hours": 72,
  "caption_length_bins": [200, 350, 550, 700],
  "sincerity_bands": [40, 70],
  "momentum_index_window": 4
}



```
### **3.2. Validate Protocols**

  

Check _SYSTEM/Protocols/ folder for:

- Bootstrap_Protocol.md
    
- Daily_Sync_Protocol.md
    
- Sync_and_Route_Protocol.md
    

  

If any are missing, re-import from the documentation repository or last Echo backup.



## **6. Phase 4 — Restore Functional Data**

  

### **4.1. Foundation → Reflection Hierarchy**

  

Confirm each phase folder contains its 00_Readme.md and key files:

- Philosophical_Genome/
    
- Platform_Intelligence/
    
- Content_Queue/
    
- EchoReports/
    

  

### **4.2. Restore Active Projects**

  

Recreate the Job_Packets and Post_Briefs from the last available copy.

If unavailable, manually regenerate using:



Post_Brief_Generator_v2.1.md
Calibration_Report_Template_v1.0.md




### **4.3. Reintegrate Echo Data**

  

Copy the most recent EchoReports/ and Calibration_Reports/ into:


4_REFLECTION/


These will seed the Echo Layer with last known learning state.

---

## **7. Phase 5 — Verify System Coherence**

  

Run a **manual SYNC & ROUTE** cycle:

1. !GPT → Verify architecture and dependencies.
    
2. !CLA → Confirm symbolic and narrative coherence.
    
3. !GEM → Validate constants and analytics schemas.
    
4. Jor → Consolidate responses and confirm “Codex OS restored” status.
    

  

**Expected confirmation output:**


System coherence verified.
Codex OS v1.3 is operational.


## **8. Phase 6 — Resume Live Sync**

1. Restart **Daily Sync Protocol** (scheduled every 24h).
    
2. Re-enable Echo Layer data capture (Reflection phase).
    
3. Validate that new Post_Briefs automatically populate metadata fields:
    
    - taste_profile_target
        
    - caption_length_bin
        
    - learning_link
        
    
4. Run the first new Echo Report within 72 hours to verify calibration.
    

---

## **9. Optional: Migration to a New Device**

  

When moving Codex OS to a new computer:

1. Copy the entire Codex_OS/ vault folder.
    
2. Reinstall Obsidian, Notion, or linked automation tools (n8n, Sheets).
    
3. Verify the structure using 12_SYSTEM_DOCUMENTATION/Architecture/Data_Flow.md.
    
4. Run the full **Bootstrap Protocol** to reinitialize AI agents.


## **10. Emergency Backup Protocol**


|**Type**|**Location**|**Frequency**|**Notes**|
|---|---|---|---|
|System Constants|_SYSTEM/Constants/|Weekly|Export as .json|
|Echo Reports|4_REFLECTION/EchoReports/|72h|Archive in cloud|
|Calibration Reports|4_REFLECTION/Calibration_Reports/|Weekly|Keep last 5 versions|
|Entire Vault|/Codex_OS/|Monthly|Store offline backup|


## **11. Success Criteria**

  

Codex OS is considered **fully restored** when:

- All AIs confirm initialization and synchronization.
    
- Echo Layer produces valid reports.
    
- Constants match the last known version.
    
- Creation → Reflection feedback loop is functional.
    
- Daily Sync executes without error.


**Status:** ✅ Finalized

**Version:** Codex OS v1.3

**Maintainer:** Jor Ferraro

**Last Updated:** 2025-10-27


