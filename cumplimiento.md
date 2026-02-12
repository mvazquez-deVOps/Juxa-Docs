## Infraestructura Global y Certificaciones (Google Cloud)

JUXA IA se ejecuta sobre la infraestructura de **Google Cloud Platform (GCP)** en la región `us-central1`, lo que nos permite heredar un marco de seguridad de nivel bancario y cumplimiento internacional.

### 1. Certificaciones de Seguridad Heredadas
Nuestra plataforma opera en centros de datos que cumplen con los estándares más rigurosos del mundo, auditados anualmente por terceros independientes:
* **ISO/IEC 27001, 27017, 27018:** Gestión de seguridad de la información y protección de PII en la nube.
* **SOC 1, SOC 2 y SOC 3:** Garantía de seguridad, disponibilidad e integridad del procesamiento.
* **Esquema Nacional de Seguridad (ENS) y PCI DSS:** Cumplimiento de altos estándares de seguridad para servicios en la nube y manejo de datos financieros.

### 2. Cumplimiento de Protección de Datos y Red Privada
* **Cifrado AES-256:** Todos los datos legales, incluyendo el historial de conversaciones en la tabla `diagnoses`, se cifran en reposo mediante el estándar avanzado AES-256.
* **Conectividad Privada (Socket Factory):** La comunicación entre el Backend (Cloud Run) y la Base de Datos se realiza mediante un túnel privado encriptado que no expone direcciones IP a la internet pública.

### 3. Cumplimiento con Soberanía y Privacidad
* **Soberanía de Datos:** Procesamiento alineado con las Cláusulas Contractuales Modelo (MCC) para el GDPR europeo y la LFPDPPP de México.
* **Vertex AI (Gemini):** Los datos del usuario y documentos subidos **NO** se utilizan para entrenar modelos globales de Google; el procesamiento ocurre en una instancia aislada del cliente.

---