# Cheatsheets SIEM & Workflows SOC

Este documento recopila **resúmenes rápidos de reglas, flujos y técnicas SOC** para facilitar el aprendizaje y la práctica en laboratorios y entornos simulados.  
Ideal para SOC L1, Blue Team y estudiantes de ciberseguridad en 2026.

---
## 1️⃣ Tipos de Alertas Comunes en SIEM

- **Autenticación**
  - Login exitoso / fallido
  - Bloqueos de cuentas
  - Inicio de sesión remoto (RDP/SSH)

- **Red**
  - Tráfico sospechoso en puertos no estándar
  - Escaneos de red (port scanning)
  - Tráfico hacia IPs maliciosas conocidas

- **Aplicaciones**
  - Errores críticos en logs de aplicaciones
  - SQL Injection / XSS detectado
  - Cambios en configuraciones críticas

---
## 3️⃣ Reglas y Patrones de Detección Frecuentes

- **SSH Brute Force**
```snort
alert ssh any any -> any any (msg:"SSH Brute Force"; threshold: type both, track by_src, count 5, seconds 60; sid:100001;)
RDP Fallidos Recurrentes
alert tcp any any -> any 3389 (msg:"RDP Failed Login"; threshold: type both, track by_src, count 5, seconds 120; sid:100002;)
Intentos de SQL Injection
alert http any any -> any any (msg:"SQLi Attempt"; content:"' OR 1=1"; nocase; sid:100003;)

---

## **Parte 5: Comandos y Consultas Útiles**

```markdown
## 4️⃣ Comandos y Consultas Útiles

### Logs Windows
```powershell
Get-EventLog -LogName Security -Newest 50

Logs Linux
tail -f /var/log/auth.log
grep "Failed password" /var/log/auth.log

Análisis de PCAP
tshark -r capture.pcap -Y "tcp.flags.syn==1 && tcp.flags.ack==0"

SIEM básico (Wazuh / Splunk)
# Buscar alertas críticas
wazuh-logtest /var/ossec/logs/alerts/alerts.log


---

## **Parte 6: Buenas Prácticas SOC y Objetivo**

```markdown
## 5️⃣ Buenas Prácticas SOC

- Documentar cada paso en ticket ITSM.  
- Validar falsos positivos antes de escalar.  
- Correlacionar logs de múltiples fuentes.  
- Mantener reglas SIEM actualizadas y testeadas.  
- Practicar con laboratorios y simuladores antes de producción.  

---

## 🎯 Objetivo

Tener a mano un **resumen práctico y rápido** de reglas SIEM, workflows y comandos esenciales para SOC L1 y Blue Team. Ideal para laboratorios, mini retos y entornos de aprendizaje 2026.
