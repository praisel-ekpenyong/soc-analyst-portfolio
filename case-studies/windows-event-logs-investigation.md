# Windows Event Logs Investigation – Finding Suspicious Activity

**Platform:** SOC Simulation (Generic)  
**Role:** SOC Analyst (Tier 1)  
**Tools:** Windows Event Logs, SIEM  
**MITRE ATT&CK:** T1059 – Command and Scripting Interpreter

---

## Alert Summary

A SIEM alert was generated based on suspicious Windows event log activity, indicating potential malicious behavior on a Windows endpoint.

---

## Initial Assessment

- Alert severity: Medium  
- Alert type: Suspicious host activity  
- Affected system: Windows endpoint  
- Potential impact: Unauthorized command execution  

The alert required log-level investigation to determine whether the activity was legitimate or malicious.

---

## Investigation Steps

### Event Log Analysis
- Reviewed Windows Security Event Logs  
- Focused on key Event IDs:
  - **4688** – Process creation  
  - **4624** – Successful logon  
  - **4625** – Failed logon  

### Behavioral Analysis
- Identified unusual process execution shortly after user logon  
- Observed command-line activity inconsistent with normal user behavior  
- Noted execution from non-standard directories  

### Correlation
- Correlated logon events with process creation timestamps  
- No scheduled tasks or administrative changes justified the activity  

---

## Findings

- Event log patterns indicated suspicious command execution  
- Activity was not associated with known legitimate software  
- Behavior mapped to **MITRE ATT&CK T1059 (Command and Scripting Interpreter)**  

---

## Conclusion

The activity was classified as a **true positive suspicious host activity** based on abnormal Windows event log behavior.

---

## Response & Recommendations

- Escalated the incident for further analysis  
- Recommended endpoint isolation if activity continued  
- Suggested enhanced monitoring of the affected user account  
- Advised review of PowerShell and command-line logging policies  

---

## Skills Demonstrated

- Windows Event Log analysis  
- Log correlation and timeline analysis  
- MITRE ATT&CK mapping  
- Incident classification and escalation  
