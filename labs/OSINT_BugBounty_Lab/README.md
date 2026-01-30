# 🔍 Investigación OSINT para Bug Bounty - Proyecto de Portafolio

## 📋 Descripción del Proyecto
Proyecto educativo que demuestra una metodología completa de Inteligencia de Fuentes Abiertas (OSINT) aplicada a la fase de reconocimiento en programas de Bug Bounty. El objetivo es identificar activos digitales, información expuesta y posibles vectores de ataque iniciales utilizando **exclusivamente fuentes públicas de información**.

**⚠️ NOTA ÉTICA IMPORTANTE:** Este proyecto se realizó siguiendo estrictamente las políticas de programas públicos de Bug Bounty. Todos los datos sensibles han sido ofuscados en las capturas de pantalla. Nunca se accedió a sistemas sin autorización.

## 🎯 Objetivos del Proyecto
- Demostrar habilidades en recopilación y análisis de información pública
- Identificar la superficie de ataque de un objetivo ético
- Documentar un proceso metodológico reproducible
- Crear un informe de inteligencia para fases posteriores de testing

## 📊 Metodología Aplicada

### Fase 1: Preparación Ética
1. Selección de empresa con programa público de Bug Bounty
2. Revisión exhaustiva del alcance permitido
3. Configuración de entorno seguro y anónimo

### Fase 2: Descubrimiento de Activos
- Enumeración de subdominios con herramientas combinadas
- Búsqueda en registros de certificados SSL
- Identificación de infraestructura en la nube

### Fase 3: Análisis de Servicios
- Fingerprinting de tecnologías con Shodan/Censys
- Identificación de servicios expuestos
- Detección de configuraciones por defecto

### Fase 4: Búsqueda de Información Sensible
- GitHub Dorking para credenciales expuestas
- Análisis de metadatos en documentos públicos
- Verificación en bases de datos de filtraciones

### Fase 5: Correlación y Priorización
- Creación de mapa de relaciones con Maltego
- Clasificación de activos por criticidad
- Generación de informe de hallazgos

## 🛠️ Herramientas Utilizadas

### Descubrimiento de Activos
| Herramienta | Propósito | Enlace |
|-------------|-----------|--------|
| Subfinder | Enumeración de subdominios | [GitHub](https://github.com/projectdiscovery/subfinder) |
| Amass | Mapeo de superficie de ataque | [GitHub](https://github.com/OWASP/Amass) |
| DNSDumpster | Búsqueda visual de DNS | [Sitio Web](https://dnsdumpster.com/) |

### Análisis de Servicios
| Herramienta | Propósito | Enlace |
|-------------|-----------|--------|
| Shodan | Motor de búsqueda de dispositivos | [Sitio Web](https://www.shodan.io/) |
| Censys | Búsqueda de activos de Internet | [Sitio Web](https://censys.io/) |
| BuiltWith | Detección de tecnologías web | [Sitio Web](https://builtwith.com/) |

### Búsqueda de Información
| Herramienta | Propósito | Enlace |
|-------------|-----------|--------|
| GitDorker | Búsqueda en GitHub | [GitHub](https://github.com/obheda12/GitDorker) |
| ExifTool | Extracción de metadatos | [Sitio Web](https://exiftool.org/) |
| DeHashed | Búsqueda en filtraciones | [Sitio Web](https://www.dehashed.com/) |

### Automatización y Visualización
| Herramienta | Propósito | Enlace |
|-------------|-----------|--------|
| Maltego | Visualización de relaciones | [Sitio Web](https://www.maltego.com/) |
| SpiderFoot | Automatización OSINT | [GitHub](https://github.com/smicallef/spiderfoot) |
| OSINT Framework | Directorio de recursos | [Sitio Web](https://osintframework.com/) |

## 🖼️ Capturas de Pantalla

### 1. Enumeración de Subdominios
![Enumeración de Subdominios](assets/screenshots/01-subdominios.png)
*Resultados ofuscados de la enumeración de subdominios mostrando la metodología aplicada.*

### 2. Análisis con Shodan
![Búsqueda en Shodan](assets/screenshots/02-shodan-result.png)
*Búsqueda de servicios expuestos con datos sensibles ofuscados.*

### 3. Mapa de Relaciones
![Mapa de Maltego](assets/screenshots/03-maltego-graph.png)
*Visualización de relaciones entre activos descubiertos.*

### 4. Diagrama de Metodología
![Diagrama de Flujo](assets/diagrams/metodologia-osint.png)
*Flujo completo de la investigación OSINT aplicada.*

## 📊 Hallazgos Relevantes (Ejemplo)

### Hallazgo 1: Subdominio de Desarrollo Expuesto
**Descripción:** Descubrimiento de un subdominio `staging-api.[empresa].com` no documentado públicamente.
**Metodología:** Enumeración mediante Certificate Transparency Logs.
**Impacto Potencial:** ALTO - Punto de entrada a entornos de preproducción.
**Recomendación:** Revisión de exposición de subdominios no esenciales.

### Hallazgo 2: Documento con Metadatos Sensibles
**Descripción:** PDF público en el sitio web con nombres de usuario internos en metadatos.
**Metodología:** Extracción con ExifTool.
**Impacto Potencial:** MEDIO - Información para ataques de ingeniería social.
**Recomendación:** Limpieza de metadatos en documentos públicos.

### Hallazgo 3: Repositorio con Configuraciones
**Descripción:** Repositorio GitHub público con archivos de configuración de ejemplo.
**Metodología:** GitHub Dorking con búsquedas específicas.
**Impacto Potencial:** MEDIO-ALTO - Posible exposición de estructuras internas.
**Recomendación:** Revisión de políticas de repositorios públicos.

## 📚 Lecciones Aprendidas

### ✅ Lo que Funcionó Bien
1. **Combinación de herramientas** múltiples para cobertura completa
2. **Documentación en tiempo real** de cada hallazgo
3. **Validación cruzada** de información entre diferentes fuentes
4. **Persistencia** en la búsqueda de activos no obvios

### 🎯 Mejoras Identificadas
1. Necesidad de mejores filtros para reducir falsos positivos
2. Establecimiento de criterios más claros de priorización
3. Automatización de reportes para ganar eficiencia
4. Mayor profundidad en análisis de correlaciones

## 🚀 Mejoras Futuras

### Corto Plazo (1 mes)
- [ ] Crear scripts de automatización para el flujo básico
- [ ] Desarrollar plantillas estandarizadas de documentación
- [ ] Implementar sistema de scoring para priorización

### Medio Plazo (3 meses)
- [ ] Integrar APIs de herramientas premium (Shodan, Censys)
- [ ] Desarrollar dashboard de visualización personalizado
- [ ] Crear base de conocimiento de hallazgos recurrentes

### Largo Plazo (6 meses)
- [ ] Sistema de monitoreo continuo de activos
- [ ] Integración con plataformas de Bug Bounty
- [ ] Módulo de alertas para cambios en superficie de ataque

## 👤 Autor

**Joaquin** - Estudiante de Ciberseguridad y OSINT

- 🌐 [Portafolio GitHub](https://github.com/CyberZenithAI)
- 💼 [LinkedIn](https://linkedin.com/in/joaquin-ocampo-cybersecurity)
- 📧 Correo: webdev.student123@outlook.com 

### 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para detalles.

---

**🔒 Nota de Responsabilidad:** Este proyecto es estrictamente educativo. Todas las técnicas se aplicaron dentro del alcance ético de programas públicos de Bug Bounty. El autor no se hace responsable del mal uso de esta información.
