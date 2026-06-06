# Change Management

> **Document:** Change Management  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how autonomous systems should propose, approve, execute, and review changes affecting organisational systems, services, infrastructure, applications, and data.

The objective is to ensure changes remain controlled, auditable, and proportionate to risk.

This document is aligned with established change management principles including ITIL Change Enablement and common governance frameworks.

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

Autonomous systems do not justify bypassing change management processes.

A production change remains a production change regardless of whether it is proposed by:

- A human
- An automation platform
- An AI agent

Governance requirements should be determined by risk, not by the identity of the requester.

---

# Change Lifecycle

All changes should follow the following lifecycle.

Request

↓

Assess

↓

Approve

↓

Implement

↓

Verify

↓

Review

↓

Close

---

# Change Categories

Changes should be categorised according to risk.

---

## Standard Change

Pre-approved, low-risk, repeatable change.

Characteristics:

- Well understood
- Documented
- Tested
- Low impact
- Low risk

Examples:

- Routine certificate renewal
- Scaling within approved limits
- Restarting approved services
- Scheduled maintenance tasks

### Autonomous Execution

Permitted

Provided documented guardrails exist.

---

## Normal Change

Change requiring assessment and approval.

Characteristics:

- Moderate risk
- Potential service impact
- Requires review

Examples:

- Application deployment
- Infrastructure modification
- Firewall rule changes
- DNS modifications

### Autonomous Execution

Approval required.

---

## Emergency Change

Change required to address:

- Service outage
- Security incident
- Business-critical disruption

Characteristics:

- Time-sensitive
- Elevated risk

### Autonomous Execution

Permitted only where explicitly authorised and documented.

Emergency execution must not bypass audit requirements.

Post-change review is mandatory.

---

# Change Request Requirements

All change requests should include:

- Description
- Business justification
- Risk assessment
- Impact assessment
- Rollback plan
- Testing approach
- Proposed implementation date

Autonomous systems should generate this information where possible.

---

# Risk Assessment

Risk assessment should follow risk-model.md.

Assessment should consider:

- Availability impact
- Security impact
- Data impact
- Compliance impact
- Customer impact
- Recoverability

The level of approval should reflect assessed risk.

---

# Impact Assessment

Before implementation, changes should identify:

- Systems affected
- Services affected
- Customers affected
- Dependencies affected

Where impact cannot be determined:

The change should be escalated for review.

---

# Approval Requirements

Approval requirements should follow approval-model.md.

Examples:

| Change Type | Typical Approval |
|-------------|------------------|
| Standard Change | Pre-approved |
| Normal Change | Single Approval |
| High Risk Change | Multiple Approvals |
| Emergency Change | Emergency Approval Process |

Approval records must be retained.

---

# Testing Requirements

Changes should be tested where practical before implementation.

Testing may include:

- Automated testing
- Integration testing
- Staging validation
- Dry-run execution

Autonomous systems should not assume successful testing.

Test results should be verified.

---

# Rollback Requirements

Changes should include a rollback strategy.

Examples:

- Previous deployment version
- Infrastructure reversion
- Configuration restore
- Backup restoration

Where rollback is not possible:

Additional review should occur before approval.

---

# Implementation

Implementation should occur using approved procedures.

Requirements:

- Authorised execution
- Audit logging
- Traceability
- Monitoring

Execution should follow execution-model.md.

---

# Verification

Following implementation:

Verify:

- Change completed successfully
- Objectives achieved
- No unexpected impact observed

Verification should be evidence-based.

Examples:

- Monitoring
- Health checks
- Functional testing
- User validation

---

# Post-Implementation Review

Significant changes should be reviewed.

Review questions:

- Did the change achieve its objective?
- Were risks correctly assessed?
- Were controls effective?
- Were unexpected effects observed?

Review outcomes should be documented.

---

# Autonomous Change Proposals

Autonomous systems may:

- Identify improvements
- Generate change requests
- Generate implementation plans
- Generate rollback procedures
- Generate testing plans

Generating a change request does not imply approval.

---

# Autonomous Change Execution

Autonomous execution should be restricted to:

- Standard changes
- Approved changes
- Low-risk changes
- Reversible changes

The burden of justification increases with risk.

---

# Change Freezes

Autonomous systems must respect organisational change freezes.

Examples:

- Peak business periods
- Regulatory events
- Major launches
- Incident response activities

Change freeze violations should be treated as policy violations.

---

# Segregation of Duties

Where possible:

The same autonomous system should not:

1. Request a change
2. Approve a change
3. Execute a change

Independent review should exist for significant changes.

---

# Audit Requirements

All changes should produce evidence sufficient to answer:

- What changed?
- Why did it change?
- Who requested it?
- Who approved it?
- Who executed it?
- What systems were affected?
- Was verification successful?

Audit requirements should follow audit-requirements.md.

---

# Emergency Changes

Emergency changes should be exceptional.

Requirements:

- Immediate documentation
- Audit records
- Risk assessment where practical
- Post-implementation review

Emergency status should not be used to avoid governance requirements.

---

# Failed Changes

Failed changes should trigger:

- Incident assessment
- Root cause analysis
- Lessons learned review

Repeated failures should result in review of:

- Procedures
- Guardrails
- Testing processes
- Autonomous permissions

---

# Change Management Is Risk Management

The purpose of change management is not to slow delivery.

The purpose is to ensure that risk is understood before change is introduced.

Well-controlled change enables autonomy.

Poorly controlled change limits it.
