# Heaven’s Light Is Our Guide

## Rajshahi University of Engineering & Technology (RUET)
### Department of Computer Science & Engineering

# A Lab Project Report on
## “CryptInfoBD”

**Course Code:** CSE 2100  
**Course Title:** Software Development Project I  

### Author
**Student’s Name:** Md. Mehedi Hasan  
**Roll:** 2303036  
**Section:** A  

### Supervisor
**(To be filled)**  
**Designation:** (To be filled)  
**Dept. of CSE, RUET**  

**Date:** 2026-04-21

---

# Certification

This is to certify that the project titled **“CryptInfoBD”** submitted by **Md. Mehedi Hasan**, Roll Number: **2303036**, for the fulfillment of the requirements of the course **CSE 2100 (Software Development Project I)**, has been examined and approved by the undersigned.

The project has been carried out under my supervision, and it is recommended for submission and evaluation.

**Supervisor:**  
**Name:** ________________________________  
**Designation:** __________________________  
**Department:** CSE  
**Institution:** RUET  
**Date:** 2026-04-21  
**Signature:** ____________________________

---

# CONTENT

1. Abstract
2. CHAPTER 1 : Introduction
   - 1.1 Problem Statement
   - 1.2 Motivation
   - 1.3 Objectives
   - 1.4 Contribution Summary
   - 1.5 Report Structure
   - 1.6 System Context
3. CHAPTER 2 : Background & Literature Review
   - 2.1 Theoretical Foundation
   - 2.2 Related Work Review
   - 2.3 Comparative Analysis
   - 2.4 Gap Analysis
4. CHAPTER 3 : Requirements & Team Workflow
   - 3.1 Functional Requirements
   - 3.2 Non-functional Requirements
   - 3.3 System Constraints
   - 3.4 Technology Stack Justification
   - 3.5 Team Structure
   - 3.6 Collaboration Workflow
5. CHAPTER 4 : Project Management & Finance
   - 4.1 Work Breakdown Structure (WBS)
   - 4.2 Project Schedule
   - 4.3 Budget
   - 4.4 Risk Analysis
   - 4.5 Summary of Management Decisions
6. CHAPTER 5 : System Architecture & Implementation
   - 5.1 Methodological Structure
   - 5.2 High-Level Architecture
   - 5.3 Module-wise Implementation
   - 5.4 Database/Storage Design (if applicable)
   - 5.5 Testing & Execution Results
7. CHAPTER 6 : Conclusion & Future Direction
   - 6.1 Interpretation of Findings
   - 6.2 Strengths of the Project
   - 6.3 Limitations
   - 6.4 Recommendations for Future Development
8. REFERENCES
9. APPENDICES

---

# Abstract

**Problem Addressed:** Users and students frequently need a single lightweight desktop utility for number-system conversions, text-to-code conversions, base-encoding transformations, and RSA numeric operations. Existing solutions are often fragmented across multiple tools or websites, lack consistent validation, and provide limited educational transparency.

**Proposed Solution:** **CryptInfoBD** is a desktop crypto-conversion toolkit built using **Python** and **PyQt6**. It combines **22 conversion tools** in one UI, covering (i) number and text conversions, (ii) base-encoding conversions, and (iii) RSA numeric encrypt/decrypt operations. The system is designed with a clear separation between frontend UI and backend conversion logic.

**Tools & Technologies:** Python 3.10+, PyQt6 for UI, modular backend routes with centralized validators and custom exceptions.

**Key Results:** The application successfully provides a multi-page conversion interface using router-based navigation (QStackedWidget). Each conversion has its own backend route module and a matching frontend page, enabling maintainability, testability, and safe user input handling.

**Significance & Impact:** The project supports both practical conversion workflows and educational understanding by documenting the mathematics behind conversions and offering consistent error feedback rather than crashes.

---

# CHAPTER 1 : Introduction

## 1.1 Problem Statement

In educational, programming, and security-related tasks, users often require quick conversion between number bases (binary, octal, decimal, hexadecimal), text and ASCII/Unicode numeric values, and common encoding schemes (Base64, Base32, and a practical Base85-based substitute used as Base128 in this project). Additionally, basic RSA modular exponentiation is frequently needed for learning public-key cryptography.

Most available tools are either web-only, scattered across multiple sources, or lack a unified workflow and structured input validation. This leads to user confusion, inconsistent results, and a higher chance of mistakes.

## 1.2 Motivation

The motivation of **CryptInfoBD** is to provide an “all-in-one” desktop conversion suite that is fast, easy to use, and educational. The application is designed to:
- consolidate many conversion utilities in one interface,
- provide clear validation and friendly error messages,
- maintain a modular architecture so features can be extended.

