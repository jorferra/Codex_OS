# 📊 Momentum Index Dashboard — Specification (Codex OS)
**Path:** `/SYSTEM/Dashboards/Momentum_Index_Dashboard_Spec.md`  
**Layer:** System / Dashboards  
**Version:** 1.0  
**Owner:** CDX Router (Jor Ferraro)  
**Status:** Active  
**Visibility:** Internal

---

## 1) Purpose
Define the data contracts, calculations, and visualization rules for the **Momentum Index (MI)** dashboard that tracks creative energy across projects and time. This spec powers Obsidian views, Sheets charts, and n8n syncs.

---

## 2) Data Sources (CSV contracts)
Primary files (must exist):

- `/SYSTEM/Dashboards/Data_Schema/MI_Log_Template.csv`
- `/SYSTEM/Dashboards/Data_Schema/Global_Pulse_Template.csv`

### 2.1 MI_Log_Template.csv — schema
| field | type | required | notes |
|---|---|---|---|
| `timestamp` | ISO-8601 string | ✔ | `YYYY-MM-DDTHH:MM:SS-03` |
| `project` | string | ✔ | short code: `SB`, `IC`, `YMS`, etc. |
| `EV` | float [0..1] | ✔ | Engagement Velocity |
| `RQ` | float [0..1] | ✔ | Resonance Quality |
| `CC` | float [0..1] | ✔ | Creative Consistency |
| `SR` | float [0..1] | ✔ | Saves Ratio |
| `MI` | float [0..1] | ✔ | Precomputed or pipeline-computed |
| `window_hours` | int | ✔ | 72 or 96 |
| `alert` | enum | ✔ | `none|low_MI|data_gap` |
| `notes` | string | – | free text |

### 2.2 Global_Pulse_Template.csv — schema
| field | type | required | notes |
|---|---|---|---|
| `timestamp` | ISO-8601 | ✔ | sample every 72–96h |
| `client` | string | ✔ | human-readable |
| `MI` | float | ✔ | momentum |
| `LV` | float | ✔ | learning vector |
| `SPS` | float | ✔ | sincerity proxy |
| `trend` | enum | ✔ | `up|down|stable` |
| `state` | enum | ✔ | `Growth|Balance|Fatigue|Decay` |
| `notes` | string | – | summary insight |

---

## 3) Core Calculations
### 3.1 MI (if computed in-dashboard)

MI = (0.35_EV + 0.30_RQ + 0.20_CC + 0.15_SR)

Rolling median smoothing (last 3 samples per project):

MI_smooth(t) = median(MI(t), MI(t-1), MI(t-2))

### 3.2 State Buckets (for coloring)
- `Growth`: 0.85–1.00
- `Balance`: 0.70–0.84
- `Fatigue`: 0.55–0.69
- `Decay`: 0.40–0.54
- `Critical`: <0.40

### 3.3 Alerts
- `low_MI` if `MI < 0.65` for ≥2 consecutive samples.
- `data_gap` if no sample for >120h for any active project.

---

## 4) Obsidian Rendering (Dataview/DataviewJS)

> Requires **Dataview** plugin. Place this spec file anywhere; the views read the CSVs from `/SYSTEM/Dashboards/Data_Schema/`.

### 4.1 Project Momentum Table (DataviewJS)
```dataviewjs
const path = "/SYSTEM/Dashboards/Data_Schema/MI_Log_Template.csv";
const csv = await dv.io.load(path);
const rows = csv.trim().split("\n").slice(1).map(r=>r.split(","));
dv.table(
  ["When","Project","MI","State","Alert","Notes"],
  rows.map(r=>{
    const mi = parseFloat(r[6]);
    const state = mi>=0.85?"Growth":mi>=0.70?"Balance":mi>=0.55?"Fatigue":mi>=0.40?"Decay":"Critical";
    return [r[0], r[1], mi.toFixed(2), state, r[8], r[9]?.replaceAll('"','')];
  })
);
```

### **4.2 Global Pulse (compact)**

