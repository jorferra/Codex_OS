# Echo Report Workflow — Codex (CDX) v1.3

### PURPOSE  
Define the step-by-step process of generating and integrating Echo Reports.

---

## 1️⃣ INPUTS
- Post performance data (platform metrics)  
- Human qualitative notes (`taste_alignment`, `symbolic_clarity`)  
- Caption + visual context  

---

## 2️⃣ PROCESS FLOW
1. **!GEM:** compiles raw metrics into `EchoReport.json`.  
2. **!CLA:** reviews symbolic and emotional resonance.  
3. **!GPT:** integrates learning into new Post_Briefs.  
4. **Jor:** validates and finalizes calibration.  

---

## 3️⃣ DATA STORAGE
- `/4_REFLECTION/EchoReports/[Client]/[Week]/EchoReport_[ID].json`  
- `/4_REFLECTION/EchoReports/[Client]/[Week]/Calibration_Report_[ID].md`  
- `/4_REFLECTION/Echo_Layer/Divergence_Log.md`  

---

## 4️⃣ LEARNING LOOP (SIMPLIFIED)
```
EchoReport → Divergence Analysis → Learning Update → Remix Engine → New Brief
```

---

## 5️⃣ DAILY SYNTHESIS FIELD
Each day, the system generates:
```yaml
date: YYYY-MM-DD
client: ""
posts_analyzed: []
brilliant_misfires: 0
hollow_hits: 0
learning_summary: ""
next_actions: ""
```

Saved as `/4_REFLECTION/Echo_Layer/Daily_Summary_[date].md`.  



**FINAL | Active | Operational**