## 1.3 Objectives

The objectives of this lab project are:
1. **Unified Desktop Tool:** Implement a single desktop application containing a broad set of conversion utilities.
2. **Modular Architecture:** Maintain strict separation between UI and conversion logic for maintainability.
3. **Reliable Validation:** Ensure inputs are validated consistently using centralized validators.
4. **Robust Error Handling:** Prevent application crashes by using custom exceptions and safe error display.
5. **Educational Transparency:** Provide clear conversion mathematics and examples to support learning.

## 1.4 Contribution Summary

Key contributions of this project include:
- a **PyQt6 router-based multi-page UI** with conversion pages registered by conversion keys,
- a **backend routes system** where each conversion is isolated in its own module,
- centralized validation and custom exception handling for safe conversions,
- built-in RSA numeric modular exponentiation tools for basic cryptography learning.

## 1.5 Report Structure

This report is organized as follows:
- Chapter 1 introduces the project goals and scope.
- Chapter 2 discusses background and related work.
- Chapter 3 presents requirements and workflow.
- Chapter 4 provides project management planning.
- Chapter 5 details architecture and implementation.
- Chapter 6 concludes with future improvement directions.

## 1.6 System Context

**System Context (Conceptual):**
- **User** interacts with the **CryptInfoBD Desktop App (PyQt6 UI)**.
- UI validates and forwards input to the **Backend Conversion Modules**.
- Backend returns either **Result** or **Validation Error**.
- UI displays the result and allows copying output.

*(Diagram placeholder: System Context Diagram of CryptInfoBD)*

---

# CHAPTER 2 : Background & Literature Review

## 2.1 Theoretical Foundation

CryptInfoBD is grounded in:
- **positional numeral systems** (base-2, base-8, base-10, base-16),
- **character encoding** (ASCII/Unicode mapping via integer code points),
- **base encodings** (Base64, Base32; Base85 used in the project as a practical substitute),
- **RSA modular arithmetic** using modular exponentiation.

## 2.2 Related Work Review

Common conversion tools exist in websites, IDE plugins, or small scripts. However, they often:
- solve only one conversion category,
- provide minimal validation,
- do not provide a consistent UI workflow,
- do not combine cryptographic numeric operations with everyday conversions.

## 2.3 Comparative Analysis

Compared to web tools or single-purpose scripts:
- CryptInfoBD provides **22 tools in one UI**.
- Uses **router-based navigation** and **component reuse**.
- Provides **centralized validation** and **custom exceptions**.

*(Diagram placeholder: Comparative Analysis Table/Chart)*

## 2.4 Gap Analysis

The main gap addressed is a lack of unified desktop tools that combine:
- number base conversions,
- text encoding/decoding,
- RSA numeric operations,
with consistent validation and user-friendly UI. CryptInfoBD bridges this by providing a modular, safe, and extendable design.

---

# CHAPTER 3 : Requirements & Team Workflow

## 3.1 Functional Requirements

1. **Login Gate:** Show login screen first; validate email format and non-empty password.
2. **Conversion Navigation:** Provide dropdown-based routing across three conversion groups:
   - Number/Text,
   - Base Encoding,
   - RSA.
3. **Conversion Execution:** For each conversion page:
   - accept input,
   - validate input,
   - call backend route,
   - show output or error.
4. **Copy/Logout Support:** Allow copying output and logging out from pages.

## 3.2 Non-functional Requirements

- **Usability:** Clean and predictable UI.
- **Maintainability:** One backend module per conversion + one UI page per conversion.
- **Reliability:** No crashes on invalid input.
- **Portability:** Python-based, runnable on Windows and other platforms supporting PyQt6.

## 3.3 System Constraints

- Requires **Python 3.10+**.
- Requires dependencies from `requirements.txt`.
- Designed and tested primarily on **Windows**.

## 3.4 Technology Stack Justification

- **Python:** Fast prototyping, readability, and strong standard library support.
- **PyQt6:** Modern desktop GUI toolkit with strong event-driven signal/slot model.
- **Modular routes:** Improves extensibility and testing.

## 3.5 Team Structure

This project is developed as an individual lab project.

## 3.6 Collaboration Workflow

A structured workflow is followed:
- modular development by conversion tool,
- testing with `test_backend.py`,
- documentation maintained in repository docs.

---

# CHAPTER 4 : Project Management & Finance

## 4.1 Work Breakdown Structure (WBS)

