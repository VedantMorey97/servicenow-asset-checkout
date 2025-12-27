  ### Change Risk Assessment & Approval Automation

## 📌 Overview
This project implements an **automated, risk-based Change Management framework** in ServiceNow using the ITSM Change module.  
The solution dynamically calculates change risk, applies conditional approvals (including CAB), enforces risk-based SLAs, and validates functionality using Automated Test Framework (ATF).

- Automated **risk scoring** based on environment, outage duration, and CI impact
- Dynamic **approval routing** using Flow Studio
- Risk-based **SLA enforcement** with pause, stop, and cancel logic
- **Automated Test Framework (ATF)** coverage for regression testing

The implementation follows **ITIL best practices**.

---

## 📌 Business Problem
Manual risk selection and static approval flows often lead to:
- Incorrect risk classification
- Skipped CAB approvals
- Delayed responses and SLA breaches
- Production incidents due to insufficient governance

## 📌 Modules & Features Used
- ITSM – Change Management
- Flow Studio (Record-triggered flows)
- Business Rules (server-side logic)
- Client Scripts (UX validation)
- UI Policies (dynamic UI behavior)
- Service Level Management (SLA Definitions)
- Automated Test Framework (ATF)
- Reporting & Dashboards

---

Dummy Change Requests are created using **Background Scripts** to validate:
- Risk scoring
- Approval routing
- SLA attachment and escalation

---

## 📌 Limitation

1. Static Risk Scoring Logic

The current risk score calculation uses predefined weightage for environment, outage duration, and CI type.

2. SLA Granularity

Separate SLA definitions are created for Low, Moderate, and High risk changes.
While this keeps logic simple and readable, it can increase maintenance overhead as the number of risk categories grows.

3. Manual SLA Escalation Notifications

SLA escalation notifications are time-based and do not consider business context such as upcoming maintenance windows or holidays.

---
