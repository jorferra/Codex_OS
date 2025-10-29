# _OPERATIONS — Router Layer

This layer captures **strategic intention** and **operational decisions**.

Flow:
1) Entry Gate receives briefs via n8n or Obsidian → JSON stored in /Entry_Gate/YYYY/
2) Router decides:
   - Approve → becomes a Cycle
   - Pause → stays in Gate
   - Drop → mark as archived
3) Decisions and tasks are logged here (SYNC_Logs)

Rules:
- Every project starts with a Gate.
- Nothing moves without the Router's approval.
- Only the Router writes in this folder.

Primary KPI:
**How many Gates become Cycles that reach Reflection?**