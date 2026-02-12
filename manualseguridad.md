## Arquitectura de Seguridad

Nuestra infraestructura está diseñada bajo el principio de **Privacidad por Diseño**, asegurando que cada interacción legal esté protegida por múltiples capas de seguridad.

### 1. Autenticación 
* **JSON Web Tokens (JWT):** El acceso a los recursos legales está restringido mediante tokens firmados con algoritmo **HS256**, gestionados por un filtro de seguridad persistente en el backend.
* **Encriptación de Identidad:** Las credenciales de acceso se almacenan en la base de datos **Cloud SQL** utilizando el estándar de encriptación **BCrypt**, lo que impide la lectura de contraseñas incluso para administradores del sistema.

### 2. Confidencialidad del Motor de IA (Gemini)
* **Aislamiento de Prompts:** El sistema utiliza una capa intermedia de sanitización que ofusca nombres de archivos internos (como `Hoja_deRita.csv`) y evita la fuga de instrucciones de sistema.
* **Filtro de Integridad Técnica:** Si el motor de IA detecta un intento de compromiso de los protocolos de seguridad, activa un *Security Fallback* automático que bloquea la respuesta y notifica al equipo técnico.

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


**© 2026 JUXA AI . Todos los derechos reservados.**