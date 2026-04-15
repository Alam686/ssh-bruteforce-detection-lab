# SSH Brute Force Detection Lab

## 1. Objective
To simulate and investigate SSH brute force attacks against a Linux server by analyzing authentication logs, network traffic, and attack patterns in order to understand brute force detection and response workflows.

--------------------------------------------------------------------------------------------------------------------------------------

## 2. Scenario
A SOC analyst receives an alert indicating repeated failed SSH login attempts against a Linux server. The objective is to determine whether the activity represents brute force authentication attempts, assess impact, and recommend remediation.

--------------------------------------------------------------------------------------------------------------------------------------

## 3. Lab Setup

| Component        |    Role  |
|----------        |    ------|
| Kali Linux       | Attacker / Analyst |
| Metasploitable2  | SSH Target |

-------------------------------------------------------------------------------------------------------------------------------------------

## 4. Baseline Authentication Log Review

Reviewed `/var/log/auth.log` prior to attack simulation to establish baseline authentication activity.

Observed:
- Normal sudo session activity
- Scheduled cron jobs
- SSH daemon logging reconnaissance-related connection anomalies

---------------------------------------------------------------------------------------------------------------------------------------

## 5. Findings

- Detected repeated failed SSH authentication attempts against user `msfadmin`
- Source IP `192.168.56.104` generated high-volume login failures within seconds
- PAM aggregated multiple failures, indicating automated attack behavior
- Brute-force attack successfully identified valid credentials: `msfadmin:msfadmin`
- Validated unauthorized SSH access using discovered credentials

--------------------------------------------------------------------------------------------------------------------------------------

## 6. MITRE ATT&CK Mapping

- T1110 – Brute Force
- T1078 – Valid Accounts


-----------------------------------------------------------------------------------------------------------------------------------------

## Remediation Verification

Re-ran brute-force attack against SSH service using original attack methodology after password hardening.

Result:
- No valid credentials discovered
- Brute-force attack unsuccessful

This confirms remediation effectively mitigated the original finding.














