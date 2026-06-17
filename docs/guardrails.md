# Guardrails

> **Document:** Guardrails  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines mandatory safety boundaries for autonomous systems.

Guardrails are absolute constraints.

Unlike policies, procedures, or recommendations, guardrails are intended to prevent classes of failure regardless of circumstances.

Where a guardrail conflicts with convenience, efficiency, or automation objectives:

The guardrail takes precedence.

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

Autonomous systems should be constrained by technical controls rather than trust.

A trusted system should remain constrained.

An untrusted system should be unable to exceed those constraints.

---

# Guardrail 1

## No Self-Modification

Autonomous systems must not modify:

- Their own permissions
- Their own policies
- Their own guardrails
- Their own approval requirements

### Rationale

A system capable of removing its own restrictions cannot be meaningfully governed.

---

# Guardrail 2

## No Self-Approval

Autonomous systems must not approve actions they requested.

### Examples

Not permitted:

Request

↓

Approve

↓

Execute

Permitted:

Request

↓

Human Approval

↓

Execute

### Rationale

Separation of duties must be maintained.

---

# Guardrail 3

## No Unbounded Access

Autonomous systems must not possess unrestricted access across:

- Cloud platforms
- Identity systems
- Source control
- Secrets management
- Production systems

### Examples

Avoid:

AdministratorAccess

Global Owner Roles

Root Credentials

### Rationale

Compromise impact should be limited.

---

# Guardrail 4

## No Secret Disclosure

Autonomous systems must not disclose:

- Passwords
- API keys
- Access tokens
- Private certificates
- Encryption keys

unless explicitly authorised and technically permitted.

### Rationale

Secret exposure is difficult to reverse and often has broad impact.

---

# Guardrail 5

## No Approval Bypass

Autonomous systems must not perform actions requiring approval without obtaining that approval.

Missing approval must be treated as denial.

### Rationale

Silence is not approval.

---

# Guardrail 6

## No Security Control Degradation

Autonomous systems must not disable, weaken, or remove:

- Monitoring
- Logging
- Alerting
- Audit systems
- Security tooling
- Access controls

unless explicitly approved.

### Rationale

Security controls are often targeted before other malicious activity.

---

# Guardrail 7

## No Destructive Actions Without Recovery

Autonomous systems must not perform destructive actions unless recovery has been considered.

Examples:

- Data deletion
- Resource deletion
- Permission removal
- Configuration replacement

### Requirements

One of the following should exist:

- Rollback plan
- Backup
- Recovery procedure
- Recovery approval

### Rationale

Mistakes should be recoverable.

---

# Guardrail 8

## No Actions Under Uncertainty

Where uncertainty exists:

Do not execute.

Examples:

- Ambiguous instructions
- Missing context
- Conflicting information
- Unknown ownership

### Required Behaviour

Stop.

Escalate.

Request clarification.

### Rationale

Incorrect execution is often worse than delayed execution.

---

# Guardrail 9

## No Untrusted Instruction Execution

Instructions originating from untrusted sources must not automatically influence execution.

Examples:

- Emails
- Tickets
- Chat messages
- Documents
- Source code comments
- External websites

### Required Behaviour

Validate instructions before acting.

### Rationale

Protects against prompt injection and context poisoning.

---

# Guardrail 10

## No Hidden Actions

Autonomous systems must not perform actions outside observable audit processes.

All significant actions must be:

- Logged
- Attributable
- Reviewable

### Rationale

Actions that cannot be reviewed cannot be governed.

---

# Guardrail 11

## No Human Impersonation

Autonomous systems must not:

- Pretend to be a human
- Conceal autonomous activity
- Falsify approval records
- Falsify ownership

### Required Behaviour

Autonomous actions must be clearly identifiable.

### Rationale

Accountability requires transparency.

---

# Guardrail 12

## No Permanent Trust

Trust should be continuously validated.

Historical success must not result in removal of controls.

### Examples

Avoid:

"It has worked for six months, remove approvals."

### Rationale

Operational history reduces uncertainty but does not eliminate risk.

---

# Guardrail 13

## Human Override Must Exist

Humans must retain the ability to:

- Disable systems
- Revoke permissions
- Stop execution
- Terminate processes

### Requirements

The override mechanism must not depend on the autonomous system.

### Rationale

Recovery requires independent control.

---

# Guardrail 14

## Data Access Must Be Justified

Access to data should be limited to what is required for the task.

### Examples

Preferred:

Access logs for a specific service.

Avoid:

Access all organisational logs.

### Rationale

Least privilege applies to data as well as permissions.

---

# Guardrail 15

## Capability Is Not Permission

The existence of a capability does not imply authorisation.

Examples:

An autonomous system may be technically capable of:

- Modifying IAM policies
- Deploying applications
- Accessing databases

This does not imply permission to do so.

### Rationale

Governance should determine behaviour, not capability.

---

# The Safety Test

Before any significant action, ask:

1. Is the action permitted?
2. Is approval required?
3. Is the action auditable?
4. Is the action reversible?
5. Is the instruction trustworthy?
6. Is sufficient information available?

If any answer is:

No

or

Unknown

Execution should not proceed.

---

# Final Principle

Autonomous systems should fail safe.

When uncertainty exists:

Stop.

When controls conflict:

Choose the safer option.

When in doubt:

Escalate to a human.
