Open SOC & XDR Lab 

##  Overview
This project demonstrates how to build a fully open-source **SOC (Security Operations Center)** with **XDR capabilities**, using:

- **Wazuh SIEM** – Log collection, detection rules, dashboards
- **IRIS Case Management** – Incident triage and investigation
- **Shuffle SOAR** – Automated playbooks & enrichment
- **MISP** – Threat Intelligence feeds and IOC enrichment
- **Linux & Windows endpoints** – Agents forwarding logs

The goal: **Automated detection + response for enterprise & IoT environments**.


## Architecture
![SOC Architecture](architecture/soc-architecture.png)


##  Components

### 1. Wazuh SIEM
- Custom detection rules for:
  - SSH brute force
  - File Integrity Monitoring (e.g., `/etc/passwd` edits)
  - Windows RDP failed logins
  - EICAR test file
- Integration scripts:
  - Forward alerts to IRIS
  - Send alerts to Shuffle webhook

### 2. IRIS
- Case management for SOC alerts
- API integration with Wazuh & Shuffle
- Predefined case templates

### 3. Shuffle SOAR
- Workflows:
  - IOC enrichment (VirusTotal, MISP, AbuseIPDB)
  - Auto-block malicious IPs
  - Push enriched cases to IRIS

### 4. MISP
- OSINT threat feeds enabled
- API key configured for Shuffle enrichment


## Endpoints
- **Linux Endpoint (Ubuntu on AWS/GCP/Azure)** with Wazuh agent
- **Windows Endpoint (Local VM)** with Wazuh agent


##  Test Scenarios
- Linux: SSH brute force (Hydra), FIM changes
- Windows: Failed RDP logins, EICAR malware test
- SOC Flow: Alerts → Wazuh → IRIS case → Shuffle enrichment → Automated response


##  Outcome
A fully functional **open-source SOC + XDR platform** with:
- Proactive detection
- Automated response
- Threat intel enrichment
- Case tracking & reporting


 📚 Credits
Built using:
- [Wazuh](https://wazuh.com)
- [IRIS DFIR](https://dfir-iris.github.io)
- [Shuffle SOAR](https://shuffler.io)
- [MISP](https://www.misp-project.org)

Author: **Banu Prakash E**  
LinkedIn: [linkedin.com/in/banu-prakash-e](https://linkedin.com/in/banu-prakash
