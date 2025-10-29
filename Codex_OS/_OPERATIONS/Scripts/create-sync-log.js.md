async function createSyncLog(tp) {
    const fname = `${tp.date.now("YYYY-MM-DD-HHmm")}-sync`;
    const folder = "Codex_OS/_OPERATIONS/SYNC_Logs";
    const templatePath = "Codex_OS/_OPERATIONS/Templates/SYNC_Log_Template.md";
    
    const template = await tp.file.find_tfile(templatePath);
    if (!template) {
        new Notice("Template no encontrado");
        return;
    }
    
    const newFile = await tp.file.create_new(template, fname, false, folder);
    
    if (newFile) {
        await app.workspace.getLeaf().openFile(newFile);
    }
}

module.exports = createSyncLog;