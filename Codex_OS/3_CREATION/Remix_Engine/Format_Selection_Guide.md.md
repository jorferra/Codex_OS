# 🎛️ Format Selection Guide — Codex OS  
**Layer:** 3 — Creation / Remix Engine  
**Version:** 1.0  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Format Selection Guide** defines the decision logic Codex OS uses to translate **validated patterns** into the most effective content format — balancing tone, intention, and audience behavior.

Codex does not chase trends.  
It **chooses containers for truth**.

---

## 2. System Context


5_PATTERN_LIBRARY → 3_CREATION (Remix Engine) → 4_REFLECTION



The format is selected after the pattern is validated but before post generation.  
Each choice must reinforce the message’s **resonance**, **emotional weight**, and **temporal relevance**.

---

## 3. Format Taxonomy

| Format | Typical Use | Strength | Limitation |
|---------|--------------|----------|-------------|
| **Reel** | Motion-based storytelling | Reach, discovery, emotional immersion | Requires strong visual rhythm |
| **Carousel** | Narrative depth, sequential reasoning | Retention, clarity, storytelling | Demands user intent to engage |
| **Post (static)** | Simplicity, focused message | Precision, minimal effort | Limited emotional depth |
| **Story** | Real-time connection, intimacy | Immediacy, authenticity | Short lifespan, low discoverability |

---

## 4. Selection Framework

The **Format Decision Matrix (FDM)** operates across three dimensions:

| Dimension | Description | Typical Indicator |
|------------|--------------|-------------------|
| **Tone Intensity** | Emotional weight of message | Calm ↔ Intense |
| **Narrative Depth** | Amount of reasoning or storytelling required | Short ↔ Complex |
| **Platform Priority** | Where message impact is strongest | Instagram, LinkedIn, TikTok, etc. |

The chosen format is the **intersection** of these variables.

---

## 5. Format Decision Logic

```text
IF Tone_Intensity > 0.75 AND Visual_Story_Ratio > 0.6
   → FORMAT = REEL

ELSE IF Narrative_Depth ≥ 0.7 AND Visual_Story_Ratio < 0.6
   → FORMAT = CAROUSEL

ELSE IF Message_Length ≤ 350 chars AND Tone_Intensity ≤ 0.5
   → FORMAT = STATIC POST

ELSE IF Urgency_Factor ≥ 0.8 OR Context = “Live moment”
   → FORMAT = STORY
   
   
```
## **6. AI-Driven Scoring (Integration with !GEM)**

  

Each validated pattern receives a **Format Suitability Score (FSS)**

from the Analyst Layer (!GEM) during Remix preparation.



|**Variable**|**Weight**|**Description**|
|---|---|---|
|Tone_Intensity|0.4|Based on CLA’s taste profile|
|Narrative_Depth|0.3|Extracted from pattern complexity|
|Visual_Story_Ratio|0.2|Measured from previous performance data|
|Urgency_Factor|0.1|Derived from cultural radar or trending topics|



**Formula:**


FSS = (T * 0.4) + (N * 0.3) + (V * 0.2) + (U * 0.1)


Highest-scoring format wins — unless manually overridden by Router.

---

## **7. Manual Override (Router Control)**

  

The Router (Jor) retains full authority to override automatic selections.

Overrides must be documented in the **Decision Log**:

  

**File:** /OPERATIONS/SYNC_Logs/Decisions_Log.md

  

Example (es-AR):

  

> “Se prioriza Story sobre Reel por sensibilidad del momento. Mantener tono íntimo y evitar sobreexposición.”

---

## **8. Platform Calibration**


|**Platform**|**Optimal Format Ratio**|**Notes**|
|---|---|---|
|**Instagram**|50% Reels / 35% Carousels / 10% Posts / 5% Stories|Prioritize storytelling and motion|
|**LinkedIn**|60% Carousels / 30% Posts / 10% Reels|Focus on clarity and authority|
|**TikTok**|90% Reels / 10% Stories|Humor, humanity, energy|
|**YouTube**|70% Reels / 30% Long-Form|Depth over speed|
|**Spotify Video Podcasts**|100% Long-Form|Retention-driven|


These ratios feed directly into the **Timing Optimization Protocol** for balanced scheduling.

---

## **9. Output Schema**

  

Each selected format triggers creation of a **Format_Packet.json**:

json
{
  "format_id": "CDX_FORMAT_2025_11_SB_0003",
  "pattern_source": "CDX_PATTERN_2025_11_SB_004",
  "selected_format": "carousel",
  "fss_score": 0.78,
  "platform_target": "Instagram",
  "router_override": false,
  "timestamp": "2025-10-27T10:00:00Z"
}



Saved to:
/3_CREATION/Remix_Engine/Format_Packets/


## **10. Integration Flow (n8n Automation)**\


|**Node**|**Function**|
|---|---|
|**Pattern Fetcher**|Retrieves top validated pattern.|
|**FSS Calculator**|Computes format suitability score.|
|**Format Selector**|Determines optimal format type.|
|**Router Validator**|Awaits manual confirmation (if needed).|
|**Remix Generator**|Sends data to Post_Generation_Protocol.md.|


## **11. Example Use Case**

  

**Pattern:** Resonant Minimalism

**Tone Intensity:** 0.8

**Narrative Depth:** 0.6

**Visual Story Ratio:** 0.75

**Result:**

→ FSS = 0.77

→ **Format:** Reel

→ Rationale: Emotionally rich pattern, high visual potential, rhythm-driven.

  

**Example Caption (es-AR):**

  

> “No todo silencio es vacío. Algunos significan presencia.”

---

## **12. Metadata**

json
{
  "module_id": "CDX_Creation_FormatSelection_v1.0",
  "parent_phase": "Creation",
  "linked_layers": ["Pattern Library", "Reflection", "Awareness"],
  "update_frequency": "per_post_cycle",
  "status": "active"
}

## **13. Operating Philosophy**

  

> Codex doesn’t ask _what format performs best_ —

> it asks _what format the truth deserves._

  

The format is not a container —

it’s a **ritual** that carries intention

from the unseen to the visible.

---

**Next Recommended File:**

/3_CREATION/Remix_Engine/Synthesis_Rules.md — defines the combinatorial logic Codex uses to merge multiple validated patterns and cultural signals into new hybrid compositions.

---

**Version Date:** 2025-10-27

**Status:** **FINAL | Active | Internal**

**Visibility:** Internal Documentation



