# Guía Práctica de OSINT – Open Source Intelligence

Este documento proporciona **técnicas, herramientas y buenas prácticas de OSINT** para aprender de manera ética y fortalecer habilidades aplicables en SOC, Blue Team y proyectos educativos.

---

## 1️⃣ Conceptos Clave

- **OSINT (Open Source Intelligence):** Recopilación y análisis de información de fuentes públicas para generar inteligencia útil.  
- **Objetivo:** Identificar riesgos, activos expuestos y posibles vectores de ataque de manera ética.  
- **Áreas de aplicación:**  
  - Reconocimiento web y dominios  
  - Redes sociales y perfiles públicos  
  - Metadatos de documentos y archivos  
  - Información de infraestructura y servicios  

---

## 2️⃣ Flujo Básico OSINT

1. **Recolección**
   - Identificar objetivos y dominios.  
   - Buscar información pública en internet, redes sociales y motores de búsqueda.  
2. **Enumeración**
   - Subdominios: `sublist3r`, `Amass`  
   - Emails y usuarios: Hunter.io, email permutator  
   - Tecnologías web: Wappalyzer, BuiltWith  
3. **Análisis**
   - Correlacionar datos de diferentes fuentes  
   - Detectar activos expuestos o vulnerabilidades potenciales  
4. **Documentación**
   - Registrar hallazgos en un formato estructurado  
   - Indicar fuentes, fecha y contexto  
5. **Acción ética**
   - Solo para fines educativos o de defensa  
   - No explotar vulnerabilidades sin permiso  

---

## 3️⃣ Herramientas Gratuitas Destacadas

| Categoría                     | Herramientas / Web |
|--------------------------------|------------------|
| Dominio y Subdominios          | `sublist3r`, `Amass`, `crt.sh` |
| Emails y Usuarios              | Hunter.io, Email Permutator, theHarvester |
| Redes Sociales                 | LinkedIn, Twitter, GitHub, Facebook (público) |
| Tecnologías Web                | Wappalyzer, BuiltWith |
| Metadatos y Documentos         | ExifTool, FOCA, Metagoofil |
| Motor de búsqueda especializado| Google Dorks, Shodan Free, Censys |

---

## 4️⃣ Buenas Prácticas OSINT

- Mantener **legalidad y ética**: solo información pública y permitida.  
- Registrar siempre **fuente y fecha** de los hallazgos.  
- Correlacionar información con múltiples herramientas y fuentes.  
- Practicar en **entornos de laboratorio o simuladores** antes de aplicarlo en escenarios reales.  
- Automatizar tareas repetitivas con **Python o Bash scripting**.  

---

## 5️⃣ Objetivo

Proporcionar un **manual práctico de OSINT** para estudiantes, SOC L1 y Blue Teamers en 2026.  
Permite:  
- Reconocimiento de activos y superficie de ataque.  
- Análisis previo a incidentes de seguridad.  
- Aprendizaje ético y aplicado para laboratorios, mini retos y proyectos educativos.

---

## 🔗 Recursos Recomendados
- [OWASP Web Security Academy](https://owasp.org/www-project-web-security-testing-guide/)  
- [TryHackMe – OSINT Labs](https://tryhackme.com/)  
- [GitHub Awesome OSINT](https://github.com/lockfale/awesome-osint)  
- [Red Team Leaders OSINT Resources](https://courses.redteamleaders.com/)  

