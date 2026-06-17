# Incident Response

> **Document:** Incident Response  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how organisations should identify, investigate, contain, eradicate, recover from, and learn from incidents involving autonomous systems.

The objective is to ensure incidents involving autonomous systems are managed using the same disciplined approach applied to any other production system.

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

Autonomous systems are not exempt from incident response processes.

An incident involving an autonomous system should be treated with the same seriousness as an incident involving:

- Production infrastructure
- Security controls
- Applications
- Employees
- Third-party vendors

---

# Incident Categories

## Category 1 - Operational Error

The autonomous system performs an unintended action.

### Examples

- Incorrect deployment
- Unintended configuration change
- Erroneous ticket creation
- Incorrect scaling action

### Typical Impact

- Service degradation
- Increased operational effort
- Temporary disruption

---

## Category 2 - Policy Violation

The autonomous system performs an action that violates organisational policy.

### Examples

- Unapproved production change
- Unauthorised data access
- Execution outside defined guardrails

### Typical Impact

- Governance breach
- Compliance concerns
- Increased risk exposure

---

## Category 3 - Security Incident

The autonomous system contributes to or causes a security event.

### Examples

- Privilege misuse
- Secret exposure
- Access control bypass
- Unauthorised system modification

### Typical Impact

- Confidentiality compromise
- Integrity compromise
- Availability compromise

---

## Category 4 - Compromise

The autonomous system itself is believed to be compromised.

### Examples

- Supply-chain compromise
- Credential theft
- Malicious plugin behaviour
- Malicious model behaviour
- Command-and-control activity

### Typical Impact

- Critical

---

# Detection Sources

Potential indicators include:

- Audit log anomalies
- Unexpected actions
- Unusual API activity
- Permission violations
- Monitoring alerts
- User reports
- Security alerts
- Approval bypass events

---

# Incident Response Lifecycle

## 1. Identification

Determine:

- What happened?
- Which autonomous system was involved?
- Which permissions were available?
- Which resources were affected?

Record:

- Timestamp
- Detection source
- Initial impact assessment

---

## 2. Containment

The primary objective is preventing further harm.

Potential containment actions include:

- Disable the autonomous system
- Revoke credentials
- Disable integrations
- Block network access
- Remove cloud permissions
- Suspend execution queues

Containment actions should prioritise safety over availability.

---

## 3. Investigation

Determine:

- What action occurred?
- Why did it occur?
- Was the action expected?
- Was approval present?
- Was the behaviour malicious?
- Was the behaviour accidental?

Investigations should use:

- Audit records
- Approval records
- Configuration history
- System logs
- Change records

---

## 4. Eradication

Remove the cause of the incident.

Examples:

- Remove malicious code
- Remove compromised credentials
- Disable vulnerable integrations
- Correct permission assignments
- Remove unsafe prompts
- Remove compromised dependencies

---

## 5. Recovery

Restore normal operation.

Recovery should include:

- Validation of controls
- Verification of permissions
- Monitoring of affected systems
- Business approval where appropriate

Recovered systems should not be immediately trusted.

Verification should occur before returning to service.

---

## 6. Lessons Learned

Every significant incident should result in review.

Questions should include:

- Why did controls fail?
- Were guardrails sufficient?
- Were permissions appropriate?
- Was approval correctly enforced?
- Was detection timely?
- Were audit records sufficient?

Corrective actions should be tracked to completion.

---

# AI-Specific Scenarios

## Prompt Injection

Description:

Untrusted content influences system behaviour.

Examples:

- Documents
- Emails
- Support tickets
- Source code
- Web content

Response:

- Stop execution
- Preserve evidence
- Review accessed content
- Review permissions
- Assess potential actions taken

---

## Context Poisoning

Description:

Incorrect or malicious information enters the system context.

Examples:

- False documentation
- Malicious instructions
- Corrupted knowledge sources

Response:

- Identify source
- Remove affected context
- Revalidate outputs
- Review affected decisions

---

## Approval Bypass

Description:

Actions occur without required approval.

Response:

- Immediate investigation
- Review audit trail
- Review approval workflow
- Verify scope of impact

Approval bypass should be treated as a high-severity event.

---

## Excessive Permissions

Description:

The autonomous system possesses permissions beyond business requirements.

Response:

- Remove unnecessary access
- Review access model
- Perform retrospective analysis
- Verify no misuse occurred

---

## Supply Chain Compromise

Description:

Compromise of:

- Dependencies
- Plugins
- Models
- Containers
- Integrations

Response:

- Disable affected systems
- Isolate environment
- Review execution history
- Rotate credentials
- Validate software integrity

---

# Evidence Preservation

During investigation:

Do not destroy evidence.

Preserve:

- Audit records
- Approval records
- Configuration history
- Prompt history where available
- Logs
- Credentials used
- System state

Evidence requirements should align with organisational incident response policies.

---

# Authority to Disable

Organisations should designate individuals authorised to immediately disable autonomous systems.

This authority should not require approval from the autonomous system owner.

Examples:

- Security team
- Incident commander
- Operations leadership

---

# Break Glass Controls

Organisations should maintain a documented method to:

- Disable autonomous systems
- Revoke credentials
- Remove permissions
- Disable integrations

The process should function even if the autonomous system is unavailable.

---

# Post-Incident Reviews

Reviews should focus on:

- Process improvement
- Control improvement
- Detection improvement
- Risk reduction

The objective is to improve resilience rather than assign blame.

---

# Safety Overrides Availability

If uncertainty exists regarding the behaviour of an autonomous system:

Disable it.

Service disruption is generally preferable to uncontrolled execution.
