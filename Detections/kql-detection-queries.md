# KQL Detection Queries – Pre-Ransomware Behavioral Detection

## 1. Suspicious PowerShell Execution (Encoded Command)

Event Source: Sysmon Event ID 1 (Process Create)

Detection Logic:
process.name: "powershell.exe" AND
process.command_line: "*EncodedCommand*"

MITRE Technique:
T1059.001 – Command and Scripting Interpreter: PowerShell

---

## 2. Shadow Copy Deletion (Ransomware Preparation)

Event Source: Sysmon Event ID 1

Detection Logic:
process.command_line: "*vssadmin delete shadows*" OR
process.command_line: "*wmic shadowcopy delete*"

MITRE Technique:
T1490 – Inhibit System Recovery

---

## 3. Suspicious Command Prompt Chaining

Detection Logic:
process.name: "cmd.exe" AND
process.command_line: "*&&*"

MITRE Technique:
T1059 – Command and Scripting Interpreter

---

## 4. Credential Dumping Behavior

Detection Logic:
process.command_line: "*lsass*" OR
process.command_line: "*procdump*"

MITRE Technique:
T1003 – OS Credential Dumping

---

## 5. Multi-Event Correlation Logic (Pre-Ransomware Pattern)

Detection Strategy:
- PowerShell execution
- Followed by shadow copy deletion
- Followed by suspicious process spawning

If all 3 events occur within 10 minutes → Raise High Severity Alert.