const p = "/SYSTEM/Dashboards/Data_Schema/Global_Pulse_Template.csv";
const csv = await dv.io.load(p);
const rows = csv.trim().split("\n").slice(1).map(r=>r.split(","));
dv.table(
  ["When","Client","MI","LV","SPS","Trend","State","Notes"],
  rows.map(r=>[r[0],r[1],Number(r[2]).toFixed(2),Number(r[3]).toFixed(2),Number(r[4]).toFixed(2),r[5],r[6],r[7]?.replaceAll('"','')])
);

### **4.3 Simple Sparkline per Project (inline SVG)**

dataviewjs

const path = "/SYSTEM/Dashboards/Data_Schema/MI_Log_Template.csv";
const raw = await dv.io.load(path);
const byProject = {};
raw.trim().split("\n").slice(1).forEach(line=>{
  const [ts, project, , , , , mi] = line.split(",");
  (byProject[project] ??= []).push({ts, mi: Number(mi)});
});
for (const [proj, arr] of Object.entries(byProject)) {
  arr.sort((a,b)=>a.ts.localeCompare(b.ts));
  const points = arr.map((d,i)=>`${i*20},${100 - d.mi*100}`).join(" ");
  dv.paragraph(`**${proj}**`);
  dv.el("svg", null, (el)=>{
    el.setAttribute("width", (arr.length-1)*20+20);
    el.setAttribute("height", 100);
    const poly = document.createElementNS("http://www.w3.org/2000/svg","polyline");
    poly.setAttribute("points", points);
    poly.setAttribute("fill","none");
    poly.setAttribute("stroke","currentColor");
    poly.setAttribute("stroke-width","2");
    el.appendChild(poly);
  });
}

## **5) Google Sheets / Charts (optional)**

- Mirror both CSVs to a Sheet via n8n.
    
- Build charts:
    
    - **Line**: MI per project (smoothed).
        
    - **Bar**: LV and SPS per client (latest window).
        
    - **Heatmap**: State buckets by client vs timestamp.
        
    
- Publish charts and embed in Obsidian using ![](chart-public-url).
    

---

## **6) n8n Integration (reference nodes)**

  

Workflow: CDX_Dashboard_Pipeline_v1

1. **Read Echo** → compute EV/RQ/SR (normalize 0..1)
    
2. **Compute MI** (or accept precomputed)
    
3. **Append Row** to MI_Log_Template.csv
    
4. **Aggregate** last sample per client → Global_Pulse_Template.csv
    
5. **Alert** if low_MI or data_gap → Telegram/Email
    
6. **Sheet Sync** (optional)
    

  

Environment flags in /SYSTEM/Constants/Echo_Constants_v1.0.json:

json

{
  "mi_weights": {"EV":0.35,"RQ":0.30,"CC":0.20,"SR":0.15},
  "window_hours": [72,96],
  "alert_thresholds": {"low_mi":0.65, "gap_hours":120}
}


## **7) QA & Data Hygiene**

- **Timestamp monotonic** per project (no future dates).
    
- **Bounds check**: EV, RQ, CC, SR, MI ∈ [0,1].
    
- **Null guard**: replace missing with previous valid; tag alert=data_gap.
    
- **Duplicate row rule**: same timestamp+project → keep latest.
    

---

## **8) Dashboard Layout (recommended)**

  

Create /SYSTEM/Dashboards/Global_Performance_Overview.md with sections:

1. **Top Tiles** (manual text or callouts):
    
    - Avg MI (7d), #Projects in Growth, #Alerts open.
        
    
2. **Global Pulse Table** (section 4.2).
    
3. **Sparklines per Project** (section 4.3).
    
4. **Actions Queue**
    
    - Link to /OPERATIONS/SYNC_Logs/Decisions_Log.md
        
    - Link to /4_REFLECTION/Calibration_Reports/
        
    
5. **Last Sync** (auto-updated by n8n in a footer snippet).
    

---

## **9) Completion Criteria (for “CDX OBSIDIAN STRUCTURE COMPLETED”)**

- ✅ Both CSVs exist and have ≥1 row.
    
- ✅ This spec file saved at the path above.
    
- ✅ Global_Performance_Overview.md created and rendering tables.
    
- ✅ n8n pipeline appends rows every 72–96h (or manual updates in the interim).
    
- ✅ Echo constants include mi_weights and alert_thresholds.
    

---

## **10) Change Log**

- **v1.0 (2025-10-27)** — Initial dashboard spec aligned to MI v1.1 and Echo constants v1.0.


