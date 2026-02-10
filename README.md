# IT Helpdesk Ticket System (CLI)

## Overview
This project is a **simple internal IT Helpdesk system** built to understand how real IT departments handle issues in a structured way.

The focus of this project is **not** on building a full product or UI, but on:
- structuring IT problems,
- defining priorities,
- managing ticket workflows,
- and improving usability step by step.

The system runs as a **command-line tool (CLI)** and stores tickets in a CSV file.

---

## Problem Statement
In many organizations, IT issues are reported in an unstructured way:
- emails,
- messages,
- phone calls,
- or informal communication.

This often leads to:
- unclear priorities,
- missing documentation,
- repeated issues,
- inefficiency for IT staff.

This project models a **structured alternative**: a simple helpdesk workflow.

---

## Core Design Concept
Before writing any code, the system was designed around three essential questions:

1. **Who is reporting the issue?**
2. **What kind of problem is it?**
3. **How urgent is it?**

All system logic is based on these inputs.

---

## Ticket Categories
The helpdesk supports four realistic IT issue categories:

- **Access** – login problems, permissions, account issues  
- **Network** – VPN, Wi-Fi, connectivity problems  
- **System failure** – hardware or operating system failures  
- **Phishing** – suspicious emails and security incidents  

These categories reflect common internal IT workloads, with a strong focus on security.

---

## Priority Logic
Ticket priority is calculated automatically based on **category and impact**.

### Priority rules:
- **Phishing** → always **HIGH** (security risk)
- **Network**
  - Blocked → **HIGH**
  - Not blocked → **MEDIUM**
- **Access**
  - Blocked → **MEDIUM**
  - Not blocked → **LOW**
- **System failure**
  - Blocked → **MEDIUM**
  - Not blocked → **LOW**

This reflects how IT teams prioritize issues based on **risk and business impact**.

---

## Project Evolution

### Version 1 – Ticket Creation
- User provides:
  - name or role
  - issue category
  - blocked status
  - short description
- System:
  - generates a unique ticket ID
  - calculates priority
  - stores the ticket in `tickets.csv`
- Initial status: **OPEN**

**Learning focus:**  
Translating real-world IT problems into structured data.

---

### Version 2 – Ticket Management
- Added:
  - listing all tickets
  - updating ticket status (`OPEN → IN_PROGRESS → CLOSED`)
- Introduced a basic ticket lifecycle.

**Learning focus:**  
Understanding workflow states and controlled updates.

---

### Version 3 – Ticket Filtering & Usability
- Introduced a ticket viewing submenu:
  - All tickets
  - OPEN tickets
  - IN_PROGRESS tickets
  - CLOSED tickets
  - HIGH priority tickets
  - MEDIUM priority tickets
- Focused on usability for IT staff instead of technical complexity.

**Learning focus:**  
Improving system design from the user’s perspective.

---

## Data Storage
- Tickets are stored in a CSV file (`tickets.csv`)
- This allows:
  - easy inspection,
  - export to Excel,
  - simple reporting.
- CSV was chosen to keep the focus on **logic and workflow**, not databases.

---

## AI-Assisted Development
AI tools were used to assist with:
- code generation,
- refactoring,
- and syntax correction.

All changes were:
- reviewed manually,
- validated by running the program,
- adjusted when business logic or usability issues were identified.

AI was used as a **support tool**, not as a decision-maker.

---

## What This Project Demonstrates
- System-oriented thinking
- IT workflow design
- Priority and risk handling
- Iterative improvement
- Responsible use of AI in development

---

## Future Improvements
- Role separation (employee vs IT staff)
- Authentication
- Database-backed storage
- Web-based interface using the same logic

---

## Purpose
This project was created as part of my preparation for an **IT Ausbildung**, especially in areas related to system integration and internal IT operations.
