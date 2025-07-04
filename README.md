# CodeAlpha_SecureCodingReview

Secure Coding Review with Bandit

This repository contains the result of the Secure Coding Review performed on a Flask micro-web app (todo-flask) using Bandit, the Python static analyzer focused on security vulnerabilities.

code credits: https://github.com/sreecodeslayer

Summary

1. Purpose
2. Setup-environment
3. Running Bandit
4. Report analysis
5. Recommendations & Best Practices

1. Purpose

To evaluate the security level of the Python code of an open-source Flask app ("todo-flask" by sreecodeslayer), identifying:

- Hard-coded secrets
- SQL injection
- XSS / CSRF
- Insecure configurations
- Vulnerable dependencies

All the results were collected in a report generated by Bandit.

# Prerequisites

- Kali Linux (or any Debian-based distro)
- Python 3.8+
- Git
- Internet access to download packages

2. Environment Setup

```bash
# 1. Clone the test app repo
git clone https://github.com/sreecodeslayer/todo-flask.git
cd todo-flask

# 2. Create and activate the virtualenv
python3 -m venv venv
source venv/bin/activate # macOS/Linux
# or .\venv\Scripts\Activate.ps1 # Windows PowerShell

# 3. Install dependencies and Bandit
pip install --upgrade pip
pip install -r requirements.txt
pip install bandit
Running Bandit

Run Bandit in recursive mode, showing all severities and saving the output to JSON:
bandit -r . -lll -f json -o bandit-report.json

Main options:

-r . — recursive scan

-lll — all severities (Low/Medium/High)

-f json — JSON format

-o file — output to file


4. Report analysis

Open the generated JSON or TXT:
jq '.' bandit-report.json # if you have jq
cat bandit-report.txt

Find critical issues (severity ≥ HIGH) and those that are repeated multiple times.

For each vulnerability note:

ID (e.g. B303)

File & Line

Description

Recommended Remediation


Prepared by Yasmine – Secure Coding Review & Analysis with Bandit
