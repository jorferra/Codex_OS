# 🌐 Global Performance Overview — Codex OS
**Layer:** System (Dashboards)  
**Version:** 1.0  
**Author:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal

---

## 1) Purpose
Provide a single, cross-project view of Codex health: Momentum, Resonance, Cadence, and Output Quality. This dashboard aggregates Reflection, Awareness, and Creation signals to guide weekly decisions.

---

## 2) Scope & Projects
Tracked projects (examples):
- **SB** — Sandra Borghi
- **IC** — Indómito Café
- **YMS** — YouMaySay

> Add/remove projects by updating the data sources map (Section 4).

---

## 3) Core KPIs (per project)
| KPI | Definition | Source | Target |
|---|---|---|---|
| **MI** (Momentum Index) | Energy state (0–1) | Reflection → Momentum_Index | ≥ 0.70 |
| **LV** (Learning Vector) | Weighted learning quality (0–1) | Reflection → EchoReports | ≥ 0.75 |
| **SPS** (Sincerity Proxy Score) | Truth/alignment score (0–1) | Echo (CLA+GEM) | ≥ 0.80 |
| **Cadence Adherence** | Posts published vs planned (%) | Creation → Post Log | 85–110% |
| **Resonance Δ** | Δ saves+shares vs last 4w (%) | Echo | +10% |
| **Format Mix Fit** | Deviation vs platform mix target | Creation → Format Packets | ≤ 10% dev. |
| **Timing Fit** | % posts inside optimal windows | Creation+Awareness | ≥ 70% |

---

## 4) Data Sources (canonical)
| Data | Path | Notes |
|---|---|---|
| Momentum log | `/4_REFLECTION/Momentum_Index/MI_Log.csv` | Rolling values per project |
| Echo reports | `/4_REFLECTION/EchoReports/[Project]/**/*.json` | LV, SPS, summary |
| Post briefs log | `/3_CREATION/Content_Queue/[Project]/Archive/` | Cadence & timing |
| Format packets | `/3_CREATION/Remix_Engine/Format_Packets/*.json` | Mix analysis |
| Platform metrics | `/2_AWARENESS/Platform_Intelligence/*.md` or Sheets API | Reach/engagement |

> n8n consolidates these into a Sheets workbook: `CDX_Global_Perf`.

---

## 5) Visual Layout (recommended)
1. **Global Pulse** (top row)
   - MI sparkline per project (last 30 days)
   - Status chips: 🟢 Ascending / 🟡 Balanced / 🟠 Fatigue / 🔴 Decline
2. **Resonance Panel**
   - LV vs SPS scatter (per project); quadrant = truth × learning
3. **Cadence & Timing**
   - Bar: planned vs published
   - Gauge: Timing Fit %
4. **Format Mix**
   - Stacked bars vs platform target ratios
5. **Router Notes**
   - Latest human annotations per project (auto-embed)

---

## 6) Calculation Notes
- **Momentum State**: color thresholds from `Echo_Constants_v1.x.json`
- **Resonance Δ**:  
  `((Saves+Shares last 4w) – (prior 4w)) / (prior 4w)`
- **Format Mix Fit**: mean absolute % deviation vs targets in `/3_CREATION/Remix_Engine/Format_Selection_Guide.md`
- **Timing Fit**: posts within platform baseline windows (see Timing Optimization Protocol)

---

## 7) n8n Automation Flow (global refresh)
1. **Fetch Echo & MI** → parse JSON/CSV per project  
2. **Normalize & Compute** → MI, LV, SPS, deltas  
3. **Append to Sheets** → `Global_Pulse`, `Resonance`, `Cadence`, `Formats`, `Timing` tabs  
4. **Render Exports** (optional) → PNG charts to `/SYSTEM/Dashboards/Charts/`  
5. **Router Alert** → if any project breaches thresholds (Section 8)

---

## 8) Alert Rules (Router)
- `MI < 0.55` or weekly ΔMI ≤ –0.10 → **Momentum Alert**
- `SPS < 0.70` & `LV < 0.65` → **Integrity Alert**
- `Cadence Adherence < 70%` for 2 weeks → **Consistency Alert**
- `Timing Fit < 55%` → **Scheduling Alert**

**Telegram template**  
> ⚠️ *{{alert_type}}* — {{project}}  
> MI: {{mi}} | LV: {{lv}} | SPS: {{sps}}  
> Note: {{auto_recommendation}}  
> Logged: {{timestamp}}

---

## 9) Weekly Ops Ritual (Monday)
- Review **Global Pulse** trends
- Read **Echo Highlights** per project (auto-summarized)
- Approve **Calibration Actions** (links to `/4_REFLECTION/Calibration_Reports/`)
- Update Router Notes (max 3 bullets per project, es-AR).  
  _Ejemplo_: “SB: bajar intensidad retórica; sostener calma. Probar slot 09:00 AR.”

---

## 10) File Structure

/SYSTEM/Dashboards/

├── Global_Performance_Overview.md   ← this file

├── Momentum_Index_Dashboard_Spec.md

├── Charts/

│   ├── Global_Pulse_[YYYY-MM].png

│   ├── Resonance_Scatter_[YYYY-MM].png

│   └── Cadence_Timing_[YYYY-MM].png

└── 00_Readme.md


---

## 11) Obsidian Embeds (optional)
```md
![[../4_REFLECTION/Momentum_Index/Charts/Momentum_Curve.png]]
![[../SYSTEM/Dashboards/Charts/Resonance_Scatter_2025-11.png]]

```

## **12) Metadata**

json
{
  "module_id": "CDX_System_GlobalPerformance_v1.0",
  "parent_phase": "System",
  "linked_layers": ["Reflection", "Creation", "Awareness"],
  "update_frequency": "every_72h",
  "status": "active"
}

## **13) Operating Philosophy**

  

> One board. Many rhythms. Decisions stay calm when truth is visible.

  

**Next:** ensure /SYSTEM/Dashboards/00_Readme.md explains how to add/remove projects and where the n8n workbook lives.

  

**Version Date:** 2025-10-27