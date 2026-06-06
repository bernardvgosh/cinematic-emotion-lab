# Security Policy
## Cinematic Emotion Lab

---

## Scope

This document describes the security policy for the Cinematic Emotion Lab
repository. Given that this is a research repository rather than a deployed
application, the scope of security concerns is specific and bounded.

---

## What Is In Scope

The following are considered in-scope security concerns for this repository:

**Dependency vulnerabilities**
Vulnerabilities in Python packages listed in `requirements.txt` that could
compromise a researcher's environment when running the public notebooks.

**Notebook code risks**
Code in public Jupyter notebooks that could cause unintended system-level
effects (file system access beyond the repository, network requests to
external services, subprocess execution) without clear documentation of
that behavior.

**Sensitive data exposure**
Any accidental commit of personal data, API keys, credentials, email addresses,
or other sensitive information that should not be in a public repository.

**Dependency confusion**
Package names in `requirements.txt` that could be susceptible to dependency
confusion attacks through malicious packages on public registries.

---

## What Is Out of Scope

The following are not in scope for this security policy:

- The research findings, annotation corpus, or trained model weights - these
  are withheld for research reasons, not security reasons.
- Audio files - these are not committed to the repository.
- The GitHub.com platform itself - report platform-level issues to GitHub.

---

## Reporting a Vulnerability

If you identify a security concern that falls within the scope above, please
report it privately rather than opening a public Issue.

**Contact:** contactbernardg@gmail.com
**Subject line:** `[Cinematic Emotion Lab] Security`

Please include:

1. A clear description of the concern
2. The file(s) and line number(s) involved, if applicable
3. Steps to reproduce or a proof of concept, if relevant
4. Your assessment of the potential impact

**Response timeline:**
All security reports will be acknowledged within five business days.
Resolution timeline depends on severity: critical issues affecting researcher
environments will be addressed within seven days; lower-severity issues
within thirty days.

---

## Dependency Policy

All Python dependencies are pinned to specific versions in `requirements.txt`.
The primary researcher reviews dependency updates before incorporating them
into the public requirements file. If you identify an outdated or vulnerable
dependency, a public Issue labeled `infrastructure` is acceptable for this
class of concern — no sensitive information is involved.

---

## No Authentication or User Data

This repository does not operate any service, does not collect user data,
and does not handle authentication. There are no API endpoints, no backend
systems, and no user accounts associated with this repository beyond standard
GitHub platform functionality.

---

*Cinematic Emotion Lab - Security Policy v1.0 - 2026*
