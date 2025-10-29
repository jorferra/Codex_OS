# ⚙️ Post Generation Protocol — Codex OS  
**Layer:** 3 — Creation / Remix Engine  
**Version:** 1.2  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Post Generation Protocol** defines how Codex synthesizes new creative outputs by fusing validated patterns (from the Pattern Library) with current platform signals and contextual data.

This process converts **learning into creation**, ensuring that every new piece of content reflects accumulated intelligence, tone coherence, and rhythm awareness.

Codex does not produce content — it **recreates alignment**.

---

## 2. System Context

5_PATTERN_LIBRARY → 3_CREATION → 4_REFLECTION


The Remix Engine uses validated pattern blueprints and real-time platform data to auto-generate or assist in building creative assets (posts, reels, carousels, scripts, etc.).  
Its goal is not automation for speed, but **continuity of intent**.

---

## 3. Core Inputs

| Input | Source | Description |
|--------|---------|-------------|
| **Pattern Blueprint** | `/5_PATTERN_LIBRARY/Blueprints/` | Core creative DNA to be reused. |
| **Platform Signals** | `/2_AWARENESS/Platform_Intelligence/` | Algorithmic preferences and audience behavior. |
| **Cultural Radar** | `/2_AWARENESS/Cultural_Radar.md` | Trending emotional or narrative cues. |
| **Router Brief** | `/1_FOUNDATION/Operating_Blueprints/` | Human intention and campaign objective. |
| **Echo Feedback** | `/4_REFLECTION/EchoReports/` | Resonance and timing data from past cycles. |

---

## 4. Core Outputs

| Output | Destination | Description |
|---------|--------------|-------------|
| **Post_Brief (v2.2)** | `/3_CREATION/Content_Queue/[Client]/Week_YYYY-MM-DD/` | Draft file containing concept, caption, tone, and visual notes. |
| **Job_Packet.json** | `/3_CREATION/Job_Packets/` | Technical asset request + metadata for post-production. |
| **Taste_Profile_Update** | `/4_REFLECTION/EchoReports/` | Micro-adjustment to stylistic parameters after publication. |

---

## 5. Workflow Overview



1. Fetch latest validated pattern
    
2. Merge with current platform and cultural data
    
3. Cross-check timing and resonance with Echo metrics
    
4. Generate Post_Brief (v2.2)
    
5. Produce Job_Packet.json for media team or automation tools
    
6. Publish → Reflect → Feed back to Echo Layer

---

## 6. Generation Logic

Codex combines **Pattern**, **Context**, and **Platform** as follows:

```text
Post_Output = (Pattern_Essence × Context_Signal) + Platform_Modifiers


```

Where:

- Pattern_Essence = validated creative DNA (tone, rhythm, visual logic)
    
- Context_Signal = current cultural or thematic trend relevance
    
- Platform_Modifiers = algorithmic adjustments (caption length, aspect ratio, timing)
    

---

## **7. AI Role Distribution**


|**Role**|**Agent**|**Function**|
|---|---|---|
|**Architect**|!GPT|Structural clarity, synthesis, post logic|
|**Poet**|!CLA|Tone, rhythm, emotional coherence|
|**Analyst**|!GEM|Timing optimization, platform prediction|


**Router:** validates, curates, and approves all final outputs.

---

## **8. Post_Brief Template (v2.2)**


---
post_id: CDX_POST_2025_11_SB_0008
client: Sandra Borghi
pattern_source: CDX_PATTERN_2025_11_SB_004
objective: "Reinforce tone of quiet authority while maintaining human warmth."
theme: "Resonant Minimalism"
tone: "Warm Precision"
platform: "Instagram"
recommended_posting_time: "2025-11-02 09:00 AM ART"
key_message: "Presence is not pressure."
caption_length_bin: short
hashtags: ["#Codex", "#MindfulWork", "#Resonance"]
visual_guidelines:
  ratio: "4:5"
  mood: "soft contrast, neutral background"
cta_style: "Soft invitation"
approval_status: "pending_router"




## **Example Caption (es-AR):**

  

> A veces, el silencio dice todo.

>   

> Lo importante no es hablar más, sino sostener lo que decís con calma.

>   

> #Resonancia #Codex

---

## **9. Job_Packet.json Example**

json
{
  "job_id": "CDX_JOB_2025_11_003",
  "post_id": "CDX_POST_2025_11_SB_0008",
  "media_type": "carousel",
  "slides": 3,
  "assets_required": ["image_1", "quote_slide", "cta_slide"],
  "deadline": "2025-10-30T23:59:00Z",
  "responsible": "CDX_ContentOps",
  "automation_trigger": "n8n_RemixFlow_v1"
}


## **10. Timing Optimization Integration**

|**Metric**|**Source**|**Adjustment**|
|---|---|---|
|**Momentum Index**|/4_REFLECTION/Momentum_Index/|Delays or accelerates post cadence.|
|**Echo Vector**|/4_REFLECTION/Echo_Layer/|Adjusts resonance-based posting times.|
|**Platform Boost Windows**|/2_AWARENESS/Platform_Intelligence/|Aligns with optimal posting periods.|



_Reference:_ /3_CREATION/Remix_Engine/Timing_Optimization_Protocol.md

---

## **11. Automation Hooks (n8n)**


|**Node**|**Function**|
|---|---|
|**Pattern Fetcher**|Retrieves latest validated pattern.|
|**Platform Syncer**|Pulls platform data from Awareness Layer.|
|**Post Composer**|Generates Post_Brief and Job_Packet.|
|**Router Dispatcher**|Sends for human approval.|
|**Echo Feedback Sync**|Pushes results to Echo Layer post-publication.|


## **12. File Structure Reference**


/3_CREATION/
├── Content_Queue/
│   ├── [Client]/
│   │   ├── Week_YYYY-MM-DD/
│   │   │   ├── Post_Brief_[ID].md
│   │   │   ├── Media/
│   │   │   └── Notes/
│   │   └── Archive/
├── Job_Packets/
│   ├── Job_Packet_[ID].json
│   └── 00_Readme.md
└── Remix_Engine/
    ├── Post_Generation_Protocol.md   ← this file
    ├── Timing_Optimization_Protocol.md
    ├── Format_Selection_Guide.md
    └── Synthesis_Rules.md


## **13. Metadata**


json
{
  "module_id": "CDX_Creation_PostGeneration_v1.2",
  "parent_phase": "Creation",
  "linked_layers": ["Pattern Library", "Reflection", "Awareness"],
  "update_frequency": "per_post_cycle",
  "status": "active"
}

---

## **14. Operating Philosophy**

  

> Codex doesn’t publish to be seen —

> it speaks when there’s something worth echoing.

>   

> The system is not a megaphone.

> It’s a **resonance instrument**,

> calibrated by attention and truth.

---

**Next Recommended File:**

/3_CREATION/Remix_Engine/Format_Selection_Guide.md — defines how Codex selects the most effective content format (reel, carousel, post, story) per pattern and momentum vector.

---

**Version Date:** 2025-10-27

**Status:** **FINAL | Active | Internal**

**Visibility:** Internal Documentation