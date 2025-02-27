---
id: application-security-checklist
title: Application Security Checklist
sidebar_label: Application Security Checklist
---


# Application Security Checklist

This document provides a comprehensive guide to application security requirements, organized by security domains and categories. It serves as a reference for implementing security controls throughout the application development lifecycle.

## Table of Contents

1. [Architecture & Design](#1-architecture--design)
2. [Authentication](#2-authentication)
3. [Session Management](#3-session-management)
4. [Access Control](#4-access-control)
5. [Input Validation & Output Encoding](#5-input-validation--output-encoding)
6. [Cryptography & Data Protection](#6-cryptography--data-protection)
7. [Logging & Error Handling](#7-logging--error-handling)
8. [Communications Security](#8-communications-security)
9. [Malicious Code & File Management](#9-malicious-code--file-management)
10. [Web Services & API Security](#10-web-services--api-security)
11. [Configuration & Deployment](#11-configuration--deployment)

---

## 1. Architecture & Design

### 1.1 Secure Software Development Lifecycle

- Implement a secure software development lifecycle that addresses security in all stages of development and aligns to established secure coding guidelines.

### 1.2 Authentication Architecture

- Ensure communications between application components, including APIs, middleware, and data layers, are authenticated with the least necessary privileges.
- Enforce consistent authentication security control strength across all authentication pathways and identity management APIs, avoiding weaker alternatives.

### 1.3 Input and Output Architecture

- Define clear requirements for handling and processing data based on type, content, and applicable laws, regulations, and policy compliance.
- Ensure output encoding occurs close to or by the interpreter for which it is intended.

### 1.4 Errors, Logging and Auditing Architecture

- Securely transmit logs to a preferably remote system for analysis, detection, alerting, and escalation.

### 1.5 Data Protection and Privacy Architecture

- Define protection levels with associated requirements (encryption, integrity, retention, privacy) and apply them in the architecture.

### 1.6 Communications Architecture

- Encrypt communications between components, particularly when components are in different containers, systems, sites, or cloud providers.
- Verify the authenticity of each side in a communication link to prevent person-in-the-middle attacks (e.g., validate TLS certificates and chains).

### 1.7 Malicious Software Architecture

- Implement source code control with procedures ensuring check-ins are accompanied by issues or change tickets, with access control and user identification for traceability.

### 1.8 Configuration Architecture

- Segregate components of differing trust levels through well-defined security controls, firewall rules, API gateways, reverse proxies, or cloud-based security groups.
- Avoid using unsupported, insecure, or deprecated client-side technologies (NSAPI plugins, Flash, Shockwave, ActiveX, Silverlight, NACL, client-side Java applets).

## 2. Authentication

### 2.1 Password Security

- Enforce password policies that align with organizational requirements, including complexity, length, and history.
- Implement secure password reset functionality via multi-factor authentication or one-time use password reset links sent only to registered email addresses.
- Ensure password validation errors do not reveal which part of the credentials was incorrect.
- Store passwords using strong, adaptive, and salted hashing algorithms designed for password storage.
- Ensure password entry fields are not vulnerable to automated submission via hidden fields.

### 2.2 General Authenticator Security

- Implement anti-automation controls to mitigate breached credential testing, brute force, and account lockout attacks.
- Require secondary authentication for critical transactions (payments, contact updates, password resets).
- Verify submitted credentials are not transmitted in clear text or easily decryptable forms.
- Allow users to change their password, with appropriate validations and verification of current password.
- Enable FIDO or multi-factor authentication where possible.

### 2.3 Authenticator Lifecycle

- Generate secure, random initial passwords or activation codes that comply with password policies and must be changed upon first login.
- Send renewal instructions with sufficient time to renew time-bound authenticators.

### 2.4 Credential Storage

- Store passwords in a form resistant to offline attacks, using approved one-way key derivation or password hashing functions with salts and appropriate cost factors.
- Store a unique salt value and the resulting hash for each credential.

### 2.5 Credential Recovery

- Eliminate shared or default accounts (e.g., "root", "admin", "SAP*", "sa"). If required due to dependencies, change default passwords to stronger ones.
- Notify users when authentication factors are changed or replaced.
- Implement a secure credential recovery mechanism that does not reveal current passwords.

### 2.6 Out-of-Band Verifier

- Expire out-of-band authentication requests, codes, or tokens (SMS, digital tokens) after 10 minutes.
- Ensure out-of-band authentication requests, codes, or tokens are only usable once and only for the original authentication request.
- Verify the out-of-band authentication channel is physically in possession of the user before initial registration and before any re-issuance or recovery.
- Protect the application against SIM-swapping attacks by using tokens instead of SMS, confirming possession of the SIM, or verifying identity through other means.
- Require re-authentication, secondary verification, or one-time nonces for sensitive feature access or transactions.

### 2.7 One-Time Verifier

- Define a lifetime before expiring time-based OTPs.
- Protect symmetric keys used for OTP verification using hardware security modules or secure operating system-based key storage.
- Ensure OTPs are only usable once and only for the original authentication request.

### 2.8 Cryptographic Verifier

- Use approved cryptographic algorithms for the generation, seeding, and verification of cryptographic verifiers.

## 3. Session Management

### 3.1 Fundamental Session Management Security

- Never reveal session tokens in URL parameters.

### 3.2 Session Binding

- Generate a new session token on user authentication.
- Ensure session tokens possess at least 64 bits of entropy.
- Implement proper session validation measures to prevent session hijacking.

### 3.3 Session Termination

- Require re-authentication periodically during active use and after idle periods for persistent sessions.
- Provide an option to terminate all other active sessions after a successful password change, effective across the application, federated login, and relying parties.
- Properly invalidate server-side session objects after logout, absolute timeout, or idle timeout.

### 3.4 Cookie-based Session Management

- Set the 'Secure' attribute on cookie-based session tokens.
- Set the 'HttpOnly' attribute on cookie-based session tokens.
- Use the 'SameSite' attribute to restrict cookie sharing across sites.
- Implement additional protection for cookies where SameSite is not supported.
- Apply cookie prefixes (e.g., "__Host-" and "__Secure-") to protect cookies from default domain assumptions.

### 3.5 Defenses Against Session Management Exploits

- Require re-authentication or secondary verification for sensitive transactions or account modifications.

## 4. Access Control

### 4.1 General Access Control Design

- Enforce access control rules on a trusted service layer, even if client-side access control is present.
- Ensure user and data attributes and policy information used by access controls cannot be manipulated by end users without authorization.
- Apply the principle of least privilege for all accounts and services.
- Implement authorization checks for all accessible resources and APIs.

### 4.2 Operation Level Access Control

- Protect sensitive data and APIs against Insecure Direct Object Reference (IDOR) attacks targeting creation, reading, updating, and deletion of records.
- Enforce strong anti-CSRF mechanisms for authenticated functionality and anti-automation or anti-CSRF for unauthenticated functionality.

### 4.3 Other Access Control Considerations

- Protect administrative interfaces with appropriate multi-factor authentication.
- Disable directory browsing and prevent discovery or disclosure of file or directory metadata (Thumbs.db, .DS_Store, .git, .svn folders).

## 5. Input Validation & Output Encoding

### 5.1 Input Validation

- Implement defenses against HTTP parameter pollution attacks.
- Protect against mass parameter assignment attacks by marking fields private or implementing similar countermeasures.
- Apply input validation using positive validation (allowlisting), appropriate validation strategies, and syntax/semantic validation.
- Enforce UTF-8 character encoding and validate before accepting input.
- Validate client-side redirects and forwards, only allowing destinations from an allowlist or showing a warning.

### 5.2 Sanitization and Sandboxing

- Sanitize untrusted HTML input from WYSIWYG editors using HTML sanitizer libraries or framework features.
- Sanitize unstructured data to enforce safety measures, including allowed characters and length.
- Apply strict validations for more structured data formats (JSON, XML) and enforce schemas, encodings, and validations.
- Validate uploaded files by file type, size, content, and filename, handling files securely.
- Process uploaded files at a system level rather than at application level when possible.

### 5.3 Output Encoding and Injection Prevention

- Apply context-specific output encoding for different interpreters (HTML values, HTML attributes, JavaScript, URL parameters, HTTP headers, SMTP).
- Preserve the user's chosen character set and locale in output encoding.
- Use parameterized queries, ORMs, or prepared statements for database queries, avoiding dynamic queries with string concatenation.
- Escape special characters in OS commands using language-specific libraries or by using safer APIs.
- Prevent LDAP injection by using language-specific libraries for LDAP queries.
- Escape untrusted data in mail headers and apply strict validation.
- Prevent template injection by strictly separating untrusted code from template expressions and variables.
- Prevent XPath injection and XXE attacks with appropriate escaping and XML parsing configurations.
- Avoid unsafe HTML, CSS, and JavaScript practices from client-side frameworks.

### 5.4 Memory, String, and Unmanaged Code

- Use memory-safe string handling, safer memory copy functions, and pointer arithmetic to prevent stack, buffer, or heap overflows.

### 5.5 Deserialization Prevention

- Apply integrity checks or encryption to serialized objects to prevent hostile object creation or data tampering.
- Configure XML parsers with restrictive settings to prevent XXE attacks.
- Avoid native deserialization formats and prefer data formats that only permit primitive data types.
- Monitor deserialization and implement integrity checks, encryption, and logging if necessary.

## 6. Cryptography & Data Protection

### 6.1 Data Classification

- Store regulated private data (PII, sensitive personal information, GDPR-subject data) encrypted at rest, and offer users the choice to delete their information per regulatory requirements.
- Encrypt regulated health data (medical records, device details, de-anonymized research records) while at rest.
- Protect nationally restricted data in accordance with applicable regulations.

### 6.2 Algorithms

- Ensure all cryptographic modules fail securely with errors handled to prevent Padding Oracle attacks, and review SSL/TLS protocols and ciphers to use only strong configurations.

### 6.3 General Data Protection

- Protect sensitive data from being cached in server components (load balancers, application caches).
- Purge, invalidate, or protect cached or temporary copies of sensitive server-side data from unauthorized access.
- Remove sensitive data from backups, cached data, or client-side storage once it's no longer required for business purposes.

### 6.4 Client-side Data Protection

- Avoid storing sensitive data in browser storage (localStorage, sessionStorage, IndexedDB, cookies).

### 6.5 Sensitive Private Data

- Send sensitive data in the HTTP message body or headers, not in query string parameters.
- Provide users with methods to remove or export their data on demand.
- Disable autocomplete for fields containing sensitive data and prevent browsers from caching pages with sensitive data.
- Ensure sensitive data is not included in logs or debug output.
- Minimize sensitive data collection, processing, and retention to what's needed for business functions.

## 7. Logging & Error Handling

### 7.1 Log Content

- Avoid logging credentials or payment details, and store session tokens only in irreversible, hashed form.
- Avoid logging sensitive data as defined by privacy laws or security policies.
- Ensure logs contain important detail for debugging and forensic investigations without excessive data.
- Protect sensitive information in logs, particularly personal data, using controls like data masking and encryption.

### 7.2 Log Processing

- Log all authentication decisions with relevant metadata for security investigations, without storing sensitive tokens or passwords.

### 7.3 Log Protection

- Protect security logs from unauthorized access and modification.
- Synchronize time sources to the correct time and time zone, considering logging in UTC for global systems to aid forensic analysis.

### 7.4 Error Handling

- Show generic messages for unexpected or security-sensitive errors, potentially with unique IDs for support personnel.

## 8. Communications Security

### 8.1 Client Communication Security

- Use TLS for all client connectivity without fallback to insecure communications.
- Enable only strong cipher suites, with the strongest set as preferred.
- Use Transport Layer Security (TLS) certificate keys of sufficient strength (at least 2048 bits for RSA, 224 bits for ECC).

### 8.2 Server Communication Security

- Use trusted TLS certificates for server connections, with proper configurations for internal or self-signed certificates.
- Enable proper certification revocation mechanisms such as Online Certificate Status Protocol (OCSP) Stapling.

## 9. Malicious Code & File Management

### 9.1 Malicious Code Search

- Verify application source code and third-party libraries don't contain unauthorized data collection capabilities without user permission.
- Avoid requesting unnecessary permissions for privacy-related features or sensors (contacts, cameras, microphones, location).
- Ensure the application doesn't contain obfuscated code, malicious code, or code that wasn't explicitly approved.

### 9.2 Application Integrity

- Obtain and validate digital signatures for updates via secure channels if the application has auto-update features.
- Implement integrity protections like code signing or subresource integrity, avoiding code loading from untrusted sources.
- Protect the application against XSS, CSRF, and injection attacks that could compromise application security.

### 9.3 Business Logic Security

- Process business logic flows for the same user in sequential step order without skipping steps.
- Implement anti-automation controls to protect against excessive calls, mass data exfiltration, and denial of service attacks.

### 9.4 File Upload

- Reject large files that could cause storage issues or denial of service.
- Enforce file size quotas and maximum file counts per user to prevent storage abuse.

### 9.5 File Execution

- Avoid using user-submitted filename metadata directly in system operations; use a URL API to prevent path traversal.
- Validate or ignore user-submitted filename metadata to prevent local file disclosure, creation, updating, or removal (LFI).
- Store files outside the webroot with limited permissions, using a content handler for download or filename references.
- Use server-side validation to ensure uploaded files meet expectations for type, size, and content.

### 9.6 File Storage

- Scan files from untrusted sources with antivirus scanners to prevent upload of malicious content.

### 9.7 File Download

- Configure the web tier to serve only files with specific extensions to prevent information and source code leakage.
- Ensure direct requests to uploaded files never execute as HTML/JavaScript content.

## 10. Web Services & API Security

### 10.1 Generic Web Service Security

- Use the same encodings and parsers across all application components to avoid parsing attacks in SSRF and RFI attacks.
- Avoid exposing sensitive information in API URLs (API keys, session tokens).
- Ensure cross-domain requests follow a proper trust evaluation and include as few privileges as possible.
- Harden the API against automated attacks, brute force, denial of service, and injection-based attacks.

### 10.2 RESTful Web Service

- Limit RESTful HTTP methods to valid choices based on user roles (e.g., prevent normal users from using DELETE or PUT on protected resources).
- Protect cookie-based RESTful services from CSRF using patterns like double submit cookies, CSRF nonces, or Origin header checks.
- Ensure REST services explicitly check the Content-Type header (e.g., application/xml, application/json) to prevent attacks exploiting interpretation differences.

### 10.3 SOAP Web Service

- Validate XML documents using XSD schema validation before processing, ensuring proper formation and input validation.
- Sign message payloads using WS-Security to ensure reliable transport between client and service.

## 11. Configuration & Deployment

### 11.1 Dependency

- Keep all components up to date, preferably using dependency checkers during build or compile time.
- Remove unneeded features, documentation, sample applications, developer comments, and configurations.
- Ensure components are obtained from official sources via secure links and verified using digital signatures.

### 11.2 Unintended Security Disclosure

- Disable debug modes in production to eliminate debug features, developer consoles, and unintended security disclosures.
- Avoid exposing detailed version information of system components in HTTP headers or responses.

### 11.3 HTTP Security Headers

- Include a Content-Type header in every HTTP response, specifying safe character sets for text content.
- Add Content-Disposition headers for API responses to prevent content rendering in browsers.
- Implement Content Security Policy (CSP) headers to prevent XSS and injection attacks.
- Add X-Content-Type-Options: nosniff header to prevent MIME type sniffing.
- Include the X-Frame-Options header to prevent clickjacking.
- Add the Referrer-Policy header to control information in the Referer header.
- Implement the Permissions-Policy header to control browser features and APIs.

### 11.4 HTTP Request Header Validation

- Accept only the HTTP methods used by the application/API, including pre-flight OPTIONS, and log/alert on invalid requests.
- Properly configure Cross-Origin Resource Sharing (CORS) headers with a strict allowlist of trusted domains without supporting the "null" origin.