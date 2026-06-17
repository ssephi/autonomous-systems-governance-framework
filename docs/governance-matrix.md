# Governance Matrix

> **Document:** Governance Matrix  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-17  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---

## Purpose

This document provides the authoritative mapping between governance classifications used throughout the framework.

The objective is to ensure governance controls operate as a unified system rather than independent policy domains.

This document defines the relationship between:

- Risk Classification
- Access Level
- Approval Category
- Audit Requirements
- Review Requirements
- Governance Authority

Where conflicts exist, this document takes precedence.

---

# Core Principles

Governance controls should be consistent.

Risk, access, approval, audit, and review requirements should align with one another.

Higher risk should result in stronger controls.

Lower risk should not result in unnecessary bureaucracy.

---

# Governance Matrix

| Risk Classification | Maximum Access Level | Minimum Approval Category | Audit Requirement | Review Frequency |
|---------------------|----------------------|---------------------------|-------------------|------------------|
| Low | Level 1 | Category 0 | Basic | Annually |
| Medium | Level 2 | Category 1 | Standard | Annually |
| High | Level 3 | Category 2 | Enhanced | Every 6 Months |
| Critical | Level 4 | Category 3 | Comprehensive | Quarterly |

Level 5 access remains exceptional and should require explicit executive approval regardless of risk classification.

---

# Risk Classification Guidance

## Low

Characteristics:

- Limited operational impact
- Public or low-sensitivity information
- No production modification capability

Examples:

- Documentation assistants
- Internal knowledge search
- Read-only reporting

---

## Medium

Characteristics:

- Internal business impact
- Limited operational influence
- Non-sensitive internal data

Examples:

- Ticket triage
- Monitoring analysis
- Workflow orchestration

---

## High

Characteristics:

- Production influence
- Access to restricted information
- Potential operational disruption

Examples:

- Infrastructure remediation
- Deployment automation
- Customer-impacting workflows

---

## Critical

Characteristics:

- Significant operational impact
- Highly sensitive information
- Financial, legal, regulatory, or security implications

Examples:

- IAM administration
- Security control management
- Financial approval workflows

---

# Data Classification Adjustment

Data classification may increase governance requirements.

The highest applicable control should be used.

| Data Classification | Minimum Risk Classification |
|---------------------|-----------------------------|
| Public | Low |
| Internal | Medium |
| Restricted | High |
| Highly Sensitive | Critical |

Organisations may apply stronger controls where required.

---

# Access Escalation Rules

Access levels should not exceed the maximum defined by risk classification without documented justification.

Example:

Low Risk

↓

Level 4 Administrative Access

↓

Not Permitted Without Exception

Exceptions should follow approval-model.md.

---

# Approval Requirements

Approval categories should align with risk.

| Approval Category | Typical Use |
|-------------------|-------------|
| Category 0 | Read-only and advisory systems |
| Category 1 | Limited operational actions |
| Category 2 | Production-impacting actions |
| Category 3 | High-risk or critical actions |

Approval requirements should follow approval-model.md.

---

# Audit Requirements

## Basic

Minimum logging requirements.

Suitable for:

- Read-only systems
- Advisory systems

---

## Standard

Enhanced attribution and activity records.

Suitable for:

- Operational systems
- Internal workflows

---

## Enhanced

Comprehensive audit records and approval traceability.

Suitable for:

- Production-impacting systems
- High-risk workflows

---

## Comprehensive

Full accountability chain and governance evidence.

Suitable for:

- Critical systems
- Regulatory environments
- High-sensitivity operations

Audit requirements should follow audit-requirements.md.

---

# Review Requirements

Reviews should assess:

- Continued business need
- Risk classification
- Access requirements
- Approval requirements
- Operational effectiveness

Minimum review frequencies are defined by the governance matrix.

Additional reviews should occur:

- Following significant change
- Following significant incident
- Following material scope expansion

---

# Governance Authorities

## Business Owner

May approve:

- Low Risk
- Medium Risk

Responsible for:

- Business justification
- Operational necessity

---

## Risk Owner

Responsible for:

- Risk ownership
- Risk review
- Risk treatment oversight
- Risk acceptance recommendations

---

## Technical Owner

Provides technical review for:

- Medium Risk
- High Risk
- Critical Risk

Responsible for:

- Technical feasibility
- Operational impact

---

## Security Function

Required for:

- High Risk
- Critical Risk

Responsible for:

- Risk oversight
- Control validation
- Security review

---

## Executive Authority

Required for:

- Critical Risk acceptance
- Level 5 access approval
- Significant policy exceptions

Executive accountability should remain explicit and documented.

The organisation should explicitly define Executive Authority.

---

# Risk Classification Authority

Risk classification should be performed by an appropriately qualified individual or governance function.

This may include:

- Risk Owners
- Security Functions
- Risk Management Functions
- Equivalent governance authorities

Risk classification does not constitute risk acceptance.

Risk acceptance authority should follow the requirements defined below.

---

# Risk Acceptance Authority

Risk acceptance should align with risk classification.

| Risk Classification | Minimum Acceptance Authority |
|---------------------|------------------------------|
| Low | Business Owner |
| Medium | Business Owner |
| High | Security Function + Business Owner |
| Critical | Executive Authority |

Where multiple authorities are required, Security Function review should occur before risk acceptance.

Security Function review does not constitute risk acceptance.

Executive Authority retains final responsibility for Critical risk acceptance.

Disagreements between Security Function and other governance authorities should be escalated to Executive Authority for resolution.

Risk ownership may not be delegated to autonomous systems.

Risk acceptance decisions should consider recommendations provided by the Risk Owner where one has been assigned.

---

# Exception Authority

Exceptions should be time-limited and documented.

| Exception Type | Minimum Authority |
|----------------|-------------------|
| Low | Business Owner |
| Medium | Business Owner |
| High | Security Function |
| Critical | Executive Authority |

Permanent exceptions should be avoided.

---

# Emergency Authority

Emergency actions may bypass normal approval processes only when:

- Immediate action is required
- Material harm is likely
- Delay increases risk

Emergency approvals should be reviewed retrospectively.

Authority levels:

| Risk Classification | Emergency Authority |
|---------------------|---------------------|
| Low | Business Owner |
| Medium | Business Owner |
| High | Security Function |
| Critical | Executive Authority |

Emergency authority should not become routine authority.

---

# Conflict Resolution

Where multiple classifications apply:

The highest governance requirement should prevail.

Examples:

Medium Risk

Highly Sensitive Data

=

Critical Governance Requirements

or

Low Risk

Level 4 Access

=

High Governance Requirements

Governance controls should follow the most restrictive applicable classification.

---

# Related Documents

- risk-model.md
- access-model.md
- approval-model.md
- audit-requirements.md
- data-classification.md
- governance-model.md

---

# Final Principle

Governance controls should reinforce one another.

Risk should determine access.

Access should determine approval.

Approval should determine oversight.

The governance matrix exists to ensure the framework operates as a single system rather than a collection of independent controls.
