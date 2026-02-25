# Multi-Event Correlation Strategy

## Objective

Detect ransomware behavior before encryption stage by correlating multiple suspicious activities instead of relying on single-event alerts.

## Why Multi-Event?

Single event detections generate false positives.
Behavior-based chained detection increases accuracy.

## Correlation Model

Stage 1: Suspicious PowerShell execution  
Stage 2: Defense evasion (Shadow copy deletion)  
Stage 3: Additional suspicious process activity  

If events occur within 10 minutes from same host:
→ Risk Score Increased
→ Severity: High

## Risk Scoring Model

Low Risk: 20  
Medium Risk: 50  
High Risk: 80+  

Risk increases with each suspicious stage detected.
