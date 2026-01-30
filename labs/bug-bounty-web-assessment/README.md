# 🔓 Proyecto de Pruebas de Penetración Web - Entorno Controlado

## 📋 Descripción
Este proyecto demuestra una evaluación de seguridad web (pentest) completa, realizada en un **entorno de laboratorio controlado y autorizado**. El objetivo es identificar, explotar y documentar vulnerabilidades comunes del **OWASP Top 10**[citation:3] en aplicaciones web deliberadamente vulnerables, siguiendo una metodología ética y profesional. Todo el trabajo se realizó bajo estricto cumplimiento de las leyes y normas éticas, sin dirigirse a sistemas en producción sin autorización.

## 🎯 Objetivos
- Aplicar la metodología estándar de pruebas de penetración web (Reconocimiento, Análisis, Explotación, Post-Explotación, Informe)[citation:3].
- Identificar vulnerabilidades críticas como Inyección SQL, Cross-Site Scripting (XSS) y Fallos de Control de Acceso.
- Generar un informe profesional que documente los hallazgos, su impacto y las recomendaciones de remediación.

## 📊 Metodología Aplicada
El proyecto siguió las fases de un pentest, adaptando la metodología OWASP[citation:3] a un entorno de laboratorio.

| Fase | Actividades Clave | Herramientas/Enfoque |
|------|-------------------|----------------------|
| **1. Reconocimiento** | Recopilación de información sobre el objetivo (tecnologías, endpoints)[citation:3]. | Nmap, WhatWeb, Google Dorks. |
| **2. Análisis de Vulnerabilidades** | Identificación de debilidades y fallos de configuración[citation:3]. | OWASP ZAP, Burp Suite Scanner. |
| **3. Explotación** | Intento de aprovechar las vulnerabilidades para comprometer el sistema[citation:3]. | SQLmap, payloads manuales de XSS. |
| **4. Post-Explotación** | Evaluación del impacto y alcance del acceso obtenido. | Análisis manual de archivos y permisos. |
| **5. Informe** | Documentación estructurada de todo el proceso, hallazgos y remediaciones[citation:7][citation:10]. | Plantilla personalizada en Markdown. |

## 🛠️ Herramientas Utilizadas

### Entorno de Laboratorio
*   **Aplicación Objetivo:** DVWA (Damn Vulnerable Web Application) o bWAPP[citation:1].
*   **Sistema:** Máquina virtual con Kali Linux o Docker[citation:5].

### Herramientas de Prueba
| Categoría | Herramienta | Uso en el Proyecto |
|-----------|-------------|---------------------|
| **Reconocimiento** | Nmap | Escaneo de puertos y servicios de la aplicación objetivo. |
| **Análisis/Proxy** | Burp Suite Community[citation:5] | Interceptación y manipulación de tráfico HTTP/HTTPS. |
| **Escaneo de Vulnerabilidades** | OWASP ZAP[citation:5] | Escaneo automático inicial para detectar problemas comunes. |
| **Explotación** | SQLmap[citation:5] | Automatización de pruebas de inyección SQL. |
| **Fingerprinting** | Wappalyzer / WhatWeb[citation:5] | Identificación de tecnologías web (CMS, frameworks). |

## 🖼️ Capturas de Pantalla (Ejemplo con datos ofuscados)
_Incluye aquí imágenes que evidencien tu proceso, asegurándote de ofuscar cualquier dato sensible como direcciones IP reales._

*   **Fase de Reconocimiento:** Resultados del escaneo de puertos con Nmap.
    ![Reconocimiento con Nmap](assets/screenshots/01_reconocimiento.png)
*   **Identificación de Vulnerabilidad:** Hallazgo de un parámetro vulnerable a inyección SQL en Burp Suite.
    ![Parámetro vulnerable](assets/screenshots/02_vulnerabilidad.png)
*   **Prueba de Concepto:** Explotación exitosa de una vulnerabilidad de XSS almacenado.
    ![XSS Explotado](assets/screenshots/03_explotacion.png)

