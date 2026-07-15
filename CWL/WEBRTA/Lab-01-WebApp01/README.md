# Lab 01 – WebApp01 Security Assessment

## Overview

This lab focused on assessing a web application using a structured penetration testing methodology. The assessment included reconnaissance, endpoint enumeration, authentication testing, XML security analysis, server-side request testing, and encoded data analysis.

---

# Objectives

- Enumerate exposed services
- Discover hidden application endpoints
- Analyze application functionality
- Assess authentication mechanisms
- Test for SQL Injection
- Evaluate XML parsing security
- Assess SSRF behavior
- Analyze encoded application data

---

# Methodology

## Reconnaissance

The assessment began with reconnaissance to identify the application's attack surface.

### Network Enumeration

- Performed service discovery using **Nmap**.
- Identified exposed services for further assessment.

### Directory Enumeration

Using **Feroxbuster**, hidden directories and endpoints were discovered, revealing additional application functionality not visible through normal navigation.

> **Screenshot:** `images/02-nmap.png`
>

---

## Application Analysis

A hidden dashboard was identified during enumeration. Manual inspection of the application helped identify functionality and user roles that guided subsequent testing.

> **Screenshot:** `images/04-dashboard.png`

---

## SQL Injection Assessment

Input parameters were tested for SQL Injection vulnerabilities using manual techniques.

Successful testing demonstrated insufficient input validation, allowing elevated application access within the lab environment.

### Skills Practiced

- Parameter testing
- HTTP request analysis
- Authentication bypass assessment
- Manual payload construction

> **Screenshot:** `images/05-sqli.png`

---

## XML External Entity (XXE)

The application accepted XML input, allowing assessment of XML parser security.

Testing demonstrated how insecure XML parser configurations can lead to local file disclosure.

### Skills Practiced

- XML payload creation
- XXE testing
- Local file disclosure assessment

> **Screenshot:** `images/07-xxe.png`

---

## Server-Side Request Forgery (SSRF)

Server-side request functionality was evaluated to determine whether internal resources could be accessed.

The assessment demonstrated the impact of insufficient validation of outbound server requests.

### Skills Practiced

- Internal resource testing
- SSRF validation
- HTTP request analysis

---

## Data Analysis

Information retrieved during testing required decoding before analysis.

The exercise reinforced the importance of recognizing hexadecimal and Base64 encodings commonly encountered during penetration testing engagements.

### Skills Practiced

- Hexadecimal decoding
- Base64 decoding
- Data interpretation

> **Screenshot:** `images/11-decode.png`

---

# Attack Flow

```
Reconnaissance
        ↓
Nmap Enumeration
        ↓
Feroxbuster Enumeration
        ↓
Application Analysis
        ↓
SQL Injection Testing
        ↓
Administrative Access
        ↓
XXE Assessment
        ↓
Local File Disclosure
        ↓
SSRF Assessment
        ↓
Encoded Data Analysis
```

---

# Tools Used

- Burp Suite
- Nmap
- Feroxbuster

---

# Key Learnings

This lab demonstrated how multiple vulnerabilities can be chained together during a penetration test. Starting with reconnaissance and endpoint discovery, the assessment progressed through authentication testing, XML parser analysis, and server-side request evaluation, highlighting the importance of secure input validation, hardened XML parser configurations, and proper server-side request controls.

---

## Disclaimer

This document summarizes the methodology followed during an authorized training exercise. Challenge-specific solutions and sensitive details have been omitted.
