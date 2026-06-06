# Testing and Validation

> **Document:** Testing and Validation  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems and LLM-Based Autonomous Systems

---

## Purpose

This document defines testing and validation requirements for autonomous systems before deployment and throughout their operational life.

The objective is to ensure autonomous systems operate as intended, remain within defined controls, and continue to satisfy governance requirements.

Testing should validate both functionality and governance controls.

---

# Core Principle

Controls should be tested, not assumed.

The existence of a control does not demonstrate its effectiveness.

Validation should provide evidence that controls operate as intended.

---

# Testing Objectives

Testing should demonstrate:

- Intended functionality operates correctly
- Access controls operate correctly
- Approval requirements operate correctly
- Audit requirements operate correctly
- Guardrails operate correctly
- Failure handling operates correctly
- Recovery processes operate correctly

---

# Validation Lifecycle

Testing should occur:

- Before initial deployment
- Following significant change
- Following significant incident
- Following material scope expansion
- At least annually

---

# Pre-Deployment Validation

Before deployment, organisations should verify:

- Ownership is assigned
- Risk assessment completed
- Required approvals obtained
- Permissions are appropriate
- Audit controls are enabled
- Monitoring is configured

Deployment should not proceed until validation is complete.

---

# Functional Testing

Validate intended behaviour.

Examples:

- Ticket creation
- Documentation generation
- Infrastructure recommendations
- Approved operational actions

Questions:

- Does the system perform its intended function?
- Does the output meet requirements?
- Are expected outcomes achieved?

---

# Access Control Testing

Validate permissions.

Questions:

- Can authorised actions be performed?
- Are unauthorised actions blocked?
- Is least privilege maintained?

Examples:

Expected:

Read-only access allows reading.

Expected:

Read-only access prevents modification.

---

# Approval Testing

Validate approval controls.

Questions:

- Are approvals requested when required?
- Are approvals enforced?
- Can expired approvals be used?
- Can approvals be bypassed?

Expected Outcome:

Approval requirements remain effective under all tested scenarios.

---

# Audit Testing

Validate audit requirements.

Questions:

- Are actions recorded?
- Are approvals recorded?
- Is attribution preserved?
- Can records be independently reviewed?

Testing should follow audit-requirements.md.

---

# Guardrail Testing

Validate guardrails.

Examples:

Attempt:

- Permission escalation
- Approval bypass
- Secret disclosure
- Security control modification
- Destructive actions

Expected Outcome:

Execution is prevented.

---

# Failure Testing

Validate behaviour during failure.

Examples:

- Service unavailable
- API unavailable
- Missing data
- Invalid responses
- Timeout conditions

Expected Outcome:

Fail-safe behaviour.

The system should stop, escalate, or request assistance.

---

# Recovery Testing

Validate recovery processes.

Questions:

- Can permissions be revoked?
- Can execution be halted?
- Can the system be disabled?
- Can operations be restored?

Recovery capabilities should not be assumed.

---

# Prompt Security Testing

Where applicable, validate resistance to:

- Prompt injection
- Indirect prompt injection
- Context poisoning
- Instruction confusion

Testing should follow prompt-security.md.

This requirement applies primarily to LLM-based autonomous systems.

---

# Incident Response Validation

Validate incident response capabilities.

Examples:

- Credential compromise
- Excessive permissions
- Approval bypass
- System compromise

Questions:

- Can incidents be detected?
- Can systems be disabled?
- Can evidence be collected?

Testing should follow incident-response.md.

---

# Vendor Validation

Third-party autonomous systems should be validated before production use.

Validation should include:

- Permission review
- Audit capability review
- Security control review
- Operational review

Vendor claims should not replace validation.

---

# Change Validation

Significant changes should trigger revalidation.

Examples:

- New permissions
- New integrations
- New models
- New tools
- New execution capabilities

The scope of testing should reflect the scope of change.

---

# Evidence Requirements

Testing should produce evidence.

Examples:

- Test records
- Validation reports
- Approval records
- Screenshots
- Audit logs

Evidence should be retained in accordance with organisational requirements.

---

# Validation Outcomes

Testing outcomes should be classified as:

## Pass

Requirements satisfied.

---

## Pass with Conditions

Requirements satisfied with documented limitations.

Additional controls may be required.

---

## Fail

Requirements not satisfied.

Deployment should not proceed until issues are resolved or formally accepted through risk management processes.

---

# Independent Validation

Higher-risk systems should undergo independent review where practical.

Examples:

- Security review
- Peer review
- External assessment

Independent validation increases confidence in results.

---

# Continuous Validation

Validation is not a one-time activity.

Changes in:

- Risk
- Scope
- Permissions
- Integrations
- Threat landscape

may invalidate previous testing.

Validation should be repeated throughout the operational lifecycle.

---

# Final Principle

Trust should be based on demonstrated behaviour rather than assumed behaviour.

An untested control should be treated as an unproven control.

Autonomous systems should earn trust through validation, not receive trust by default.
