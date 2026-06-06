# Approval Model

> **Document:** Approval Model  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines when autonomous systems require approval before performing actions.

The objective is to ensure that risk acceptance remains a human responsibility.

This document applies to:

- AI agents
- Automation platforms
- Workflow engines
- Bots
- Scripts
- Orchestration systems
- Future autonomous systems

---

# Core Principle

Approval is a mechanism for accepting risk.

Approval is not a mechanism for increasing trust.

A trusted autonomous system may still require approval.

An untrusted autonomous system should not receive approval simply because approval exists.

---

# Approval Responsibilities

Autonomous systems may:

- Observe
- Analyse
- Recommend
- Plan

Humans remain responsible for:

- Risk acceptance
- Approval decisions
- Exception authorisation

Approval authority must remain attributable to an individual or defined governance body.

---

# Approval Categories

Actions should be assigned to one of four categories.

---

## Category 0 - No Approval Required

Characteristics:

- Read-only
- No system modification
- No customer impact
- No security impact

Examples:

- Monitoring
- Reporting
- Analysis
- Documentation generation

### Approval

Not Required

### Audit

Recommended

---

## Category 1 - Pre-Approved Actions

Characteristics:

- Low risk
- Well understood
- Repeatable
- Reversible

Examples:

- Certificate renewal
- Scaling within approved limits
- Service restarts
- Standard maintenance activities

### Approval

Approved through documented policy

### Audit

Required

---

## Category 2 - Single Approval Required

Characteristics:

- Moderate risk
- Limited impact
- Controlled execution

Examples:

- Production deployment
- Infrastructure modification
- DNS changes
- Configuration updates

### Approval

One authorised approver

### Audit

Required

---

## Category 3 - Multiple Approvals Required

Characteristics:

- High risk
- Significant business impact
- Security implications
- Compliance implications

Examples:

- IAM modifications
- Production data modification
- Security control changes
- Privileged access changes

### Approval

Minimum two approvers

### Audit

Mandatory

---

# Approval Workflow

The preferred workflow is:

Observe

↓

Analyse

↓

Plan

↓

Risk Assessment

↓

Approval

↓

Execute

↓

Verify

↓

Audit

Approval should occur before execution.

---

# Approval Criteria

Approvers should evaluate:

- Business justification
- Risk assessment
- Impact assessment
- Recoverability
- Existing controls

Approval decisions should not be based solely on:

- Urgency
- Seniority
- Convenience

---

# Emergency Approvals

Emergency approval processes may exist for:

- Security incidents
- Service outages
- Disaster recovery events

Emergency approvals should:

- Be documented
- Be auditable
- Be reviewed retrospectively

Emergency status should not eliminate accountability.

---

# Approval Expiry

Approvals should be time-bound.

Approved:

"Deploy version 2.4.1 to production."

Not approved:

"Deploy any future version."

Approved:

"Increase capacity during this event."

Not approved:

"Scale without limit."

Approval should be specific to a defined action or class of actions.

---

# Delegated Approval

Organisations may delegate approval authority.

Delegation should be:

- Documented
- Time-bound where appropriate
- Reviewed periodically

Delegated authority does not transfer accountability.

---

# Approval Independence

The requester and approver should be independent wherever practical.

Avoid:

Agent

↓

Agent Approval

↓

Execution

Preferred:

Agent

↓

Human Approval

↓

Execution

Significant actions should maintain separation of duties.

---

# Approval Records

Approval decisions should record:

- Approver identity
- Timestamp
- Action approved
- Scope of approval
- Supporting information

Approval records should comply with audit-requirements.md.

---

# Approval Revocation

Approvals may be revoked before execution.

Autonomous systems must verify approval remains valid before acting.

Execution should not proceed using expired, revoked, or superseded approvals.

---

# Approval Is Not A Security Control

Approval should complement controls.

It should not replace:

- Access controls
- Guardrails
- Monitoring
- Audit logging
- Segregation of duties

An action should remain impossible if technical controls prohibit it, regardless of approval.

---

# Risk Drives Approval

Approval requirements should be proportional to risk.

Low Risk

→ No approval

Medium Risk

→ Single approval

High Risk

→ Multiple approvals

Critical Risk

→ Enhanced governance

The objective is proportionality rather than bureaucracy.

---

# Final Principle

Approval is the formal acceptance of risk by an authorised party.

Autonomous systems may identify, analyse, and recommend actions.

The decision to accept risk remains a human responsibility.
