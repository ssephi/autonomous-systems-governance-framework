# Agent Lifecycle Management

> **Document:** Agent Lifecycle Management  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---

## Purpose

This document defines the lifecycle requirements for autonomous systems operating within an organisation.

The objective is to ensure autonomous systems are:

- Identified
- Owned
- Governed
- Reviewed
- Maintained
- Retired

throughout their operational life.

This document applies to:

- AI agents
- Automation platforms
- Workflow engines
- Bots
- Scripts with autonomous behaviour
- Orchestration systems
- Future autonomous systems

---

# Core Principle

Autonomous systems are organisational assets.

They should be managed with the same discipline applied to:

- Applications
- Infrastructure
- Service accounts
- Production services

Autonomous systems must not exist without ownership, governance, and review.

---

# Lifecycle Overview

Every autonomous system should progress through the following stages:

Request

↓

Assess

↓

Approve

↓

Build

↓

Deploy

↓

Operate

↓

Review

↓

Retire

---

# Stage 1 - Request

A business need is identified.

Examples:

- Incident response assistance
- Infrastructure management
- Documentation generation
- Customer support automation

The request should define:

- Purpose
- Scope
- Expected outcomes
- Proposed owner

---

# Stage 2 - Assess

The proposed system is evaluated.

Assessment should include:

- Risk assessment
- Data classification review
- Access requirements
- Approval requirements
- Regulatory considerations
- Vendor assessment where applicable

Assessment should follow:

- risk-model.md
- data-classification.md
- vendor-management.md

---

# Stage 3 - Approve

Appropriate approval must be obtained before deployment.

Approval should include:

- Business owner approval
- Technical owner approval
- Security review where required

Approval decisions should be recorded.

---

# Stage 4 - Build

The autonomous system is created and configured.

Requirements include:

- Documented purpose
- Documented permissions
- Defined guardrails
- Defined operating model

The system should be assigned:

- Unique identifier
- Owner
- Risk classification
- Operational environment

---

# Stage 5 - Deploy

The system is introduced into operation.

Before deployment:

Verify:

- Permissions are correct
- Audit controls are enabled
- Monitoring is configured
- Documentation exists

Deployment should follow change-management.md.

---

# Stage 6 - Operate

The system performs its intended function.

During operation:

- Audit records must be retained
- Permissions must remain appropriate
- Incidents must be managed
- Changes must be controlled

Operation should follow:

- execution-model.md
- audit-requirements.md
- incident-response.md

---

# Stage 7 - Review

Autonomous systems should be reviewed periodically.

At a minimum, reviews should occur:

- Annually
- Following significant change
- Following significant incident
- Following material scope expansion

Reviews should assess:

- Continued business need
- Risk profile
- Permission appropriateness
- Operational effectiveness
- Incident history

---

# Stage 8 - Retire

Systems no longer required should be retired.

Retirement activities should include:

- Credential revocation
- Permission removal
- Data disposition
- Documentation updates
- Asset inventory updates

Retired systems should not retain active access.

---

# Ownership Requirements

Every autonomous system must have:

## Business Owner

Responsible for:

- Business justification
- Risk acceptance
- Operational necessity

Questions answered:

Why does this system exist?

---

## Technical Owner

Responsible for:

- Configuration
- Maintenance
- Monitoring
- Technical operation

Questions answered:

How does this system work?

---

## Security Function (Where Required)

Responsible for:

- Security review
- Risk oversight
- Control validation

Questions answered:

Are controls adequate?

The Security Function may consist of:

- Dedicated security teams
- Security officers
- Risk functions
- External security providers

One individual may fulfil multiple roles where appropriate.

Ownership must always be documented.

---

# Agent Inventory

Organisations should maintain an inventory of autonomous systems.

The inventory should include:

- Agent name
- Unique identifier
- Purpose
- Owner
- Risk classification
- Permissions
- Data classifications accessed
- Deployment status

An autonomous system that is not inventoried should be considered unmanaged.

---

# Agent Identity

Every autonomous system should possess a unique identity.

Avoid:

- Shared identities
- Shared credentials
- Generic service accounts

Preferred:

- One identity per autonomous system

### Rationale

Supports:

- Auditability
- Accountability
- Revocation
- Incident response

---

# Permission Reviews

Permissions should be reviewed periodically.

At a minimum, reviews should occur:

- Annually
- Following significant permission changes
- Following security incidents

Questions should include:

- Does access remain necessary?
- Has scope changed?
- Have new permissions been added?
- Can permissions be reduced?

Permission reviews should follow access-model.md.

---

# Configuration Management

Changes to:

- Models
- Prompts
- Integrations
- Tools
- Permissions

should be managed through documented change processes.

Unauthorised modifications should be investigated.

---

# Monitoring Requirements

Autonomous systems should be monitored for:

- Availability
- Performance
- Security events
- Policy violations
- Approval violations

Monitoring should be proportionate to risk.

---

# Lifecycle Events Requiring Review

The following events should trigger reassessment:

- New permissions
- New integrations
- New data sources
- Significant model changes
- Vendor changes
- Security incidents
- Ownership changes

---

# Personnel Changes

When an owner leaves the organisation or changes role:

Review:

- Ownership assignment
- Permissions
- Risk acceptance
- Operational necessity

Autonomous systems should never become ownerless.

---

# Dormant Systems

Systems inactive for extended periods should be reviewed.

Questions should include:

- Is the system still required?
- Are permissions still appropriate?
- Can the system be retired?

Dormant systems increase operational and security risk.

---

# Retirement Criteria

Retirement should be considered when:

- Business need no longer exists
- Superior replacement exists
- Risk exceeds value
- Required controls cannot be maintained

---

# Success Criteria

A mature autonomous system should be:

- Owned
- Documented
- Auditable
- Monitored
- Reviewable
- Replaceable
- Retirable

No autonomous system should become irreplaceable.

---

# Final Principle

The lifecycle of an autonomous system should be intentional.

Organisations should know:

- Why it exists
- Who owns it
- What it can access
- How it operates
- When it should be retired

If these questions cannot be answered, governance should be considered insufficient.
