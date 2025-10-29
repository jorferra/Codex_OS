# Daily Sync Protocol — Codex (CDX)

### PURPOSE  
Mantener a !GPT, !CLA, !GEM y Jor completamente alineados cada 24 horas,  
sin pérdida de contexto ni desviación del propósito central.

---

## 1️⃣ SCHEDULE
- 🕕 Hora sugerida: **08:00 AM (Buenos Aires)**  
- 📆 Frecuencia: **Cada 24 horas**

---

## 2️⃣ WORKFLOW

### 🔹 Step 1 — Initialize Layers
Cada IA se inicializa con su respectivo prompt (`INIT_!GPT.md`, `INIT_!CLA.md`, `INIT_!GEM.md`).  
El Router (Jor) lanza la sesión:

```
--- DAILY SYNC & ROUTE ---

Jor said:
Starting daily synchronization for Codex System (CDX).
Please confirm initialization and readiness for SYNC.

Question from Jor to !GPT: Confirm system constants are aligned with Echo_Constants_v1.0.json.
Question from Jor to !CLA: Confirm narrative tone consistency with Codex Manifesto.
Question from Jor to !GEM: Confirm metrics calibration and active Momentum Index tracking.

--- END SYNC ---
```

Cada IA responde **solo a su pregunta**.  
Jor sintetiza todo y guarda el resumen en `/4_REFLECTION/Echo_Layer/Daily_Summary_[date].md`.

---

### 🔹 Step 2 — Post-Sync Calibration
- Se verifican divergencias pendientes del día anterior.  
- Se aplican ajustes rápidos (niveles L1–L2).  
- Se agendan calibraciones L3 para revisión manual.

---

### 🔹 Step 3 — Documentation
- Registrar todo en `_OPERATIONS/Daily_Log/[date].md`.  
- Actualizar `Echo_Layer/Daily_Summary_[date].md`.  
- Si hubo cambios sistémicos, añadir nota al Changelog.

---

## 3️⃣ CHECKLIST (Auto Sync)

✅ Prompts inicializados  
✅ Constantes verificadas  
✅ Divergencias procesadas  
✅ Documentación diaria generada  
✅ Echo actualizado  

---

**Principle:**  
> “Alignment is the beginning of intelligence.”  