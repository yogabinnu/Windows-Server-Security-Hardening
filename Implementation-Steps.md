# Domain 02 – Demo 01
# Enhancing Windows Server 2022 Security (Advanced Hardening Guide)

## Objective
To enhance Windows Server 2022 security by protecting privileged accounts,
restricting unauthorized access, enforcing lockout policies, and reducing
attack surface to prevent cyber threats.

This hardening approach prepares systems for enterprise security environments
and aligns with privileged access protection practices used in CyberArk.

---

## Phase 1 – Account Hardening

### Step 1: Disable Guest Account

Why:
- Guest accounts allow anonymous access
- Commonly abused by attackers
- Can be used for lateral movement

Steps:
1. Open Server Manager
2. Click Tools → Computer Management
3. Go to Local Users and Groups → Users
4. Right-click Guest → Properties
5. Select "Account is disabled"
6. Click Apply → OK

Security Benefit:
Prevents unauthorized system access.

---

### Step 2: Disable Default Administrator Account

Why:
- Default admin account is a primary attack target
- Attackers try brute force on this account

Steps:
1. Open Computer Management
2. Go to Users
3. Right-click Administrator/DefaultAccount
4. Open Properties
5. Select "Account is disabled"
6. Click Apply → OK

Security Benefit:
Reduces risk of brute-force attacks on known admin accounts.

---

### Step 3: Create a New Secure Administrator Account

Why:
- Named admin accounts improve traceability
- Supports least privilege model

Steps:
1. Right-click inside Users → New User
2. Create user:
   Username: New_admin
   Full Name: New Admin
   Strong password
3. Click Create
4. Go to Groups → Administrators
5. Add New_admin to Administrators group
6. Click Apply → OK

Security Benefit:
Improves accountability and secure admin access management.

---

## Phase 2 – Access Control Hardening

### Step 4: Restrict Remote Access

Why:
- RDP is a common attack entry point
- Attackers perform brute-force login attempts

Steps:
1. Open Run → type sysdm.cpl
2. Go to Remote Settings
3. Select "Don’t allow remote connections"
4. Click Select Users
5. Add New_admin
6. Click OK

Security Benefit:
Restricts remote access to authorized administrators only.

---

## Phase 3 – Brute Force Protection

### Step 5: Configure Account Lockout Policy

Why:
- Prevents password guessing attacks
- Protects privileged accounts

Steps:
1. Open Run → type gpedit.msc
2. Navigate to:
   Computer Configuration →
   Windows Settings →
   Security Settings →
   Account Policies →
   Account Lockout Policy

3. Set:
   Account lockout threshold: 5 attempts
4. Click Apply → OK

Security Benefit:
Blocks repeated login attempts and prevents brute-force attacks.

---

## Phase 4 – Attack Surface Reduction

### Step 6: Disable Unnecessary Services

Why:
- Unused services increase security risks
- Attackers exploit vulnerable services

Steps:
1. Open Run → type services.msc
2. Right-click unnecessary service
3. Open Properties
4. Set Startup Type → Disabled
5. Click Apply → OK

Security Benefit:
Reduces system exposure and potential vulnerabilities.

---

## Phase 5 – Enterprise Security Enhancements

Additional advanced practices:

- Enable Windows Defender real-time protection
- Enable security auditing
- Monitor login events
- Prepare logs for SIEM monitoring
- Protect privileged account usage

---

## CyberArk Relevance

These hardening steps support:

- Secure privileged account management
- Safe onboarding into CyberArk Vault
- Reduced risk of admin account compromise
- Stronger access control for enterprise environments
