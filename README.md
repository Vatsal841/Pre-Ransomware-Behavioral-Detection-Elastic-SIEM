# Pre-Ransomware-Behavioral-Detection-Elastic-SIEM
SOC detection lab implementing behavioral-based pre-ransomware threat detection using Sysmon telemetry in Elastic SIEM, mapped to MITRE ATT&amp;CK with severity classification, risk scoring, and multi-event attack chain correlation.
# Pre-Ransomware Behavioral Detection & Incident Response  
### Using Sysmon + Elastic SIEM (Mapped to MITRE ATT&CK)


## 📌 Project Overview

This project demonstrates behavioral-based pre-ransomware threat detection using endpoint telemetry generated via Sysmon and analyzed in Elastic Stack (Elasticsearch + Kibana).

Custom detection logic was developed to identify suspicious execution activity, registry tampering, credential access attempts, abnormal file behavior, and network communication.  

All detections are mapped to the MITRE ATT&CK framework and enhanced with severity classification, risk scoring, and multi-event attack chain correlation.

---

## 🔎 Detection Coverage

The following behavioral detections were implemented:

- PowerShell Execution Abuse (T1059.001)  
- Command Prompt Execution (T1059)  
- Registry Tampering (T1112)  
- LSASS Access – Credential Dumping Indicator (T1003)  
- Suspicious File Creation Activity (T1486)  
- Suspicious Network Activity (T1071)  
- Abnormal Parent-Child Process Relationships
  
---

## 🧠 MITRE ATT&CK Mapping

| Detection | MITRE Technique | Tactic |
|------------|----------------|--------|
| PowerShell Abuse | T1059.001 | Execution |
| CMD Execution | T1059 | Execution |
| Registry Tampering | T1112 | Defense Evasion |
| LSASS Access | T1003 | Credential Access |
| File Activity | T1486 | Impact |
| Network Activity | T1071 | Command & Control |

---

## ⚖ Severity & Risk Classification

| Detection | Severity | Risk Score |
|------------|----------|------------|
| LSASS Access | High | 90 |
| Registry Tampering | High | 80 |
| PowerShell Abuse | Medium | 70 |
| Network Activity | Medium | 75 |
| File Activity | Medium | 65 |
| CMD Execution | Low | 50 |

---

## 🔗 Threat Correlation & Attack Chain Analysis (Level 3)

Multi-event correlation was performed to simulate realistic pre-ransomware attack progression.

### Simulated Attack Flow:
This correlation increases detection confidence by combining individual suspicious events into a high-confidence attack chain indicator.

---

## 🚨 Incident Response Playbook

1. Detection – Suspicious behavior identified via Sysmon telemetry.  
2. Analysis – Reviewed command-line arguments and process relationships.  
3. Containment – Recommended host isolation from network.  
4. Eradication – Terminated malicious processes and removed persistence.  
5. Recovery – Verified system integrity and restored normal operations.  
6. Lessons Learned – Improved detection thresholds and correlation logic.

---

## 🧪 False Positive Considerations

Each detection was evaluated against legitimate system activity to reduce noise through:

- Parent-child validation  
- Command-line inspection  
- Time-based correlation  
- Behavioral threshold analysis  

---

## 🎯 Skills Demonstrated

- SIEM Log Analysis  
- Behavioral Detection Engineering  
- MITRE ATT&CK Mapping  
- Threat Correlation  
- Incident Response Planning  
- Threat Hunting Fundamentals  

---
## 📥 Project Documentation

👉 **[Click Here to View Full PDF Report](Reports/Incident-Response-Report.pdf)**
