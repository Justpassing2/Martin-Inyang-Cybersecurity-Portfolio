# Wazuh Alert Investigation Report
Analyst: Martin Inyang  
Tool: Wazuh SIEM  
Date: 2026

## 1. Alert Overview
**Alert ID:** 53421  
**Category:** Unauthorized Access Attempt  
**Severity:** High  
**Technique:** MITRE ATT&CK T1110 (Brute Force)

## 2. Indicators
- Multiple failed SSH login attempts  
- External IP source: 185.232.xx.xx  
- Rapid repeated authentication failures  

## 3. Investigation Steps
1. Reviewed Wazuh alert metadata  
2. Checked `/var/log/auth.log` for failed login sequences  
3. Correlated timestamps with Wazuh rule triggers  
4. Confirmed no successful login  

## 4. Recommended Actions
- Block malicious IP  
- Enforce fail2ban  
- Require SSH key authentication  
- Harden server configuration (CIS benchmark)

## 5. Conclusion
Suspicious brute-force activity detected; no compromise occurred.
