---
client: "<% tp.system.prompt('Client?') %>"
goal: "<% tp.system.prompt('Goal?') %>"
signal: "<% tp.system.prompt('Signal?') %>"
timestamp: "<% tp.date.now('YYYY-MM-DD HH:mm') %>"
---

# <% tp.date.now("YYYY-MM-DD") %>-sync

⚡ Pending sync




---
 

<%*
const newName = tp.date.now("YYYY-MM-DD_HH-mm");
const targetFolder = "CDX/Codex_OS/_OPERATIONS/SYNC_Logs";
await tp.file.rename(newName);
await tp.file.move(targetFolder + "/" + newName);
%>