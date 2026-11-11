# 🛡️ Proyecto Integrador - Módulo 4: Agente de IA y Automatización Defensiva

**Alumna:** Daiana Atienza  
**Curso:** Coderhouse - Automatización con Inteligencia Artificial  
**Proyecto:** Sistema de Atención y Gestión de Seguros con n8n  

---

## 📋 Descripción del Workflow
Este flujo automatiza la atención al cliente de la agencia de seguros mediante la combinación de un disparador de correo, filtros de seguridad (*guardrails*), validación de bases de datos para evitar duplicados, un **Agente de IA (Google Gemini)** para el análisis de consultas y redacción inteligente, un sistema de supervisión humana (*Human-in-the-Loop* mediante borradores en Gmail) y alertas operativas integradas en **Slack**.

---

## 🛠️ Arquitectura y Componentes Implementados
1. **Guardrail anti-bucle:** Filtra y descarta correos automáticos (*out of office*, *no-reply*, etc.).
2. **Saneamiento de Datos (Nodo Set):** Previene errores de tipo (*Error 400*).
3. **Validación CRM (Google Sheets):** Verifica la existencia previa del usuario y actualiza o crea el registro de forma idempotente (*Evita Error 409*).
4. **Cerebro Cognitivo (AI Agent):** Razona sobre el caso utilizando contexto seguro y directrices de menor privilegio.
5. **Supervisión Humana (Human-in-the-Loop):** Genera exclusivamente borradores en Gmail (`Create Draft`), garantizando que la IA nunca envíe comunicaciones automatizadas sin validación humana.
6. **Optimización y Notificación (Slack):** Envía un payload limpio y resumido al canal operativo del equipo.

---

## 🔐 Evidencia de Conectividad (Credenciales OAuth2)
A continuación se visualizan las credenciales activas e integradas de forma segura en la instancia de n8n:


![Uploading credenciales-verde.png…]()