## 📊 Hallazgos Relevantes (Ejemplo)
_Aquí se presentan ejemplos genéricos de hallazgos. En tu proyecto, describe los específicos que encontraste._

### 1. Inyección SQL a Ciegas (Blind SQLi)
*   **Severidad:** 🟡 **ALTA** (CVSS: 7.5)
*   **Descripción:** El parámetro `id` en `/vulnerabilidad.php` era susceptible a inyección SQL booleana, permitiendo extraer información de la base de datos.
*   **Evidencia:** Captura de la respuesta HTTP diferencial al inyectar `' AND '1'='1` vs `' AND '1'='2`.
*   **Impacto:** Pérdida de confidencialidad. Un atacante podría extraer nombres de usuario, contraseñas hasheadas y otros datos sensibles.
*   **Recomendación:** Utilizar consultas parametrizadas o prepared statements en el backend.

### 2. Cross-Site Scripting (XSS) Almacenado
*   **Severidad:** 🟠 **MEDIA** (CVSS: 6.3)
*   **Descripción:** El campo de comentarios no sanitizaba la entrada, permitiendo almacenar y ejecutar código JavaScript en el navegador de otros usuarios.
*   **Evidencia:** Captura mostrando el script (`<script>alert('XSS')</script>`) ejecutándose al cargar la página de comentarios.
*   **Impacto:** Robo de sesiones, redirección a sitios maliciosos, defacement.
*   **Recomendación:** Implementar sanitización estricta de salida (output encoding) y validar la entrada.

### 3. Exposición de Archivo de Configuración
*   **Severidad:** 🔵 **BAJA** (CVSS: 4.0)
*   **Descripción:** Se encontró accesible un archivo `config.bak` en el directorio raíz, que contenía credenciales de base de datos en texto plano.
*   **Evidencia:** Captura del contenido del archivo (con credenciales ofuscadas).
*   **Impacto:** Escalada de privilegios si las credenciales son válidas para otros entornos.
*   **Recomendación:** Eliminar archivos de backup innecesarios de directorios accesibles por la web y utilizar variables de entorno.

## 📚 Lecciones Aprendidas | 🚀 Mejoras Futuras

### ✅ Lecciones Aprendidas
1.  **El contexto lo es todo:** Una herramienta automática (como ZAP) señala potenciales, pero el análisis manual es crucial para confirmar la explotabilidad real y el impacto en la lógica de la aplicación.
2.  **Documentación en tiempo real:** Tomar notas y capturas sistemáticamente durante el proceso ahorra mucho tiempo al generar el informe final[citation:7].
3.  **Metodología sobre herramientas:** Seguir un proceso estructurado (como las fases OWASP[citation:3]) es más efectivo que usar herramientas al azar.

### 🔮 Mejoras Futuras para el Proyecto
1.  **Automatización del flujo:** Crear un script (Bash/Python) que automatice la secuencia de reconocimiento y escaneo inicial.
2.  **Profundizar en APIs:** Ampliar el alcance para incluir pruebas de seguridad en APIs REST/GraphQL.
3.  **Simular un entorno más complejo:** Configurar un laboratorio con múltiples servidores que interactúen para practicar ataques de pivoting y post-explotación.

## 👤 Autor
**Tu Nombre**
*   Estudiante/Apasionado de Ciberseguridad con fundamentos en Pentesting Web.
*   🌐 [GitHub](https://github.com/CyberZenithAI) | 💼 [LinkedIn](https://linkedin.com/in/joaquin-ocampo-cybersecurity)
*   📧 Contacto: webdev.student123@outlook.com 

## 📄 Licencia
Distribuido bajo la Licencia MIT. Ver `LICENSE` para más información.

---
**⚖️ Nota Ética y Legal:** Este proyecto se realizó **exclusivamente en un entorno de laboratorio controlado y auto-contenido** (DVWA/bWAPP en una máquina virtual local). **Nunca** realice pruebas de penetración en sitios web o sistemas que no le pertenezcan sin un **permiso explícito y por escrito**. Respetar la privacidad y la ley es fundamental en la ciberseguridad.