1. Requirements & Tool List Finalization
2. UI Skeleton (Login, Main Window, Router)
3. Backend Route Development (22 conversions)
4. Validation + Exceptions Layer
5. UI Pages for Each Conversion
6. Testing and Bug Fixing
7. Documentation and Report Preparation

## 4.2 Project Schedule

A typical schedule (example):
- Week 1–2: UI skeleton + core routes
- Week 3–4: remaining routes + pages
- Week 5: validation, RSA, encoding, testing
- Week 6: documentation and final polishing

## 4.3 Budget

Budget is effectively **zero** (open-source tools; development on personal device).

## 4.4 Risk Analysis

- **Invalid input causing crashes:** mitigated via centralized validators and custom exceptions.
- **Edge cases in base encodings:** mitigated via standard library base64 codec utilities.
- **Platform differences:** PyQt6 behavior may vary slightly; tested primarily on Windows.

## 4.5 Summary of Management Decisions

- Adopted strict backend/frontend separation.
- Used router-based navigation to avoid a complex single-page UI.
- Used one-module-per-conversion for clean scaling.

---

# CHAPTER 5 : System Architecture & Implementation

## 5.1 Methodological Structure

CryptInfoBD uses a layered, modular architecture:
- **frontend/**: UI, routing, components, pages
- **backend/**: conversion logic, validators, exceptions
- **run.py**: launcher and bootstrap

The UI is event-driven using PyQt6 signal/slot. Each conversion request flows from page -> backend route -> output/error.

## 5.2 High-Level Architecture

**Client/UI Layer:** PyQt6 pages and reusable components.

**Routing Layer:** `frontend/router.py` (QStackedWidget) registers pages by conversion keys.

**Business Logic Layer:** `backend/routes/*` implement conversion algorithms.

**Validation Layer:** `backend/utils/validators.py` validates inputs and provides reusable checks.

**Error Handling Layer:** `backend/utils/exceptions.py` defines domain exceptions to avoid crashes.

*(Diagram placeholder: High-Level Architecture Diagram)*

## 5.3 Module-wise Implementation

### Backend
- `backend/main.py`: unified converter interface
- `backend/utils/validators.py`: validation helpers
- `backend/utils/exceptions.py`: domain exceptions
- `backend/routes/*.py`: one conversion per file (22 tools)

### Frontend
- `frontend/app.py`: main window; login-to-main switching
- `frontend/router.py`: key-driven navigation
- `frontend/components/*`: reusable widgets (dropdowns, input/output, error label)
- `frontend/pages/*`: one page per conversion

## 5.4 Database/Storage Design (if applicable)

This project is primarily a conversion toolkit and does not require a database for core operation.

## 5.5 Testing & Execution Results

- Backend smoke tests can be executed using:
  ```bash
  python test_backend.py
  ```
- Manual UI testing verifies:
  - login flow,
  - navigation via dropdowns,
  - conversion correctness,
  - no crash on invalid input.

*(Screenshot placeholders: Login screen, Main screen, sample conversion page, RSA page, error state)*

---

# CHAPTER 6 : Conclusion & Future Direction

## 6.1 Interpretation of Findings

CryptInfoBD successfully demonstrates that a modular PyQt6 desktop application can unify a broad set of conversion utilities while remaining stable, extendable, and educational.

## 6.2 Strengths of the Project

- Unified toolkit with 22 conversion tools.
- Modular architecture and easy extensibility.
- Centralized validation and robust exception handling.
- Educational content (mathematics + examples).

## 6.3 Limitations

- Base128 naming: internally relies on Base85 codec for practicality.
- UI screenshots/diagrams require manual capture for final submission.
- Login is a UI gate; not a full authentication backend.

## 6.4 Recommendations for Future Development

- Add persistent user settings (theme, last used tool) using local storage.
- Add more cryptography tools (hashing, AES demo, key generation).
- Improve automated testing coverage for all 22 conversions.
- Provide an installer/executable (PyInstaller) for easier distribution.

---

# REFERENCES

1. Python Documentation: https://docs.python.org/3/
2. PyQt6 Documentation: https://www.riverbankcomputing.com/static/Docs/PyQt6/
3. Python `base64` module: https://docs.python.org/3/library/base64.html
4. RSA (Intro): https://en.wikipedia.org/wiki/RSA_(cryptosystem)

---

# APPENDICES

## Appendix A: Project Structure

See repository structure in `README.md`.

## Appendix B: How to Run

- `pip install -r requirements.txt`
- `python run.py`
- Or Windows: `start.bat`

## Appendix C: Sample Test Command

- `python test_backend.py`