# 🎛️ Format Selection Protocol — Codex OS  
**Layer:** 3 — Creation (Remix Engine)  
**Version:** 1.0  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Format Selection Protocol** governs how Codex decides *which content format to deploy* —  
Reel, Carousel, Static Post, or Hybrid — for each creative output.

The choice is not aesthetic; it is *strategic*.  
Every format activates a different form of attention, emotion, and retention.

---

## 2. System Context

Pattern Library → Remix Engine → Format Selection → Post Brief


Format selection bridges the intelligence from the Pattern and Momentum layers with the emotional intent defined by the Router and !CLA.

---

## 3. Format Archetypes

| Format | Strength | Ideal Use Case | Energy Signature |
|---------|-----------|----------------|------------------|
| **Reel** | Motion, immediacy, virality | Emotional ignition, trend riding, micro-stories | High |
| **Carousel** | Depth, education, reflection | Narrative development, teaching, storytelling | Medium |
| **Static Post** | Symbolic clarity | Anchors identity, quotes, key ideas | Low–Medium |
| **Hybrid (Reel + Carousel)** | Narrative + reach | Dual-layer storytelling, multi-format launch | Variable |

Each format serves as a different **attention instrument** within Codex’s orchestration system.

---

## 4. Decision Inputs

| Input | Source | Function |
|--------|---------|----------|
| **Momentum Index (MI)** | Reflection Layer | Detects current system energy |
| **Sincerity Proxy Score (SPS)** | Echo Layer | Evaluates authenticity resonance |
| **Taste Profile** | Meaning Layer (!CLA) | Defines tone and rhythm |
| **Engagement Archetype** | Awareness Layer | Identifies audience behavior pattern |
| **Router Intent** | Manual Input | Aligns with strategic or emotional goals |

---

## 5. Format Selection Logic

### Pseudocode Overview

```text
IF MI >= 0.8 AND SPS >= 0.8 THEN
    FORMAT = "Reel"
ELSE IF MI >= 0.65 AND SPS >= 0.75 THEN
    FORMAT = "Carousel"
ELSE IF MI < 0.65 AND SPS >= 0.85 THEN
    FORMAT = "Static Post"
ELSE
    FORMAT = "Hybrid"
ENDIF




```


**Modifiers:**


|**Modifier**|**Effect**|**Example**|
|---|---|---|
|**Router sets manual override = true**|Forces selected format|Launch events, announcements|
|**Taste Tag = “introspective” or “vulnerable”**|Pushes weight toward Carousel|Reflective storytelling|
|**Trend detected in Awareness Layer**|Prioritizes Reel|Fast-cycle communication|



## **6. Decision Matrix**


|**Momentum (MI)**|**Sincerity (SPS)**|**Recommended Format**|**Notes**|
|---|---|---|---|
|0.85–1.00|0.70–0.85|Reel|Exploit mode — speed and reach|
|0.70–0.85|0.80–0.95|Carousel|Explore mode — narrative depth|
|0.55–0.70|0.85–1.00|Static Post|Reflection — preserve voice and tone|
|<0.55|Any|Hybrid|Re-engage audience or test tonal shift|




## **7. Workflow Sequence**

1. **Fetch Inputs**
    
    - Pull MI and SPS from latest Echo + Momentum Reports.
        
    - Retrieve active taste_profile and current trend data.
        
    
2. **Run Selection Logic**
    
    - Evaluate thresholds.
        
    - Determine base format.
        
    
3. **Apply Modifiers**
    
    - Router intent or taste_tag adjustments.
        
    
4. **Output Assignment**
    
    - Save format decision inside post metadata.


json
{
  "post_id": "CDX_POST_2025_11_SB_0003",
  "format_selected": "Carousel",
  "momentum_index": 0.76,
  "sincerity_proxy_score": 0.83,
  "router_override": false,
  "taste_profile": ["reflective", "vulnerable"]
}


## **8. Integration with Post_Brief_Generator**

  

When a format is selected, Codex automatically loads the appropriate **sub-template**:


|**Format**|**Template Path**|
|---|---|
|Reel|/3_CREATION/Templates/Reel_Brief_Template.md|
|Carousel|/3_CREATION/Templates/Carousel_Brief_Template.md|
|Static|/3_CREATION/Templates/Static_Brief_Template.md|
|Hybrid|/3_CREATION/Templates/Hybrid_Brief_Template.md|


Each sub-template contains:

- Structural rhythm (hook → development → release)
    
- Caption length bin
    
- CTA logic
    
- Visual pacing directives
    

---

## **9. Automation Hooks (n8n)**



|**Node**|**Function**|
|---|---|
|**Fetch Metrics**|Pulls MI + SPS from Reflection Layer|
|**Format Decision Engine**|Applies pseudocode logic|
|**Template Loader**|Inserts correct post brief template|
|**Router Notifier**|Sends decision summary to human Router|
|**Log Writer**|Updates Format_Selection_Log.md|



## **10. Logging Example**


[2025-11-15]
+ CDX_POST_2025_11_SB_0003 selected → Carousel
+ MI: 0.76 | SPS: 0.83 | Taste: Reflective, Vulnerable
+ Source Pattern: Reflective Stillness Arc




## **11. Metadata**

json
{
  "module_id": "CDX_RemixEngine_FormatSelection_v1.0",
  "parent_phase": "Creation",
  "linked_layers": ["Reflection", "Awareness"],
  "update_frequency": "per_cycle",
  "status": "active"
}



## **12. Operating Philosophy**

  

> Format is not design —

> it’s the geometry of attention.

>   

> Codex doesn’t chase formats.

> It chooses form by energy and truth.

---

**Next Recommended File:**

/3_CREATION/Remix_Engine/Timing_Optimization_Protocol.md — defines how Codex schedules publication rhythm (when to post, pause, or cluster output) according to Momentum and Audience Flow.

---

**Version Date:** 2025-10-27

**Status:** Active

**Visibility:** Internal Documentation

