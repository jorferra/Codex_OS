<%*
// 1. CONFIGURACIÓN
// ¡ACCIÓN REQUERIDA! Pega tu URL de Producción de n8n aquí:
const WEBHOOK_URL = "https://cdxlat.app.n8n.cloud/webhook/4695b2df-666d-4d0c-b8b3-d7cbe1ed722b”;

// 2. PEDIR DATOS AL ROUTER (Jor)
// Pedir el cliente.
const client = await tp.system.prompt("Cliente:", "Sandra Borghi");
if (!client) {
    new Notice("❌ Operación cancelada. No se especificó cliente.");
    return;
}

// Pedir el prompt.
const prompt = await tp.system.prompt("Prompt (La orden):", "Necesito 2 posts para IG...");
if (!prompt) {
    new Notice("❌ Operación cancelada. No se especificó prompt.");
    return;
}

// 3. MOSTRAR FEEDBACK INMEDIATO
new Notice(`✅ Tarea recibida. Contactando a !GEM...`);

// 4. PREPARAR EL PAYLOAD JSON
const payload = {
    client: client,
    prompt: prompt
};

try {
    // 5. ENVIAR DATOS A n8n (fetch)
    const response = await fetch(WEBHOOK_URL, {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(payload)
    });

    if (!response.ok) {
        throw new Error(`Error de red: ${response.status} ${response.statusText}`);
    }

    // 6. RECIBIR LA RESPUESTA INMEDIATA DE n8n
    // (Recibe el texto plano: "✅ Tarea recibida...")
    const responseText = await response.text(); 

    // 7. NOTIFICAR AL ROUTER EN OBSIDIAN
    new Notice(responseText, 10000); // Mostrar por 10 segundos

} catch (error) {
    console.error("Error al llamar al Webhook de n8n:", error);
    new Notice(`❌ ERROR: No se pudo conectar a n8n. Revisa la consola.\n${error.message}`, 15000);
}

// Esta línea evita que el script inserte "undefined" en la nota.
return "";
%>