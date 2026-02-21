# Splunk Log Analysis Report
Analyst: Martin Inyang  
Date: 2025  

## Purpose
Analyze system authentication logs to identify abnormal login patterns and suspicious activity.

## Findings

### 1. Suspicious Login from Unusual Location
- **User:** admin  
- **Source IP:** 223.142.xx.xx  
- **Issue:** Login occurred outside business hours, geolocation mismatch

### 2. Excessive Failed Logins
- 43 failed attempts within 2 minutes  
- Indicates brute-force or credential stuffing attempt

### 3. Privilege Escalation Attempts
- Abnormally frequent use of `sudo` commands  

## Splunk Queries Used
```
index=auth sourcetype=linux_secure action=failure
```
```
index=auth user=admin | stats count by src
```

## Recommendations
- Enable MFA on privileged accounts  
- Improve password policy settings  
- Add alerts for geolocation-based anomalies  
