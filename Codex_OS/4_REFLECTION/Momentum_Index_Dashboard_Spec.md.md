# 📊 Momentum Index Dashboard Specification — Codex OS  
**Layer:** 4 — Reflection  
**Version:** 1.0  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal  

---

## 1. Purpose

The **Momentum Index Dashboard (MID)** visualizes the *creative energy state* of Codex in real time.  
It converts raw MI data from the Echo Layer into intuitive, color-coded visualizations for monitoring, trend forecasting, and rhythm calibration.

The dashboard functions as Codex’s **“creative pulse monitor”** — tracking coherence, velocity, and fatigue across time.

---

## 2. System Context

/4_REFLECTION/Momentum_Index/Momentum_Index_Spec.md  →  /SYSTEM/DASHBOARDS/Momentum_Index_Dashboard_Spec.md

It is updated automatically every **72–96h** through n8n and synchronized with:
- **Google Sheets** (numeric data feed)
- **Notion / Obsidian** (display layer)
- **Telegram Alerts** (threshold triggers for the Router)

---

## 3. Data Sources

| Source | Layer | Description |
|---------|-------|--------------|
| `EchoReport.json` | Reflection | Resonance, sincerity, and saves data |
| `Post_Brief_Log.md` | Creation | Frequency and cadence metrics |
| `Platform_Analytics.json` | Awareness | Engagement and velocity signals |
| `Calibration_Report.md` | Reflection | Adjustment context for MI interpretation |

All raw metrics are normalized (0–1) through `/n8n/workflows/Momentum_Calculator_v1.1`.

---

## 4. Data Pipeline Overview

```text
n8n → Google Sheets (raw inputs)  
Sheets → Notion (via API sync)  
Notion → Obsidian (linked dashboard view)

```

The MI Dashboard runs on a **4-step logic cycle:**

1. **Ingest** — Fetch metrics from Echo + Platform APIs
    
2. **Compute** — Apply MI formula
    
3. **Visualize** — Update charts and gauges
    
4. **Notify** — Send Router alert if thresholds crossed
    

---

## **5. Visualization Components**

| **Component**              | **Type**              | **Description**                      | **Source**                    |
| -------------------------- | --------------------- | ------------------------------------ | ----------------------------- |
| **Momentum Curve**         | Line Chart            | MI value over time (rolling 30 days) | Sheets range MI_Log!A:B       |
| **Energy State Gauge**     | Circular Progress Bar | Displays current MI (0–1)            | MI_Current!B2                 |
| **Trend Direction**        | Text + Arrow          | Growth / Stable / Decay              | Calculated via 4-period slope |
| **Echo Resonance Heatmap** | Heatmap               | Cross-reference MI with Resonance    | Resonance_Trend!A:D           |
| **Cycle Summary Table**    | Table                 | 4-week performance overview          | MI_Summary!A:G                |


## **6. Color Thresholds (Visual Encoding)**

|**Range**|**State**|**Color**|**Dashboard Action**|
|---|---|---|---|
|0.85–1.00|Ascending|🟢 #42C87A|Show “Growth Pulse” banner|
|0.70–0.84|Balanced|🟡 #EFC94C|Maintain rhythm|
|0.55–0.69|Fatigue|🟠 #F08C35|Suggest pause or recalibration|
|0.40–0.54|Decline|🔴 #E44D4D|Trigger Router Alert|
|<0.40|Critical|⚫ #1E1E1E|Lock posting cycle and reset|

## **7. Calculation Schema (Google Sheets)**

excel
= (EV*0.35 + RQ*0.30 + CC*0.20 + SR*0.15)

Where:

- **EV** = Engagement Velocity (Δ% 72h)
    
- **RQ** = Resonance Quality (Echo data)
    
- **CC** = Creative Consistency
    
- **SR** = Saves Ratio
    

  

Each data point is timestamped and plotted using a **rolling median (3 values)** for smoothing.

---

## **8. n8n Automation Schema**

|**Node**|**Function**|
|---|---|
|**Fetch Echo Data**|Pulls latest Echo Reports|
|**Normalize Values**|Scales 0–1 using z-score|
|**Compute MI**|Applies weighted formula|
|**Append to Sheets**|Logs in MI_Log tab|
|**Generate Alerts**|Sends Telegram message if MI < 0.55|
|**Trigger Reflection Report**|Creates /4_REFLECTION/Daily_Summary_[date].md|

## **9. Alert Protocol (Telegram / Email)**

  

**Trigger Condition:**

If momentum_index < 0.55 OR ΔMI (week) ≤ -0.10

  

**Message Template:**

  

> ⚠️ _Momentum Drop Detected_

> Client: {{client_name}}

> MI: {{current_mi}}

> Trend: {{trend_direction}}

> Recommended Action: {{action_text}}

> Logged at: {{timestamp}}

  

Example:

  

> ⚠️ Momentum Drop — SB / MI 0.52 / Decline

> Action: Initiate tone recalibration.

---

## **10. Dashboard Layout (Obsidian or Framer View)**

  

**Main Panels:**

1. **Energy Curve** — interactive MI trend
    
2. **Echo Resonance Heatmap**
    
3. **Router Notes Embed**
    
4. **Calibration Log**
    
5. **Next Recommended Action** (auto-updated from n8n)
    

  

**Framer Embed (optional):**

- Chart.js line rendering
    
- Google Sheets API connector
    
- “Pulse Mode” — color changes background subtly based on MI range
    

---

## **11. Storage & File Structure**

/4_REFLECTION/
├── Momentum_Index/
│   ├── Momentum_Index_Spec.md
│   ├── Momentum_Index_Dashboard_Spec.md  ← this file
│   ├── MI_Log.csv
│   ├── Charts/
│   │   ├── Momentum_Curve.png
│   │   └── Heatmap_Resonance.png
│   └── Alerts/
│       ├── Telegram_Alerts_Log.md
│       └── Daily_Summary/
│           ├── [YYYY-MM-DD]_Summary.md
│           └── Archive/

## **12. Metadata**

json
{
  "module_id": "CDX_Reflection_MomentumDashboard_v1.0",
  "parent_phase": "Reflection",
  "linked_layers": ["Creation", "Awareness"],
  "update_frequency": "every_72h",
  "status": "active"
}

## **13. Operating Philosophy**

  

> Momentum is the music between posts.

> The dashboard doesn’t measure speed — it visualizes harmony.

---

**Next Recommended File:**

/SYSTEM/DASHBOARDS/Global_Performance_Overview.md — consolidates data from Momentum, Echo, and Pattern layers into a unified system report for Codex OS.

---

**Version Date:** 2025-10-27

**Status:** Active

**Visibility:** Internal