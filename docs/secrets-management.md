# Secrets Management

> **Document:** Secrets Management  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how autonomous systems may interact with secrets, credentials, authentication material, and other sensitive capabilities.

The objective is to ensure autonomous systems can perform required tasks without creating unacceptable security risk.

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

Secrets are not data.

Secrets are capabilities.

Possession of a secret may grant the ability to:

- Access systems
- Modify systems
- Impersonate identities
- Access data
- Escalate privileges

Access to secrets should therefore be considered access to the capabilities enabled by those secrets.

---

# Default Position

Autonomous systems should not have direct access to secrets.

Alternative approaches should be considered first.

Examples:

Preferred:

- Scoped API
- Broker service
- Temporary credentials
- Approved execution workflow

Avoid:

- Direct access to root credentials
- Direct access to administrator credentials
- Unrestricted secret retrieval

---

# Secret Categories

## Category A - Low Impact

Examples:

- Public API tokens
- Non-production credentials
- Low-risk service credentials

Typical Controls:

- Restricted access
- Audit logging

---

## Category B - Operational

Examples:

- Application credentials
- Service accounts
- Integration credentials

Typical Controls:

- Access justification
- Audit logging
- Rotation requirements

---

## Category C - Privileged

Examples:

- Administrative credentials
- Production credentials
- Infrastructure credentials

Typical Controls:

- Strong justification
- Approval requirements
- Enhanced monitoring

---

## Category D - Critical

Examples:

- Root credentials
- Vault administration
- Key management systems
- Certificate authority systems

Typical Controls:

- Exceptional access only
- Executive approval where appropriate
- Continuous monitoring

---

# Preferred Access Model

Autonomous systems should interact with services rather than secrets.

Preferred:

Autonomous System

↓

Approved Service

↓

Secret Usage

Avoid:

Autonomous System

↓

Secret Retrieval

↓

Direct Secret Exposure

### Rationale

The safest secret is one that is never disclosed.

---

# Temporary Credentials

Temporary credentials should be preferred over long-lived credentials.

Examples:

- AWS STS credentials
- Temporary access tokens
- Short-lived certificates

Benefits:

- Reduced exposure window
- Easier revocation
- Reduced compromise impact

---

# Least Privilege

Access should be limited to:

- Required secrets
- Required actions
- Required duration

Avoid:

"Read all secrets"

Prefer:

"Read specific credential for specific task"

---

# Secret Retrieval

Where retrieval is required:

The following should be recorded:

- Requesting identity
- Secret identifier
- Purpose
- Timestamp
- Outcome

Secret values should not be recorded in audit logs.

---

# Secret Disclosure

Autonomous systems must not disclose:

- Passwords
- Access tokens
- API keys
- Encryption keys
- Private certificates
- Session tokens

unless explicitly authorised and technically permitted.

Approval alone should not bypass technical controls.

---

# Secret Storage

Autonomous systems should not:

- Store secrets in prompts
- Store secrets in context windows
- Store secrets in memory systems
- Store secrets in chat history

unless specifically designed and approved for that purpose.

Preferred:

Dedicated secret management systems.

Examples:

- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager

---

# Context Protection

Secrets should be excluded from:

- Prompt history
- Training data
- Analytics systems
- Telemetry platforms
- Debug output

where technically possible.

---

# Secret Rotation

Secrets accessible to autonomous systems should be rotated regularly.

Rotation frequency should align with organisational policy.

Events requiring immediate rotation include:

- Suspected compromise
- Unauthorised access
- Supply-chain compromise
- Privilege escalation incident

---

# Human Approval Requirements

The following activities should require approval:

- Access to privileged secrets
- Creation of new privileged credentials
- Changes to secret management policies
- Changes to secret rotation controls

Approval requirements should follow approval-model.md.

---

# Prohibited Patterns

## Shared Credentials

Avoid:

Multiple autonomous systems sharing the same credentials.

Preferred:

Unique identities per system.

---

## Hardcoded Secrets

Avoid:

Secrets embedded in:

- Source code
- Configuration files
- Prompts
- Documentation

---

## Permanent Administrative Credentials

Avoid:

Long-lived administrative credentials.

Preferred:

Temporary privileged access.

---

## Secret Export

Avoid:

Bulk export of secrets.

Preferred:

Controlled retrieval of specific secrets.

---

# Break Glass Access

Emergency access procedures should exist for:

- Service recovery
- Disaster recovery
- Incident response

Break glass credentials should:

- Be documented
- Be monitored
- Be periodically tested
- Remain outside normal autonomous workflows

---

# Monitoring Requirements

The following events should generate audit records:

- Secret access
- Secret creation
- Secret modification
- Secret deletion
- Permission changes
- Failed access attempts

Monitoring should be independent of the consuming system.

---

# Secret Compromise Response

If compromise is suspected:

1. Revoke access
2. Rotate affected secrets
3. Review audit records
4. Assess affected systems
5. Investigate root cause
6. Restore access only after validation

Compromise should be assumed until disproven.

---

# Capability Inheritance

Access to a secret implies access to the capability enabled by that secret.

Examples:

Read access to:

AWS Administrator credential

=

Potential administrative control of AWS

Read access to:

Production database credential

=

Potential access to production data

Risk assessments should consider downstream capabilities rather than the secret itself.

---

# Final Principle

Autonomous systems should be granted the ability to use secrets wherever possible.

They should be granted the ability to view secrets only when necessary.

The difference is significant.

A system that can use a capability is easier to govern than a system that can extract and disclose that capability.
