# Lab 5: Static Code Analysis — Gym Membership System

## Overview
This project applies static code analysis to a Python-based gym membership system using **Pylint**, **Bandit**, and **Flake8**. The aim is to improve code quality, remove security risks, and enforce consistent Python style.

## Features
- Register and manage gym members.
- Check membership status and calculate renewal fees.
- Validate discount inputs.
- Generate member identifiers using SHA-256.
- Generate secure locker PINs using Python's `secrets` module.
- Export the gym roster and summarize active memberships.

## Issues Fixed
The original program contained security, maintainability, and formatting issues. Key fixes include:
- Replaced unsafe `eval()` usage with safer input handling.
- Replaced weak MD5 hashing with SHA-256.
- Removed unsafe shell-command execution.
- Used `secrets` for security-sensitive PIN generation.
- Removed mutable default arguments.
- Improved naming, exception handling, and file handling.
- Corrected Flake8 formatting violations.

See [`issues.md`](issues.md) for the issue-by-issue documentation.

## Static Analysis Results

| Tool | Before | After |
|---|---:|---:|
| Pylint | 4.81/10 | 10.00/10 |
| Bandit | 6 findings | 0 findings |
| Flake8 | 9 violations | 0 violations |

The before-and-after report files are included in this repository.

## Repository Files
- `gym_membership_system.py` — corrected application.
- `issues.md` — documented issues, severity, and fixes.
- `reflection.md` — reflection questions and answers.
- `pylint_report_before.txt` / `pylint_report_after.txt` — Pylint results.
- `bandit_report_before.txt` / `bandit_report_after.txt` — Bandit results.
- `flake8_report_before.txt` / `flake8_report_after.txt` — Flake8 results.

## Run the Application
Run from the project directory:

```bash
python gym_membership_system.py
```

## Run the Analysis Tools
```bash
pylint gym_membership_system.py
bandit -r gym_membership_system.py
flake8 gym_membership_system.py
```

## Git History
The repository includes separate commits for the Pylint, Bandit, and Flake8 fixes, plus a documentation/reflection update.
