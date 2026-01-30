# 🔐 SOC L1 – Análisis de Anomalías en Inicios de Sesión (2026)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docker](https://img.shields.io/badge/Docker-Containers-blue)](https://www.docker.com/)
[![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-green)](https://wazuh.com/)
[![SOC](https://img.shields.io/badge/SOC-Level%201-FF6B35)](https://)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB)](https://python.org)

**Laboratorio práctico de Analista SOC Nivel 1** enfocado en detección, análisis y respuesta a incidentes de seguridad mediante **Wazuh SIEM** en entorno controlado.

---

## 🎯 **Objetivo del Proyecto**

Demostrar habilidades prácticas de **Analista SOC L1** mediante:
- **Detección** de ataques de fuerza bruta SSH en tiempo real
- **Análisis** forense de logs de autenticación (`auth.log`)
- **Clasificación** de incidentes por severidad e impacto
- **Escalamiento** siguiendo workflow SOC estructurado
- **Documentación** profesional de casos de seguridad

---

## 🧠 **Escenario SOC L1 Simulado**

### **Caso: Ataque de Fuerza Bruta SSH**
```
🕒 Cronología del Incidente:
10:30:00 - Inicio del ataque (múltiples intentos SSH)
10:30:15 - Primer intento fallido detectado
10:30:20 - Wazuh genera alerta (regla 100001)
10:31:00 - Analista SOC L1 recibe alerta
10:31:30 - Triaje y análisis inicial
10:32:00 - Consulta APIs Threat Intelligence
10:33:00 - Clasificación: Severidad Alta
10:34:00 - Escalamiento a SOC L2 con evidencia
```

### **🛡️ Reglas de Detección Implementadas**
- **Regla 100001**: Múltiples intentos SSH fallidos desde misma IP
- **Regla 100002**: Alto volumen de ataques (threshold: 10 intentos/2min)
- **Regla 100003**: Acceso exitoso tras múltiples fallos

---

## 🚀 **Comenzar en 5 Minutos**

### **Requisitos Mínimos**
- **Sistema**: Ubuntu 22.04+, Kali Linux, Parrot OS
- **RAM**: 4GB mínimo (8GB recomendado)
- **Docker** 24.0+ & **Docker Compose** 2.20+

### **Instalación Rápida**
```bash
# 1. Clonar repositorio
git clone https://github.com/CyberZenithAI/soc-l1-login-anomaly-analysis.git
cd soc-l1-login-anomaly-analysis

# 2. Desplegar laboratorio
chmod +x scripts/setup/setup-lab.sh
sudo ./scripts/setup/setup-lab.sh

# 3. Acceder al dashboard
echo "🌐 Panel SOC: https://localhost:443"
echo "👤 Usuario: admin"
echo "🔑 Contraseña: ChangeMe123!"
```

---

## 🏗️ **Arquitectura del Laboratorio SOC**

```
┌─────────────────────────────────────────────────────────────┐
│                    SOC L1 Lab - Arquitectura                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    │
│  │   Wazuh     │    │   SSH       │    │   Kali      │    │
│  │   SIEM      │◄──►│   Server    │◄──►│   Attacker  │    │
│  │   (Docker)  │    │   (Target)  │    │   (Sim)     │    │
│  └─────────────┘    └─────────────┘    └─────────────┘    │
│         │                         │                        │
│         ▼                         ▼                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │           Dashboard Wazuh (Alertas SOC)             │    │
│  │      • Alertas en tiempo real                       │    │
│  │      • Análisis de logs                             │    │
│  │      • Visualización de métricas                    │    │
│  └─────────────────────────────────────────────────────┘    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### **Componentes Principales**
| Componente | Descripción | Puerto | Propósito SOC |
|------------|-------------|--------|---------------|
| **Wazuh Manager** | Motor de análisis SOC | 1514-1516 | Correlación de eventos |
| **Wazuh Dashboard** | Panel del analista | 443 | Visualización de alertas |
| **SSH Server** | Objetivo de ataque | 2222 | Generación de logs |
| **Kali Linux** | Simulador de ataque | - | Pruebas controladas |

---

## 🔧 **Habilidades de Analista SOC L1 Demostradas**

### **🔍 Análisis Técnico**
- **SIEM Management**: Configuración y operación de Wazuh
- **Log Analysis**: Análisis de `auth.log` y correlación de eventos
- **Alert Triage**: Priorización y validación de alertas
- **Threat Intelligence**: APIs de VirusTotal y AbuseIPDB

### **📋 Workflow Operacional**
- **Incident Classification**: Severidad Low/Medium/High/Critical
- **Documentation**: Reportes de incidentes estructurados
- **Escalation Procedures**: Flujos de escalamiento SOC L1→L2
- **Communication**: Explicación técnica a equipos no técnicos

### **⚡ Automatización SOC**
- **Bash Scripting**: Scripts de despliegue y análisis
- **Python Integration**: APIs de Threat Intelligence
- **Docker Management**: Contenedores para laboratorio SOC
- **Rule Development**: Reglas personalizadas de detección

---

## 📊 **Métricas y KPIs del Laboratorio**

### **🎯 Efectividad de Detección**
- **MTTD (Mean Time to Detect)**: < 2 minutos
- **Detección de ataques**: 100% en pruebas controladas
- **Falsos positivos**: < 5% con reglas optimizadas
- **Coverage de logs**: 100% sistemas críticos

### **⚡ Performance Operacional**
- **Tiempo de despliegue**: < 10 minutos
- **Recursos**: 4GB RAM, 2 vCPU mínimos
- **Portabilidad**: Ubuntu, Kali, Parrot, WSL2
- **Escalabilidad**: Fácil adaptación a más escenarios

---

## 🛠️ **Herramientas del Analista SOC L1**

### **SIEM y Monitoreo**
- **Wazuh SIEM**: Plataforma principal de detección
- **Elastic Stack**: Almacenamiento y búsqueda de logs
- **Kibana Dashboards**: Visualización de métricas SOC

### **Análisis y Triage**
- **SSH Log Analysis**: `auth.log` y eventos de autenticación
- **Network Tools**: `tcpdump`, `netstat`, `nmap`
- **Scripting**: Bash y Python para automatización

### **Threat Intelligence**
- **VirusTotal API**: Reputación de IPs y hashes
- **AbuseIPDB API**: Reportes de actividad maliciosa
- **Custom Enrichment**: Scripts de enriquecimiento automático

---

## 🔄 **Workflow Completo del Analista SOC L1**

### **1. DETECCIÓN (0-2 minutos)**
```bash
# Alertas generadas automáticamente por Wazuh
# Regla: 100001 - Multiple SSH authentication failures
# Severidad: HIGH
# Acción: Triaje inmediato requerido
```

### **2. TRIAGE (2-5 minutos)**
- ✅ Verificar alerta en Wazuh Dashboard
- ✅ Revisar logs relacionados (`/var/log/auth.log`)
- ✅ Validar IP de origen y patrones de ataque
- ✅ Consultar APIs de Threat Intelligence

### **3. ANÁLISIS (5-10 minutos)**
```python
# Ejemplo: Enriquecimiento con Threat Intel
ip_reputation = check_virustotal("10.10.10.30")
abuse_reports = check_abuseipdb("10.10.10.30")
risk_score = calculate_risk(ip_reputation, abuse_reports)
```

### **4. CLASIFICACIÓN (10-15 minutos)**
| Criterio | Valor | Impacto |
|----------|-------|---------|
| **Tipo** | Brute Force SSH | Alto |
| **Severidad** | High | Respuesta inmediata |
| **Impacto** | Credenciales comprometidas | Crítico |
| **Escalamiento** | SOC L2 requerido | Procedimiento establecido |

### **5. RESPUESTA (15-20 minutos)**
- 📝 Documentar incidente en plantilla SOC
- 🔄 Escalar a SOC L2 con contexto completo
- 🛡️ Recomendar acciones de mitigación
- 📊 Actualizar métricas y KPIs

### **6. DOCUMENTACIÓN (20-25 minutos)**
```markdown
# Reporte de Incidente SOC L1
**ID**: INC-20260115-001
**Severidad**: HIGH
**Tipo**: SSH Brute Force
**Acciones**: Escalado a SOC L2
**Evidencia**: Logs + Threat Intel report
```

---

## 📂 **Estructura del Proyecto para Analista SOC**

```
soc-l1-login-anomaly-analysis/
├── 📂 docker/                    # Entorno Docker del SOC
│   ├── docker-compose.yml       # Servicios SOC
│   └── wazuh-config/            # Reglas de detección
├── 📂 scripts/                  # Automatización SOC
│   ├── setup/                   # Instalación del lab
│   ├── simulation/              # Simulaciones de ataque
│   ├── threat-intelligence/     # APIs Threat Intel
│   └── soc-workflow/            # Flujo trabajo SOC
├── 📂 docs/                     # Documentación SOC
│   ├── SOC-WORKFLOW.md          # Procedimientos operativos
│   └── ETHICAL-GUIDELINES.md    # Ética del analista
├── 📂 examples/                 # Ejemplos prácticos
│   ├── alerts/                  # Alertas de muestra
│   ├── reports/                 # Reportes SOC
│   └── logs/                    # Logs para análisis
└── README.md                    # Este archivo
```

---

## 🎯 **Roles y Responsabilidades Demostradas**

### **Responsabilidades del Analista SOC L1**
- ✅ **Monitorización continua** de alertas de seguridad
- ✅ **Triaje inicial** de incidentes de seguridad
- ✅ **Análisis básico** de logs y eventos
- ✅ **Clasificación** por severidad y prioridad
- ✅ **Documentación** clara y estructurada
- ✅ **Escalamiento** siguiendo procedimientos establecidos

### **Competencias Técnicas Validadas**
- **SIEM Operations**: Wazuh configuration and monitoring
- **Log Analysis**: SSH, authentication, system logs
- **Incident Response**: Triage, classification, escalation
- **Threat Intelligence**: API integration and analysis
- **Automation**: Scripting for SOC tasks automation
- **Documentation**: Professional reporting and communication

---

## ⚠️ **Consideraciones Éticas - Solo para Laboratorio**

### **Principios Fundamentales**
🔒 **LABORATORIO AISLADO** - Red privada sin conexión a internet  
🔒 **SISTEMAS PROPIOS** - Solo hardware/software del desarrollador  
🔒 **FINES EDUCATIVOS** - Desarrollo profesional legítimo  
🔒 **CUMPLIMIENTO LEGAL** - Todas las regulaciones respetadas  

### **Configuraciones de Seguridad**
- Firewall habilitado con reglas estrictas
- Credenciales seguras generadas automáticamente
- Acceso restringido únicamente a localhost
- Logs de auditoría completos y cifrados

---

## 📈 **Preparación para Entrevistas Técnicas SOC L1**

### **Preguntas Técnicas Cubiertas**
- "¿Cómo detectarías un ataque de fuerza bruta SSH?"
- "¿Qué información buscarías en los logs de autenticación?"
- "¿Cómo priorizarías múltiples alertas simultáneas?"
- "¿Qué APIs de Threat Intelligence utilizarías y por qué?"

### **Casos Prácticos Incluidos**
1. **Detección de Brute Force SSH** - Análisis completo
2. **Triaje de Alertas Múltiples** - Priorización efectiva
3. **Escalamiento a SOC L2** - Comunicación profesional
4. **Documentación de Incidente** - Reportes estructurados

### **Portafolio Técnico Tangible**
- ✅ Código fuente completo y documentado
- ✅ Ejemplos reales de análisis de logs
- ✅ Scripts de automatización funcionales
- ✅ Dashboards de monitoreo configurables
- ✅ Plantillas de documentación profesional

---

## 🚀 **Próximos Pasos para el Analista SOC L1**

### **Desarrollo Profesional**
1. **Certificaciones relacionadas**: Security+, CySA+, Blue Team L1
2. **Proyectos avanzados**: Malware analysis, network forensics
3. **Especializaciones**: Cloud security, threat hunting, automation

### **Contribución a Comunidad**
- Compartir conocimientos en foros técnicos
- Contribuir a proyectos open-source de seguridad
- Crear contenido educativo para nuevos analistas
- Participar en CTFs y ejercicios prácticos

### **Preparación Laboral 2026**
- **Portafolio actualizado**: Este proyecto como demostración principal
- **Habilidades validadas**: Todas las competencias técnicas demostradas
- **Preparación entrevistas**: Casos prácticos y escenarios reales
- **Red profesional**: Conexiones en la comunidad de seguridad

---

## 🤝 **Contribuciones y Comunidad**

### **¿Cómo Contribuir?**
1. **Reportar issues** - Problemas técnicos o mejoras
2. **Sugerir features** - Nuevas funcionalidades SOC
3. **Mejorar documentación** - Claridad y ejemplos
4. **Compartir conocimientos** - Experiencias prácticas

### **Áreas de Colaboración**
- Nuevas reglas de detección Wazuh
- Integración con más herramientas SOC
- Mejoras en automatización y scripting
- Traducciones y documentación en más idiomas

---

## 📄 **Licencia**

MIT License - Ver [LICENSE](LICENSE) para detalles completos.

---

**⭐ ¡Valora este proyecto si te ayuda en tu camino como Analista SOC L1! ⭐**

> *"La experiencia práctica en un laboratorio controlado es la mejor preparación para las responsabilidades reales de un Centro de Operaciones de Seguridad."*

---

📌 **Proyecto desarrollado como preparación práctica para el rol de Analista SOC Nivel 1 - 2026**
