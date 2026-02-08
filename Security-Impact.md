# Security Impact & Risk Reduction Analysis

## Overview
This project focuses on strengthening Windows Server 2022 security by protecting privileged accounts and reducing the attack surface.

The controls implemented are commonly used in enterprise environments before onboarding systems into Privileged Access Management (PAM) solutions like CyberArk.

---

## Key Security Risks Addressed

### 1. Default Administrator Account Risk
Risk:
- Attackers target default admin account names
- High chance of brute-force attempts

Mitigation:
- Disabled built-in Administrator
- Created a unique named admin account

Security Benefit:
- Reduces attack predictability
- Improves accountability

---

### 2. Guest Account Risk
Risk:
- Unauthorized anonymous access
- Potential lateral movement

Mitigation:
- Disabled Guest account

Security Benefit:
- Blocks untrusted access paths

---

### 3. Brute Force Attack Risk
Risk:
- Password guessing attacks
- Privileged account compromise

Mitigation:
- Configured account lockout threshold (5 attempts)

Security Benefit:
- Stops repeated login attempts
- Generates security logs for monitoring

---

### 4. Remote Access Exposure
Risk:
- RDP is a major attack vector
- Unauthorized remote logins

Mitigation:
- Restricted remote access to authorized admin only

Security Benefit:
- Reduces external attack surface

---

### 5. Unnecessary Services Risk
Risk:
- Vulnerable services can be exploited
- Increases system exposure

Mitigation:
- Disabled unused services

Security Benefit:
- Minimizes attack surface

---

## CyberArk Relevance

This hardening supports CyberArk onboarding by:

- Securing privileged ac
