# Execution Model

> **Document:** Execution Model  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines the lifecycle that autonomous systems must follow when interacting with organisational systems, data, and resources.

The objective is to ensure actions are predictable, explainable, auditable, and controllable.

This model applies to:

- AI agents
- Automation platforms
- Workflow engines
- Bots
- Scripts
- Orchestration systems
- Future autonomous systems

---

# Core Principle

Autonomous systems should not move directly from observation to execution.

Execution should occur through a controlled lifecycle.

The preferred lifecycle is:

Observe

↓

Analyse

↓

Plan

↓

Validate

↓

Approve

↓

Execute

↓

Verify

↓

Audit

↓

Review

---

# Lifecycle Stages

## 1. Observe

The system gathers information.

Examples:

- Monitoring alerts
- Documentation
- Inventory information
- Source code
- Ticket data
- User requests

### Requirements

- Data sources must be identified
- Data classification must be respected
- Access controls must be enforced

### Output

Observed facts

---

## 2. Analyse

The system evaluates the observed information.

Examples:

- Root cause analysis
- Risk assessment
- Dependency analysis
- Impact assessment

### Requirements

- Assumptions should be identified
- Confidence should be expressed where possible
- Evidence should be retained

### Output

Findings

---

## 3. Plan

The system determines possible actions.

Examples:

- Restart service
- Scale infrastructure
- Open incident
- Create pull request
- Escalate to human

### Requirements

The plan should include:

- Expected outcome
- Risks
- Dependencies
- Rollback approach

### Output

Execution plan

---

## 4. Validate

The system determines whether the plan is permissible.

Validation should include:

- Access model review
- Approval model review
- Policy review
- Guardrail review

### Questions

- Is this action permitted?
- Is approval required?
- Are sufficient permissions available?
- Does the action violate policy?

### Output

Validated plan

or

Rejected plan

---

## 5. Approve

Where required, approval must be obtained.

### Requirements

- Approval requirements must follow approval-model.md
- Approval decisions must be auditable
- Approval records must be retained

### Output

Approved action

or

Rejected action

---

## 6. Execute

The approved action is performed.

### Requirements

- Actions must operate within granted permissions
- Actions must be logged
- Actions must be attributable

### Examples

- Deploy application
- Create ticket
- Modify infrastructure
- Execute runbook

### Output

Execution result

---

## 7. Verify

The system confirms the intended outcome occurred.

### Questions

- Did the action succeed?
- Was the objective achieved?
- Were unexpected effects observed?

### Examples

- Service health check
- Deployment validation
- Monitoring verification

### Output

Verification result

---

## 8. Audit

Execution evidence is recorded.

### Requirements

- Follow audit-requirements.md
- Preserve execution records
- Preserve approval records
- Preserve outcome records

### Output

Audit record

---

## 9. Review

The outcome is evaluated.

### Questions

- Was the action successful?
- Were controls effective?
- Were guardrails sufficient?
- Should future behaviour change?

### Output

Operational learning

---

# Decision Boundaries

Autonomous systems should not assume:

- Missing approvals
- Missing permissions
- Missing information

If required information is unavailable:

Stop.

Request assistance.

---

# Preferred Outcomes

When multiple actions are possible:

Prefer:

1. Observation
2. Recommendation
3. Human-assisted execution
4. Autonomous execution

Examples:

Preferred:

"Recommend restarting the service."

Acceptable:

"Restart service after approval."

Avoid:

"Restart service immediately."

---

# Execution Modes

## Advisory Mode

Observe

↓

Analyse

↓

Recommend

No execution occurs.

Examples:

- Security assistant
- Cost optimisation assistant
- Architecture assistant

---

## Assisted Mode

Observe

↓

Analyse

↓

Plan

↓

Approve

↓

Execute

Human approval required.

Examples:

- Infrastructure assistants
- Deployment assistants
- Operations assistants

---

## Autonomous Mode

Observe

↓

Analyse

↓

Plan

↓

Validate

↓

Execute

Approval may not be required.

Only appropriate for low-risk and well-defined actions.

Examples:

- Auto-scaling
- Certificate renewal
- Queue management

---

# Failure Handling

If execution fails:

The system should:

1. Stop execution
2. Record the failure
3. Preserve evidence
4. Notify responsible parties

Repeated execution attempts should not occur indefinitely.

---

# Uncertainty Handling

When uncertainty exists:

Do not execute.

Examples:

- Conflicting information
- Missing approvals
- Missing permissions
- Ambiguous instructions

Recommended behaviour:

Escalate.

---

# Human Authority

Humans retain authority over:

- Plans
- Approvals
- Permissions
- Execution
- Termination

Autonomous systems may assist.

They must not prevent intervention.

---

# Safe Execution Hierarchy

Preferred order of operation:

Observe

↓

Recommend

↓

Approve

↓

Execute

↓

Automate

The burden of justification increases at each stage.

The ability to automate an action is not sufficient justification for doing so.

---

# Execution Is A Privilege

Execution capability should be earned through:

- Demonstrated reliability
- Appropriate controls
- Sufficient auditability
- Proven operational value

Autonomous execution should be considered the final stage of maturity, not the starting point.
