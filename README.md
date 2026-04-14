# SSH Brute Force Detection Lab

## 1. Objective
To simulate and investigate SSH brute force attacks against a Linux server by analyzing authentication logs, network traffic, and attack patterns in order to understand brute force detection and response workflows.

---

## 2. Scenario
A SOC analyst receives an alert indicating repeated failed SSH login attempts against a Linux server. The objective is to determine whether the activity represents brute force authentication attempts, assess impact, and recommend remediation.

---

## 3. MITRE ATT&CK Mapping
- T1110 – Brute Force
- T1078 – Valid Accounts (if authentication succeeds)

---

## 4. Lab Setup

| Component        |    Role  |
|----------        |    ------|
| Kali Linux       | Attacker / Analyst |
| Metasploitable2  | SSH Target |