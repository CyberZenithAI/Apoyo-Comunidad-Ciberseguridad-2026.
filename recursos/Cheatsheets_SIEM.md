# Cheatsheets SIEM & Workflows SOC

Este documento recopila **resúmenes rápidos de reglas, flujos y técnicas SOC** para facilitar el aprendizaje y la práctica en laboratorios y entornos simulados.

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

## 2️⃣ Workflows SOC Nivel 1 (L1)
1. **Detección**
   - Recepción de alerta desde SIEM (Wazuh, Splunk, etc.)
   - Validación de falso positivo
2. **Clasificación**
   - Severidad: Baja / Media / Alta / Crítica
   - Tipo: Malware, Phishing, Recon, Intrusión
3. **Enriquecimiento**
   - VirusTotal / AbuseIPDB / Shodan
   - Log correlación (auth.log, Windows Event Logs, PCAP)
4. **Escalamiento**
   - Documentación en ticket ITSM / SOC
   - Escalamiento a SOC L2 / Red Team según impacto
5. **Cierre**
   - Remediación confirmada
   - Lessons Learned y actualización de reglas SIEM

---

## 3️⃣ Reglas y patrones de detección frecuentes
- **SSH Brute Force**
