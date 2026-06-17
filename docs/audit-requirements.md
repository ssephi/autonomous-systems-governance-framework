# Audit Requirements

> **Document:** Audit Requirements  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines the audit and accountability requirements for autonomous systems operating within an organisation.

The objective is to ensure that all actions performed by autonomous systems are attributable, traceable, reviewable, and explainable.

These requirements are designed to support regulatory, compliance, governance, security, and operational obligations.

This document applies to:

- AI agents
- Automation platforms
- Workflow engines
- Scripts
- Bots
- Orchestration systems
- Future autonomous systems

---

# Core Principle

No action should occur without evidence.

An organisation must be able to answer:

- Who requested the action?
- What information was provided?
- What decision was made?
- What action was executed?
- When did it occur?
- What was affected?
- Was the action approved?
- By whom?

If these questions cannot be answered, the action should be considered unauditable.

---

# Mandatory Audit Events

The following events must be recorded.

---

## Authentication

Record:

- Identity used
- Authentication method
- Success or failure
- Timestamp
- Source system

Examples:

- User login
- Service authentication
- API authentication
- Token issuance

---

## Authorisation

Record:

- Requested action
- Permission evaluated
- Decision
- Timestamp

Examples:

- Access granted
- Access denied
- Privilege escalation request

---

## Data Access

Record:

- Data source
- Classification
- Identity
- Action performed
- Timestamp

Examples:

- Database query
- Document retrieval
- Secret retrieval
- Customer record access

---

## Recommendations

Record:

- Recommendation generated
- Supporting evidence
- Confidence level (if available)
- Timestamp

Examples:

- Security recommendations
- Cost recommendations
- Incident recommendations

---

## Approval Requests

Record:

- Requested action
- Risk category
- Requesting system
- Timestamp

Examples:

- Deployment approval
- Access approval
- Infrastructure approval

---

## Approval Decisions

Record:

- Approver identity
- Decision
- Timestamp
- Supporting notes

Examples:

- Approved
- Rejected
- Deferred

---

## System Actions

Record:

- Action executed
- Target system
- Identity used
- Timestamp
- Outcome

Examples:

- Deployment
- Resource creation
- Resource modification
- Resource deletion

---

## Configuration Changes

Record:

- Previous configuration
- New configuration
- Author
- Timestamp

Examples:

- Policy changes
- Infrastructure changes
- Access changes

---

## Permission Changes

Record:

- Previous permissions
- New permissions
- Approver
- Timestamp

Examples:

- IAM modifications
- Group membership changes
- Role assignments

---

# Required Audit Fields

All audit records should contain:

| Field | Required |
|---------|----------|
| Timestamp | Yes |
| Unique Event ID | Yes |
| System Name | Yes |
| Action Type | Yes |
| Actor Identity | Yes |
| Outcome | Yes |

Where applicable:

| Field | Required |
|---------|----------|
| User Identity | Yes |
| Approval Reference | Yes |
| Target Resource | Yes |
| Risk Category | Yes |
| Data Classification | Yes |

---

# Human Attribution

Autonomous systems must not obscure accountability.

Where an autonomous system acts on behalf of a user:

Both identities should be recorded.

Example:

User:

John Smith

Executing System:

Production Operations Agent

Audit Record:

John Smith -> Production Operations Agent -> Action

Not:

Production Operations Agent -> Action

---

# Approval Traceability

Approval decisions must be traceable to executed actions.

An auditor should be able to follow:

Request

↓

Approval

↓

Execution

↓

Outcome

using recorded identifiers.

---

# Immutable Audit Records

Audit records should be protected against modification.

Preferred controls include:

- Write-once storage
- Centralised logging
- Retention controls
- Access restrictions

Audit logs should not be editable by the systems generating them.

---

# Separation of Duties

Systems responsible for performing actions should not be solely responsible for recording those actions.

Audit collection should occur independently where possible.

Examples:

Preferred:

Application -> Central Logging Platform

Avoid:

Application -> Local Log File Only

---

# Evidence Retention

Audit records should be retained in accordance with:

- Legal requirements
- Regulatory requirements
- Contractual requirements
- Organisational policy

Retention periods should be formally documented.

---

# Explainability

Where autonomous systems make decisions, sufficient evidence should exist to explain:

- Inputs considered
- Rules evaluated
- Constraints applied
- Outcome selected

The objective is not to record every internal model operation.

The objective is to allow reasonable reconstruction of the decision-making process.

---

# Security of Audit Data

Audit data should be treated as sensitive information.

Audit records may contain:

- User identities
- Infrastructure details
- Security information
- Operational procedures

Access should be restricted accordingly.

---

# Audit Review

Audit records should be reviewed periodically.

Reviews should verify:

- Completeness
- Accuracy
- Integrity
- Compliance with policy

An audit process that is never reviewed provides limited value.

---

# Minimum Audit Test

An organisation should be able to answer the following questions for any significant action:

1. Who requested it?
2. Who approved it?
3. Which system executed it?
4. What changed?
5. When did it occur?
6. Why did it occur?
7. Can the evidence be independently verified?

If any answer cannot be produced, audit controls should be considered insufficient.

---

# Auditability Overrides Convenience

The ability to perform an action is not sufficient justification to perform it.

Actions that cannot be adequately audited should not be automated.
