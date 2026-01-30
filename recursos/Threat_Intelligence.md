# Guía de Threat Intelligence & OSINT

Este documento proporciona **recursos, técnicas y herramientas** para recopilar, analizar y enriquecer información de amenazas (Threat Intelligence) y realizar OSINT (Open Source Intelligence) de manera ética y educativa.

---

## 1️⃣ Conceptos Clave

- **Threat Intelligence (TI):** Información procesable sobre amenazas cibernéticas, usada para prevenir, detectar y responder a incidentes.
  - Tipos: Estratégica, Táctica, Operativa y Técnica
- **OSINT:** Información obtenida de fuentes públicas o abiertas (internet, redes sociales, dominios, etc.) para análisis de seguridad.

---

## 2️⃣ Fuentes de Threat Intelligence Gratuitas

- **VirusTotal** – Análisis de archivos, hashes y URLs sospechosas.  
- **AbuseIPDB** – Reputación de direcciones IP maliciosas.  
- **Shodan Free** – Búsqueda de dispositivos expuestos en Internet.  
- **CIRCL OSINT Tools** – Herramientas gratuitas de análisis de amenazas.  
- **AlienVault OTX** – Indicadores de compromiso (IoC) compartidos por la comunidad.  

---

## 3️⃣ Técnicas OSINT Éticas

- **Reconocimiento de dominios y subdominios**  
  - Herramientas: `sublist3r`, `Amass`, `crt.sh`  
- **Enumeración de tecnologías web**  
  - Herramientas: `Wappalyzer`, `BuiltWith`  
- **Investigación en redes sociales y perfiles públicos**  
  - LinkedIn, Twitter, GitHub, foros públicos  
- **Análisis de metadatos y documentos**  
  - Herramientas: `exiftool`, `FOCA`  

---

## 4️⃣ Flujo Básico de Threat Intel para SOC L1

1. **Recolección de Datos**  
   - Captura de IoCs: IP, dominios, hashes, URLs  
   - Información pública: noticias de seguridad, alertas CERT  
2. **Análisis**  
   - Correlación de alertas con fuentes TI  
   - Validación de amenazas mediante logs y PCAP  
3. **Enriquecimiento**  
   - Consultar VirusTotal, AbuseIPDB, Shodan, OTX  
   - Agregar contexto: geolocalización, reputación, tácticas MITRE ATT&CK  
4. **Documentación y Escalamiento**  
   - Registrar hallazgos en ticket SOC  
   - Escalar incidentes relevantes a SOC L2 o Red Team  

---

## 5️⃣ Herramientas Gratuitas Destacadas

| Categoría                   | Herramientas / Web |
|------------------------------|------------------|
| Malware / Hash Analysis      | VirusTotal, Hybrid Analysis |
| IP / Domain Reputation       | AbuseIPDB, Whois, Shodan Free |
| Vulnerabilidad Web           | OWASP ZAP, Wappalyzer, BuiltWith |
| Open Source Intelligence     | Maltego CE, Recon-ng, theHarvester |
| Metadatos y Documentos       | ExifTool, FOCA, Metagoofil |

---

## 6️⃣ Buenas Prácticas

- Trabajar siempre en **entornos seguros y legales**.  
- Documentar todas las acciones y hallazgos.  
- Correlacionar información de **múltiples fuentes** antes de tomar decisiones.  
- Mantenerse actualizado con **alertas de CERTs y blogs de seguridad**.  
- Utilizar scripts y automatización para agilizar la recolección (Python, Bash).  

---

## Objetivo

Proporcionar un **manual práctico y ético** para aplicar Threat Intelligence y OSINT en laboratorios, simuladores SOC y proyectos educativos 2026.  
Ideal para **SOC L1, Blue Team y nuevos talentos** que buscan aprender técnicas reales de análisis de amenazas.
