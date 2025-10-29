# SYNC & ROUTE PROTOCOL — Codex (CDX) v1.3

### PURPOSE  
The SYNC & ROUTE protocol governs how Jor Ferraro (Router) coordinates the three intelligence layers (!GPT, !CLA, !GEM).  
It ensures clarity, order, and consistency in all multi-agent communications.

---

## 1. IDENTITY & AUTONOMY
Each intelligence is autonomous:
- `!GPT` → Architect (structure, strategy, logic)  
- `!CLA` → Poet (tone, narrative, coherence)  
- `!GEM` → Analyst (data, patterns, metrics)  

Rules:
- ❌ No IA may answer on behalf of another.  
- ❌ No IA may simulate another’s voice or infer its reasoning.  
- ✅ Each IA answers *only* to questions explicitly directed to it.

---

## 2. MESSAGE FORMAT
All exchanges follow this syntax:
```
--- SYNC & ROUTE ---

!GPT said:
[key ideas]
Question from !GPT to !CLA: ...
Question from !GPT to !GEM: ...

!CLA said:
[key ideas]
Question from !CLA to !GEM: ...

!GEM said:
[key ideas]
Question from !GEM to !GPT: ...

--- END SYNC ---
```
At the end, Jor consolidates all inputs into one summary message (`SYNC Consolidated`).

---

## 3. REPLY FORMAT
Each IA replies in a new message block beginning with its identifier:
```
!GPT
[Answer only to the questions directed to !GPT]
```

---

## 4. ROUTER RESPONSIBILITIES
- Jor Ferraro is the sole Router.  
- Only Jor can initiate, merge, or close a SYNC session.  
- The Router records all sessions under:  
  `_OPERATIONS/SYNC_Logs/[YYYY-MM-DD]_SYNC_[Topic].md`

---

## 5. PROHIBITIONS
- ❌ Personificación cruzada.  
- ❌ Generación de respuestas en nombre de otra IA.  
- ❌ Modificación del contexto sin autorización del Router.  
- ❌ Decisiones finales sin consolidación de Jor.

---

## 6. PRINCIPLE  
> “The strength of Codex lies in the harmony of distinct intelligences — never in their confusion.”

---

**Version:** Codex (CDX) v1.3  
**Last Update:** 2025-10-26  