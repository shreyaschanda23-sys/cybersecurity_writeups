# Lab 02 – WebApp02 Security Assessment

## Overview

This lab continued the assessment by analyzing a second web application. Information gathered during the previous phase was used to evaluate authentication, authorization, and multi-factor authentication mechanisms in a controlled environment.

---

# Objectives

- Enumerate application endpoints
- Analyze authentication workflows
- Validate recovered credentials
- Assess authorization controls
- Evaluate OTP implementation
- Review access to privileged functionality

---

# Methodology

## Reconnaissance

Directory enumeration was performed using **Feroxbuster** to identify accessible application resources.

This process revealed the application's client login functionality.

> **Screenshot:** `images/01-feroxbuster.png`

---

## Authentication Assessment

The client login workflow was analyzed using credentials obtained during the previous phase of the assessment.

This demonstrated how information disclosure in one application can impact the security of another related application.

> **Screenshot:** `images/02-login.png`

---

## Authorization Testing

After successful authentication, HTTP requests were inspected using Burp Suite.

Authorization-related parameters were evaluated to determine whether privilege levels were enforced on the server.

Testing demonstrated the importance of server-side authorization validation.

### Skills Practiced

- HTTP request manipulation
- Parameter tampering
- Authorization assessment

> **Screenshot:** `images/03-scope.png`

---

## OTP Security Assessment

The application required One-Time Password (OTP) verification before granting elevated access.

Within the authorized lab environment, **Burp Suite Intruder** was used to evaluate the effectiveness of the OTP protection mechanism and its resistance to automated guessing.

### Skills Practiced

- Burp Intruder
- Authentication workflow analysis
- OTP security testing

> **Screenshot:** `images/04-otp.png`

---

## Sensitive Data Exposure

Following successful completion of the authentication workflow, privileged functionality became available.

The assessment highlighted the importance of protecting sensitive information through strong authentication, authorization, and access-control mechanisms.

> **Screenshot:** `images/05-admin.png`

---

# Attack Flow

```
Reconnaissance
        ↓
Directory Enumeration
        ↓
Login Portal Analysis
        ↓
Authentication
        ↓
Authorization Testing
        ↓
OTP Security Assessment
        ↓
Administrative Access
        ↓
Sensitive Data Review
```

---

# Tools Used

- Burp Suite
- Burp Intruder
- Feroxbuster

---

# Key Learnings

This lab reinforced the importance of evaluating authentication and authorization as a complete workflow. Weak authorization logic, insufficient protection against automated authentication attacks, and improper access controls can significantly increase application risk. The exercise also demonstrated how findings from one assessment phase may contribute to testing related systems.

---

## Disclaimer

This write-up summarizes techniques practiced within an authorized training environment. Proprietary challenge details and solution-specific information have been intentionally omitted.
