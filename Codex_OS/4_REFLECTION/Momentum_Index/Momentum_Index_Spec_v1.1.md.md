# 📈 Momentum Index Specification — Codex OS  
**Layer:** 4 — Reflection  
**Version:** 1.1  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Momentum Index (MI)** measures the *energy state* of a creative system.  
It tracks whether the system is gaining resonance, losing traction, or entering creative fatigue.  

It translates performance fluctuations into clear **narrative rhythm signals** — so Codex knows when to push, pause, or pivot.

---

## 2. Core Definition

**Momentum Index (MI)** = *weighted synthesis of engagement velocity, resonance quality, and creative consistency.*

Expressed as a normalized value between **0 and 1**:

- `0.80–1.00` → **Ascending Momentum** (growth phase)  
- `0.60–0.79` → **Stable Momentum** (steady state)  
- `0.40–0.59` → **Decaying Momentum** (creative fatigue)  
- `<0.40` → **Critical Zone** (requires strategic intervention)

---

## 3. Formula (Echo Integration)

```text
MI = (W₁ * EV + W₂ * RQ + W₃ * CC + W₄ * SR) / (W₁ + W₂ + W₃ + W₄)


```

Where:

|**Variable**|**Meaning**|**Description**|
|---|---|---|
|**EV**|Engagement Velocity|% change in engagement over 72h–96h window|
|**RQ**|Resonance Quality|Sincerity-adjusted emotional tone index|
|**CC**|Creative Consistency|Regularity of posting and message clarity|
|**SR**|Saves Ratio|Ratio of saves to likes (retention signal)|

**Default Weights (Echo_Constants_v1.1.json):**


W₁ = 0.35  
W₂ = 0.30  
W₃ = 0.20  
W₄ = 0.15


## **4. Data Sources**


|**Metric Source**|**Input**|**Layer**|
|---|---|---|
|Engagement Velocity|Platform analytics (Instagram, YouTube, etc.)|Awareness|
|Resonance Quality|Sentiment and tone scores from Echo Reports|Reflection|
|Creative Consistency|Post_Brief publication cadence|Creation|
|Saves Ratio|Retention tracking in Echo Layer|Reflection|


## **5. Rolling Window Logic**

  

The **MI is recalculated** every **72h–96h** using a rolling median window.

  

This ensures:

- Minor anomalies (e.g., viral spikes) don’t distort long-term momentum.
    
- System learning prioritizes **consistency over virality**.




MI_t = median(MI_t-1, MI_t-2, MI_t-3)



The value is visualized as a **momentum curve** in the Calibration Dashboard, updated via n8n or Google Sheets.


## **6. Interpretation Framework**


|**MI Range**|**State**|**Recommended Action**|
|---|---|---|
|**0.85–1.00**|Growth|Continue current creative cadence; minor optimization only.|
|**0.70–0.84**|Balance|Healthy equilibrium; gather learning for next phase.|
|**0.55–0.69**|Fatigue|Reduce posting frequency, reintroduce silence windows.|
|**0.40–0.54**|Decay|Rethink creative strategy; trigger new Discovery mini-session.|
|**<0.40**|Breakdown|Immediate recalibration required; pause all campaigns.|



## **7. Integration with Echo & Calibration Layers**


**From Echo → Calibration → Momentum:**

1. Echo generates _resonance data_ (sincerity, engagement, saves).
    
2. Calibration applies _adjustments_ (changes constants, tone, posting rhythm).
    
3. Momentum Index measures _impact_ of those changes across time.
    

  

**Feedback Loop Example:**

Echo Report → Calibration Report → Momentum Index → Awareness Update → Remix Engine


This chain ensures Codex continuously _evolves its creative metabolism_.

## **8. n8n Automation Flow**


|**Node**|**Function**|
|---|---|
|**Echo Fetcher**|Pulls metrics from last Echo Report|
|**Data Normalizer**|Standardizes values between 0–1|
|**Momentum Calculator**|Computes MI formula|
|**Trend Tracker**|Logs 4-week slope of MI curve|
|**Alert Generator**|Sends message if MI < 0.55|
|**Sheet Sync**|Updates Momentum Dashboard|


## **9. Output Schema**


{
  "momentum_id": "CDX_MI_SB_2025_11_10",
  "client": "Sandra Borghi",
  "time_window_hours": 96,
  "values": {
    "EV": 0.78,
    "RQ": 0.82,
    "CC": 0.74,
    "SR": 0.71
  },
  "weights": {
    "W1": 0.35,
    "W2": 0.30,
    "W3": 0.20,
    "W4": 0.15
  },
  "momentum_index": 0.77,
  "trend_direction": "stable",
  "recommendation": "Maintain rhythm; monitor next Echo cycle."
}

## **10. Metadata**


{
  "module_id": "CDX_Reflection_MomentumIndex_v1.1",
  "parent_phase": "Reflection",
  "linked_layers": ["Awareness", "Creation"],
  "update_frequency": "every_72h",
  "status": "active"
}


---

## **11. Operating Philosophy**

  

> Codex doesn’t chase acceleration — it measures flow.

> True momentum isn’t motion — it’s coherence sustained over time.


**Next Recommended File:**

/5_PATTERN_LIBRARY/Post_Patterns_Update_Protocol.md — defines how learnings from Momentum Index translate into reusable creative templates.

---

**Version Date:** 2025-10-27

**Status:** Active

**Visibility:** Internal Documentation











