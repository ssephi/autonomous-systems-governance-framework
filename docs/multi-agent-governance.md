# Multi-Agent Governance

> **Document:** Multi-Agent Governance  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems Operating Through Delegation  

---

## Purpose

This document defines governance requirements for autonomous systems that invoke, coordinate, supervise, delegate to, or otherwise interact with other autonomous systems.

The objective is to ensure accountability, approval requirements, permissions, auditability, and governance controls remain effective across chains of autonomous systems.

This document applies regardless of whether the systems are:

- Internal
- External
- Vendor-provided
- Open source
- Hosted
- Self-managed

---

# Core Principle

Delegation does not transfer accountability.

An autonomous system that invokes another autonomous system remains part of the accountability chain.

Each autonomous system remains independently responsible for operating within its approved scope, permissions, and guardrails.

---

# Example Topology

Single-Agent Model:

User

↓

Agent

↓

Action

---

Multi-Agent Model:

User

↓

Agent A

↓

Agent B

↓

Agent C

↓

Action

Additional systems do not remove governance requirements.

Additional systems increase governance complexity.

---

# Governance Objectives

Multi-agent systems should remain:

- Understandable
- Auditable
- Governable
- Reviewable
- Controllable

The introduction of additional agents should not obscure accountability.

---

# Accountability Chains

Every significant action should retain a complete accountability chain.

Example:

User

↓

Agent A

↓

Agent B

↓

Agent C

↓

Production Change

Audit records should preserve the complete chain.

The final action should never appear as:

Agent C

↓

Production Change

without preserving upstream context.

---

# Ownership Requirements

Every autonomous system must have:

- Business owner
- Technical owner
- Security review where required

Ownership of one system does not imply ownership of another.

Each participating system must have documented ownership.

---

# Approval Inheritance

Approval does not automatically propagate between agents.

Examples:

Approved:

Agent A may analyse monitoring data.

Not Approved:

Agent A may delegate production modification authority to Agent B.

Delegated actions must remain within the scope of the original approval.

---

# Approval Validation

Each autonomous system must independently validate:

- Approval requirements
- Access requirements
- Guardrails
- Scope restrictions

A downstream agent must not assume approvals have been validated by an upstream agent.

---

# Permission Boundaries

Permissions should be evaluated independently.

Example:

Agent A possesses:

Read-only access

Agent B possesses:

Administrative access

Agent A must not obtain administrative capability through delegation.

Delegation must not become a mechanism for privilege escalation.

---

# Effective Permission Principle

The effective permission of a multi-agent workflow should be considered equal to the highest privilege available within the workflow.

Example:

Agent A

Read-only

↓

Agent B

Administrative

↓

Production

Effective workflow risk:

Administrative

Risk assessments should consider aggregate capability.

---

# Scope Inheritance

Delegated activities must remain within approved scope.

Example:

Approved:

Analyse service health

↓

Recommend remediation

Not Approved:

Analyse service health

↓

Modify IAM policies

Delegation must not expand scope beyond approved boundaries.

---

# Agent-to-Agent Approval

Autonomous systems must not approve actions requested by other autonomous systems.

Not permitted:

Agent A

↓

Requests Action

↓

Agent B

↓

Approves Action

↓

Execution

Approval authority must remain independent.

Approval requirements should follow approval-model.md.

---

# Trust Boundaries

Each autonomous system should be considered an independent trust boundary.

Questions should include:

- Who owns the system?
- What permissions exist?
- What data is accessible?
- What controls exist?
- What audit records are available?

Trust in one system should not automatically extend to another.

---

# Cross-Organisation Agents

Additional controls should apply when agents cross organisational boundaries.

Examples:

Internal Agent

↓

Vendor Agent

↓

Vendor Tool

Questions should include:

- Where is data processed?
- Who controls execution?
- What audit capability exists?
- What contractual protections exist?

Vendor interactions should follow vendor-management.md.

---

# Shared Context

Where agents exchange information:

The following should be considered:

- Data classification
- Data minimisation
- Confidentiality
- Context poisoning risk

Information shared between agents should be limited to operational necessity.

---

# Prompt and Context Propagation

Instructions should not automatically inherit trust when passed between agents.

Example:

External Content

↓

Agent A

↓

Agent B

↓

Action

The content remains external in origin.

Propagation does not create trust.

Prompt-security.md remains applicable throughout the chain.

---

# Audit Requirements

Audit records should capture:

- Invoking agent
- Invoked agent
- Purpose
- Approval references
- Actions performed
- Outcomes

The objective is reconstructing the complete execution path.

Audit requirements should follow audit-requirements.md.

---

# Incident Response

Incidents involving multi-agent systems should identify:

- Originating system
- Intermediate systems
- Executing system
- Affected resources

Containment may require disabling multiple systems simultaneously.

Incident response should follow incident-response.md.

---

# Failure Handling

Failure in one system should not cause uncontrolled execution by another.

Examples:

- Approval validation failure
- Audit failure
- Permission validation failure
- Communication failure

Expected behaviour:

Stop.

Escalate.

Request assistance.

Fail-safe behaviour should be preserved throughout the chain.

---

# Loop Prevention

Organisations should prevent uncontrolled recursive behaviour.

Examples:

Agent A

↓

Agent B

↓

Agent A

or

Agent A

↓

Agent B

↓

Agent C

↓

Agent A

Controls should exist to detect and prevent execution loops.

---

# Chain Length

Organisations should avoid unnecessary delegation layers.

Longer chains increase:

- Complexity
- Audit burden
- Failure modes
- Governance challenges

Delegation should occur only where it provides clear value.

---

# Independent Review

High-risk multi-agent systems should undergo additional review.

Review areas may include:

- Trust boundaries
- Delegation patterns
- Permission inheritance
- Auditability
- Failure handling

Complexity should be treated as a risk factor.

---

# Governance Assessment

Questions for reviewers should include:

- Is accountability preserved?
- Are permissions clearly defined?
- Can approvals be traced?
- Are audit records complete?
- Can systems be independently disabled?
- Can delegation expand privileges?

If these questions cannot be answered confidently, governance should be considered insufficient.

---

# Final Principle

A chain of autonomous systems should not weaken governance.

Additional agents may distribute work.

They must not distribute accountability.

The organisation should always be able to determine:

- Who initiated an action
- Which systems participated
- What approvals existed
- What permissions were used
- Why the action occurred

If this cannot be determined, the multi-agent system should be considered inadequately governed.
