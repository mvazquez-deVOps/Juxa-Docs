
# Manual de Seguridad y Protección de Datos - JUXA IA
**Versión:** 1.3.0 | **Estatus:** Cumplimiento UE (GDPR) y México (LFPDPPP) 2026

Bienvenido al centro oficial de documentación sobre seguridad de JUXA. Este manual detalla los protocolos técnicos y legales implementados para garantizar la integridad y confidencialidad de la asesoría jurídica asistida por IA.

---

## Arquitectura de Seguridad

Nuestra infraestructura está diseñada bajo el principio de **Privacidad por Diseño**, asegurando que cada interacción legal esté protegida por múltiples capas de seguridad.

### 1. Autenticación Industrial
* **JSON Web Tokens (JWT):** El acceso a los recursos legales está restringido mediante tokens firmados con algoritmo **HS256**, gestionados por un filtro de seguridad persistente en el backend.
* **Encriptación de Identidad:** Las credenciales de acceso se almacenan en la base de datos **Cloud SQL** utilizando el estándar de encriptación **BCrypt**, lo que impide la lectura de contraseñas incluso para administradores del sistema.

### 2. Blindaje del Motor de IA (Gemini)
* **Aislamiento de Prompts:** El sistema utiliza una capa intermedia de sanitización que ofusca nombres de archivos internos (como `Hoja_deRita.csv`) y evita la fuga de instrucciones de sistema.
* **Filtro de Integridad Técnica:** Si el motor de IA detecta un intento de compromiso de los protocolos de seguridad, activa un *Security Fallback* automático que bloquea la respuesta y notifica al equipo técnico.

---

## Infraestructura Global y Certificaciones (Google Cloud)

JUXA IA se ejecuta sobre la infraestructura de **Google Cloud Platform (GCP)** en la región `us-central1`, lo que nos permite heredar un marco de seguridad de nivel bancario y cumplimiento internacional.

### 1. Certificaciones de Seguridad Heredadas
Nuestra plataforma opera en centros de datos que cumplen con los estándares más rigurosos del mundo, auditados anualmente por terceros independientes:
* **ISO/IEC 27001, 27017, 27018:** Gestión de seguridad de la información y protección de PII en la nube.
* **SOC 1, SOC 2 y SOC 3:** Garantía de seguridad, disponibilidad e integridad del procesamiento.
* **Esquema Nacional de Seguridad (ENS) y PCI DSS:** Cumplimiento de altos estándares de seguridad para servicios en la nube y manejo de datos financieros.

### 2. Blindaje de Datos y Red Privada
* **Cifrado AES-256:** Todos los datos legales, incluyendo el historial de conversaciones en la tabla `diagnoses`, se cifran en reposo mediante el estándar avanzado AES-256.
* **Conectividad Privada (Socket Factory):** La comunicación entre el Backend (Cloud Run) y la Base de Datos se realiza mediante un túnel privado encriptado que no expone direcciones IP a la internet pública.

### 3. Cumplimiento con Soberanía y Privacidad
* **Soberanía de Datos:** Procesamiento alineado con las Cláusulas Contractuales Modelo (MCC) para el GDPR europeo y la LFPDPPP de México.
* **Vertex AI (Gemini):** Los datos del usuario y documentos subidos **NO** se utilizan para entrenar modelos globales de Google; el procesamiento ocurre en una instancia aislada del cliente.

---

## Privacidad y Derechos ARCO

Cumplimos rigurosamente con los derechos de **Acceso, Rectificación, Cancelación y Oposición**:

1. **Minimización de Datos:** Solo procesamos la información estrictamente necesaria. Los documentos subidos por **OCR** se procesan de forma efímera para el análisis del caso.
2. **Derecho al Olvido:** El sistema permite la supresión técnica definitiva de los registros históricos vinculados al `userId`.
3. **Cooperación Judicial:** Ante una orden judicial fundada, JUXA actuará como custodio legal, entregando únicamente la información específica requerida sin comprometer al resto de los usuarios.

---

## Reporte de Incidencias

Para garantizar la detección temprana de vulnerabilidades, JUXA integra un **Canal de Denuncias Técnico**. Los usuarios pueden reportar errores de interfaz o anomalías directamente al equipo de soporte.

---
**© 2026 JUXA Intelligence. Todos los derechos reservados.**