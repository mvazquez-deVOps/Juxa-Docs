---
layout: default
title: Referencia de API
---

# Referencia de API y Endpoints

Esta sección detalla los puntos de entrada (endpoints) del backend de JUXA IA para la integración con el frontend y servicios externos.

---

## Autenticación (`/api/auth`)

Gestión de sesiones, registros y validación de identidad mediante Google.

### 1. Registro de Usuario
* **Ruta:** `POST /api/auth/register`
* **Cuerpo (JSON):** `{ "name", "email", "password", "phone" }`
* **Descripción:** Crea un nuevo perfil con rol 'USER' y plan 'FREE' por defecto.

### 2. Inicio de Sesión Tradicional
* **Ruta:** `POST /api/auth/login`
* **Descripción:** Valida credenciales y devuelve un Token JWT para peticiones seguras.

### 3. Autenticación con Google
* **Ruta:** `POST /api/auth/google`
* **Descripción:** Verifica el ID Token de Google y sincroniza el perfil con la base de datos de JUXA.

---

## Inteligencia Artificial (`/api/ai`)

Interacción directa con el motor Gemini y procesamiento de documentos legales.

### 1. Chat Interactivo (Multimodal)
* **Ruta:** `POST /api/ai/chat`
* **Consumo:** `multipart/form-data`
* **Parámetros:**
    * `message`: Texto de la consulta actual.
    * `file` (opcional): Archivo PDF o imagen para análisis OCR.
    * `history`: Historial de la conversación en formato JSON.
* **Seguridad:** Implementa un interceptor de seguridad para evitar la fuga de directrices internas.

### 2. Generación de Diagnóstico Inicial
* **Ruta:** `POST /api/ai/generate-initial-diagnosis`
* **Descripción:** Realiza el triaje legal inicial basado en el perfil del usuario.

---

## Gestión de Diagnósticos (`/api/diagnoses`)

Persistencia de casos y recuperación de historial en Cloud SQL.

* **Guardar Diagnóstico:** `POST /api/diagnoses`.
* **Listar por Usuario:** `GET /api/diagnoses/user/{userId}`.
* **Obtener PDF:** `GET /api/pdf/{id}` (Genera el dictamen legal en formato descargable).

---

### Notas Técnicas
* **Base URL:** `https://back-legaladvice-284685729356.us-central1.run.app`
* **Cabeceras Obligatorias:** Todas las rutas protegidas requieren `Authorization: Bearer <JWT_TOKEN>`.