# Vendor Management

> **Document:** Vendor Management  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how organisations should assess, approve, monitor, and review third-party autonomous systems, AI services, models, platforms, and related vendors.

The objective is to ensure external dependencies are understood and managed appropriately.

This document applies to:

- AI vendors
- SaaS providers
- Model providers
- Agent platforms
- Open-source projects
- Hosted services
- Third-party integrations

---

# Core Principle

Trust should be proportional to impact.

A vendor should not be trusted because:

- It is popular
- It is well marketed
- It is AI-related
- It is widely adopted

Trust should be based on:

- Risk
- Access
- Data exposure
- Operational dependency
- Demonstrated controls

---

# Vendor Categories

## Category A - Low Trust Requirement

Characteristics:

- No organisational data
- No system access
- No operational dependency

Examples:

- Public chatbots
- Documentation tools
- Public model experimentation

### Typical Controls

- Minimal review
- User awareness

---

## Category B - Moderate Trust Requirement

Characteristics:

- Limited organisational data
- Limited operational impact

Examples:

- Development assistants
- Code generation tools
- Documentation systems

### Typical Controls

- Vendor review
- Data classification review

---

## Category C - High Trust Requirement

Characteristics:

- Access to organisational systems
- Access to internal information
- Operational dependency

Examples:

- Hosted agent platforms
- Infrastructure assistants
- Integrated operational tooling

### Typical Controls

- Security review
- Risk assessment
- Approval process

---

## Category D - Critical Trust Requirement

Characteristics:

- Access to privileged systems
- Access to sensitive data
- Ability to influence production operations

Examples:

- Production automation agents
- Privileged infrastructure platforms
- Identity-integrated autonomous systems

### Typical Controls

- Formal assessment
- Executive awareness
- Continuous review

---

# Assessment Areas

Before adoption, organisations should assess:

---

## Business Viability

Questions:

- Is the vendor likely to continue operating?
- Is there a clear support model?
- Is there a sustainable business model?

### Rationale

Operational dependency introduces business risk.

---

## Security Posture

Questions:

- Does the vendor operate security controls?
- Are incidents disclosed?
- Are vulnerabilities addressed?

Evidence may include:

- Security documentation
- Certifications
- Public disclosures

Certifications are useful evidence but should not replace assessment.

---

## Data Handling

Questions:

- What data is transmitted?
- Where is data stored?
- Who can access data?
- How long is data retained?

Assessment should align with data-classification.md.

---

## Access Requirements

Questions:

- What permissions are required?
- Can permissions be reduced?
- Is least privilege supported?

Assessment should align with access-model.md.

---

## Auditability

Questions:

- Can actions be traced?
- Are logs available?
- Are approvals visible?

Assessment should align with audit-requirements.md.

---

## Operational Dependency

Questions:

- What happens if the vendor disappears?
- What happens if the service becomes unavailable?
- What happens if pricing changes?

Dependency should be understood before adoption.

---

# Open Source Software

Open source software should not be automatically trusted or distrusted.

Assessment should consider:

- Maintainer activity
- Release frequency
- Community health
- Security history
- Dependency structure

### Examples

Positive indicators:

- Active maintenance
- Transparent development
- Security response process

Negative indicators:

- Unmaintained repositories
- Unknown maintainers
- Excessive dependency chains

---

# Supply Chain Risk

Assessment should consider:

- Dependencies
- Plugins
- Models
- Container images
- Build systems

Questions:

- What external components exist?
- Who maintains them?
- How are updates managed?

Supply-chain risk should be reviewed periodically.

---

# Hosted AI Services

Additional considerations:

- Prompt retention
- Model training practices
- Data residency
- Regulatory requirements
- Customer commitments

Organisations should understand what happens to submitted information.

---

# Vendor Approval

Approval should be proportional to risk.

Examples:

Low Risk

→ Informal review

High Risk

→ Security review

Critical Risk

→ Formal approval process

---

# Ongoing Review

Vendors should be reviewed periodically.

Review triggers include:

- Significant incidents
- Major platform changes
- New permissions
- New integrations
- Ownership changes

Vendor approval should not be considered permanent.

---

# Exit Planning

Before adoption, organisations should understand how the vendor could be replaced.

Questions:

- Can data be exported?
- Can access be revoked?
- Can another solution be adopted?

Exit planning should occur before dependency becomes critical.

---

# Red Flags

The following should trigger additional scrutiny:

- Excessive permissions
- Limited transparency
- No audit capabilities
- Poor security disclosure practices
- Unclear ownership
- Unmaintained software
- Hidden dependencies

No single red flag should automatically prohibit adoption.

However, risk should be assessed explicitly.

---

# Trust Boundaries

Trust should be granted in layers.

Preferred:

Read-only access

↓

Limited execution

↓

Controlled execution

↓

Privileged execution

Avoid:

Immediate privileged access.

Trust should be earned through demonstrated reliability and governance.

---

# Final Principle

Vendor selection is fundamentally a trust decision.

The question is not:

"Is this vendor secure?"

The question is:

"What level of trust are we placing in this vendor, and is that trust justified?"
