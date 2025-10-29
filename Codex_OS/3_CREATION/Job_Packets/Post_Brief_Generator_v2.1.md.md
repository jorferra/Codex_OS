# 🧩 Post Brief Generator — Codex OS  
**Layer:** 3 — Creation  
**Version:** 2.1  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Post Brief Generator** transforms Codex’s strategic awareness into creative execution.  
It ensures that every piece of published content is born from system insight, not improvisation.

A **Post Brief** is a micro-strategy — a single, executable creative unit within Codex’s learning engine.  
Each brief carries creative direction, emotional tone, platform specs, and performance hypotheses ready for Echo feedback.

---

## 2. Input Sources

| Layer | Input File | Role |
|--------|-------------|------|
| **2 — Awareness** | `Trend_Map_Template.md` | Provides macro creative triggers. |
| **2 — Awareness** | `Audience_Signals_Template.md` | Provides qualitative resonance insights. |
| **2 — Awareness** | `Cross_Platform_Strategy.md` | Provides technical and distribution parameters. |
| **4 — Reflection** | `Echo_Report.json` | Feeds real performance learnings into new briefs. |

All inputs are processed through the Router (Jor) or via automation (n8n/Sheets) before a new Post_Brief is generated.

---

## 3. Post_Brief Structure

Each brief lives in its own folder:  
`/3_CREATION/Briefs/[YYYY-MM-DD]_[Client]_[Topic]/`

Inside, Codex generates the following files:


📁 [YYYY-MM-DD]_SandraBorghi_SelfReflection/

├── Post_Brief.json

├── caption.txt

├── hashtags.txt

├── assets/ (images or videos)

└── notes.md

---

## 4. Post_Brief.json Schema

```json
{
  "brief_id": "CDX_BRIEF_SB_2025_10_27_001",
  "client": "Sandra Borghi",
  "topic": "Self-Reflection in Leadership",
  "objective": "Drive engagement through authenticity and emotional authority.",
  "platform": "Instagram",
  "format": "Reel",
  "caption_length_bin": "Medium",
  "taste_profile_target": ["Grounded", "Reflective"],
  "creative_direction": "Stillness as strength. Tone: calm, direct, honest.",
  "trend_link": "CDX_Awareness_TrendMap_2025_10_20_CalmRebellion",
  "audience_signal_ref": "CDX_AudienceSignals_SB_2025_10_25",
  "hypothesis": "Short, grounded monologues about stillness outperform high-energy inspiration reels.",
  "expected_sincerity_band": "High",
  "publish_date": "2025-10-29",
  "router": "Jor Ferraro",
  "created_by": "!GPT",
  "validated_by": "!CLA",
  "monitored_by": "!GEM",
  "learning_link": "EchoReport_2025_10_31"
}


```

## **5. Workflow Overview**


Trend_Map + Audience_Signals + Platform_Data  
→ Post_Brief (creation)  
→ Published Content  
→ Echo_Report (reflection)  
→ Calibration → next brief iteration


This recursive loop ensures that every new piece of content is both an _execution_ and an _experiment_.


## **6. 70/30 Model — Exploit vs Explore**

  

Codex follows the **70/30 principle** for creative evolution:


|**Category**|**Description**|**% Allocation**|
|---|---|---|
|**Exploit**|Content formats and tones already validated by the system.|70%|
|**Explore**|New creative hypotheses to test resonance or expand brand voice.|30%|


This balance maintains stability (brand continuity) and discovery (innovation).


## **7. Caption Framework (by !CLA)**

  

Each caption follows the **Codex Three-Act Structure**:

|**Section**|**Description**|**Example (es-AR)**|
|---|---|---|
|**Act I – Hook (2–3 lines)**|Introduces human tension or paradox.|“El silencio no es vacío. Es el lugar donde las ideas respiran.”|
|**Act II – Insight (4–6 lines)**|Builds context or reveals personal truth.|“Nos enseñaron a llenar cada pausa. Pero el poder no está en decir más, sino en decir mejor.”|
|**Act III – Closure (1–2 lines)**|Emotional synthesis or call to stillness/action.|“No corras. Afiná tu frecuencia.”|


**Length bins:**

- Short (200–350 chars)
    
- Medium (351–550)
    
- Long (551–700)
    

  

!CLA validates emotional tone and ensures alignment with taste_tags (Grounded, Vulnerable, Reflective, etc.).

---

## **8. Validation Protocol**

  

Each Post_Brief must go through the following checkpoints:

|**Step**|**Responsible**|**Output**|
|---|---|---|
|1|!GPT|Generates structure + hypothesis|
|2|!CLA|Validates narrative tone + caption coherence|
|3|!GEM|Assigns expected sincerity band and performance baseline|
|4|Router (Jor)|Approves publication and schedules distribution|


After publication, performance data flows back into the **Echo Layer** for learning.

---

## **9. Integration with n8n Automation**

|**Node**|**Description**|
|---|---|
|**Input Trigger**|New Post_Brief.json created in /Briefs/ folder|
|**Formatter**|Normalizes JSON fields for Google Sheets|
|**Distributor**|Sends caption + assets to platform APIs|
|**Echo Tracker**|Captures performance after 72h window|
|**Updater**|Writes summary into Echo_Report.json|

## **10. Metadata**

{
  "module_id": "CDX_Creation_PostBriefGenerator_v2.1",
  "parent_phase": "Creation",
  "linked_layers": ["Awareness", "Reflection"],
  "update_frequency": "per_post",
  "status": "active"
}

## **11. Operating Philosophy**

  

> Creation without reflection is waste.

> Reflection without creation is theory.

> Codex builds the loop that keeps both alive — continuously learning, continuously refining.

---

**Next Recommended File:**

/3_CREATION/Job_Packet_Template.md — defines how Post_Briefs expand into multi-post or campaign structures for extended executions.

---

**Version Date:** 2025-10-27

**Status:** Active

**Visibility:** Internal Documentation
