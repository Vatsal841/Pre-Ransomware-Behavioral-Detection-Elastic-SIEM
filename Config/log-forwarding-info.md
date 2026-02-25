# Log Forwarding Configuration

Logs from Windows 11 VM were forwarded to Elastic SIEM (Ubuntu VM).

Forwarding Method:
- NXLog / Elastic Agent (Standalone Mode)

Pipeline Flow:

Windows 11 (Sysmon Logs)
        ↓
Log Forwarder
        ↓
Elastic SIEM
        ↓
Kibana Detection Engine

This setup enables centralized log analysis and detection engineering.
