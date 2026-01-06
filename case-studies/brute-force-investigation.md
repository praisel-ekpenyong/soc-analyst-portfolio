# Brute Force Attack Investigation

**Platform:** TryHackMe SOC Level 1  
**Role:** SOC Analyst (Tier 1)  
**Tools:** SIEM, Windows Event Logs  
**MITRE ATT&CK:** T1110 – Brute Force

---

## Alert Summary

A SIEM alert triggered due to multiple failed authentication attempts against a Windows host within a short time window, indicating possible brute force activity.

---

## Initial Assessment

- Alert severity: Medium  
- Alert type: Authentication anomaly  
- Affected system: Windows endpoint  
- Potential impact: Unauthorized account access  

Based on alert characteristics, the activity required further investigation to determine whether it was a false positive or a true brute force attempt.

---

## Investigation Steps

### Log Review
- Analyzed Windows Security Event Logs  
- Focused on authentication-related Event IDs:
  - **4625** – Failed logon attempts  
  - **4624** – Successful logons  

### Pattern Analysis
- Observed a high volume of failed logon attempts within a short timeframe  
- Multiple attempts targeted the same user account  
- Activity originated from a single external source IP address  

### Correlation
- Correlated timestamps, source IP, and usernames across events  
- Confirmed repetitive authentication attempts consistent with brute force behavior  

---

## Findings

- Activity matched known brute force attack patterns  
- No successful authentication observed during the investigation window  
- Mapped to **MITRE ATT&CK technique T1110 (Brute Force)**  

---

## Conclusion

This activity was confirmed as a **true positive brute force attempt** against a Windows system.

---

## Response & Recommendations

- Escalated the incident according to SOC procedures  
- Recommended blocking the source IP address  
- Suggested reviewing account lockout policies  
- Advised implementing MFA where applicable  

---

## Skills Demonstrated

- SIEM alert triage  
- Windows Event Log analysis  
- MITRE ATT&CK mapping  
- Incident documentation and escalation  
