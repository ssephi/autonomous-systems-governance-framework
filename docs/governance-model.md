# Governance Model

> **Document:** Governance Model  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines the governance structure for autonomous systems operating within an organisation.

The objective is to ensure autonomous systems are:

- Governed
- Accountable
- Auditable
- Reviewable
- Subject to risk management

This document provides the overarching governance framework supporting all other documents within this repository.

---

# Core Principles

The repository README defines the seven foundational principles of this framework.

Those principles apply to all autonomous systems and take precedence throughout the repository.

The governance model exists to implement and enforce those principles.

The seven foundational principles are:

1. Least Privilege
2. Human Accountability
3. Separation of Duties
4. Default Read-Only
5. Auditability
6. Fail Safe
7. Capability Is Not Permission

---

# Governance Implications

The following governance principles are derived from the seven foundational principles.

They are intended to guide interpretation and implementation of the framework.

---

## Governance Principle 1

### Capability Is Not Permission

The existence of a technical capability does not imply authorisation to use that capability.

Governance determines what may be done.

Technology determines what can be done.

These should not be confused.

---

## Governance Principle 2

### Accountability Cannot Be Delegated

Autonomous systems may perform actions.

They may not own responsibility for those actions.

Responsibility remains with the organisation and its designated owners.

This principle derives from Human Accountability.

---

## Governance Principle 3

### Risk Drives Governance

Governance requirements should be proportional to risk.

Higher-risk activities require:

- Greater oversight
- Stronger controls
- Additional approvals

Lower-risk activities should not be burdened by unnecessary bureaucracy.

This principle supports Least Privilege, Separation of Duties, and Auditability.

---

## Governance Principle 4

### Controls Should Be Technical Wherever Possible

Policies are important.

Technical enforcement is stronger.

A secure design should not depend solely on compliance with written instructions.

This principle supports Fail Safe, Auditability, and Capability Is Not Permission.

---

# Governance Objectives

The governance framework exists to ensure:

- Risks are understood
- Access is controlled
- Decisions are attributable
- Actions are auditable
- Changes are managed
- Incidents are handled appropriately
- Autonomous systems remain under organisational control

---

# Review Cadence

Unless otherwise specified, governance controls should be reviewed:

- At least annually
- Following significant change
- Following significant incident
- Following material scope expansion

Individual documents may define additional review requirements.

---

# Governance Hierarchy

The framework consists of the following layers.

---

## Layer 1 - Principles

Defines foundational concepts.

Examples:

- Capability is not permission
- Accountability cannot be delegated

These principles should guide interpretation of all other documents.

---

## Layer 2 - Governance Controls

Defines organisational requirements.

Examples:

- access-model.md
- approval-model.md
- risk-model.md
- data-classification.md
- agent-lifecycle.md
- multi-agent-governance.md

These documents define what is permitted, who is accountable, and how autonomous systems are governed throughout their operational life.

---

## Layer 3 - Operational Controls

Defines operational processes.

Examples:

- execution-model.md
- change-management.md
- incident-response.md
- secrets-management.md

These documents define how activities occur.

---

## Layer 4 - Security Controls

Defines security requirements.

Examples:

- guardrails.md
- prompt-security.md
- vendor-management.md

These documents define protective controls.

---

## Layer 5 - Assurance Controls

Defines accountability and evidence.

Examples:

- audit-requirements.md
- testing-and-validation.md

These documents define how compliance, accountability, and governance effectiveness are demonstrated.

---

# Governance Roles

Every organisation should identify the following responsibilities.

---

## Business Owner

Responsible for:

- Business justification
- Value realisation
- Risk acceptance

Questions answered:

Why does this system exist?

---

## Technical Owner

Responsible for:

- Configuration
- Operation
- Maintenance

Questions answered:

How does this system work?

---

## Risk Owner

Responsible for:

- Risk assessment
- Risk treatment
- Risk acceptance recommendations

Questions answered:

What could go wrong?

---

## Security Function

Responsible for:

- Independent review
- Control validation
- Security oversight

Questions answered:

Are controls adequate?

---

# Risk Acceptance

Risk acceptance should be performed by authorised individuals.

Autonomous systems must not:

- Accept risk
- Override risk decisions
- Create exceptions to governance requirements

Risk acceptance remains a human responsibility.

---

# Exceptions Management

Exceptions may be granted where justified.

Examples:

- Temporary elevated permissions
- Pilot programmes
- Emergency operations
- Exceptional business requirements

Exceptions should:

- Be documented
- Be approved
- Be time-bound
- Be reviewed

Permanent exceptions should be avoided.

---

# Governance Reviews

The framework should be reviewed periodically.

Review triggers may include:

- Significant incidents
- Regulatory changes
- Technology changes
- New threat models
- Major architectural changes

Governance should evolve as risk evolves.

---

# Policy Conflicts

Where documents appear to conflict:

Apply the most restrictive interpretation until clarification is obtained.

Safety should take precedence over convenience.

---

# Authority Hierarchy

Where uncertainty exists:

Guardrails

↓

Approval Requirements

↓

Access Controls

↓

Operational Procedures

↓

User Requests

Higher levels take precedence over lower levels.

---

# Compliance Alignment

This framework is intended to support alignment with:

- ISO 31000 Risk Management
- ISO 27001 Information Security
- SOC 2
- NIST Cybersecurity Framework
- CIS Controls
- ITIL Change Enablement

The framework should be adapted to organisational requirements.

Compliance should be considered an outcome of effective governance rather than the primary objective.

---

# Framework Success Measures

A governed autonomous system should be:

- Known
- Owned
- Documented
- Auditable
- Reviewable
- Controllable
- Retirable

An autonomous system that cannot be controlled should not be trusted.

---

# Governance Failure Indicators

Additional review should occur when:

- Ownership is unclear
- Permissions continuously increase
- Approvals are routinely bypassed
- Audit records are incomplete
- Incidents repeat without corrective action
- Exceptions become permanent

These indicators suggest governance weaknesses.

---

# Final Principle

The purpose of governance is not to prevent autonomy.

The purpose of governance is to enable autonomy safely.

Autonomous systems should remain valuable, controllable, and accountable throughout their operational life.

The organisation should always remain in control.
