# Risk Model

> **Document:** Risk Model  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how risk associated with autonomous systems should be identified, assessed, communicated, and treated.

The objective is to enable consistent decision-making across:

- Access management
- Approval processes
- Change management
- Incident response
- Vendor selection
- Autonomous execution

This document is aligned with the principles of risk management described in ISO 31000.

---

# Core Principle

Risk management exists to support decision-making.

The objective is not to eliminate risk.

The objective is to understand risk sufficiently to make informed decisions.

---

# Risk Management Process

Risk management should follow five stages:

1. Establish Context
2. Identify Risk
3. Analyse Risk
4. Evaluate Risk
5. Treat Risk

Risk should then be continuously monitored and reviewed.

---

# Establish Context

Before assessing risk, organisations should understand:

- Business objectives
- Regulatory obligations
- Data classifications
- System criticality
- Customer expectations
- Existing controls

Risk cannot be assessed in isolation.

The same action may represent different risks in different organisations.

---

# Identify Risk

Identify:

- What could happen?
- How could it happen?
- What assets are affected?
- What controls currently exist?

Examples:

- Excessive permissions
- Prompt injection
- Credential compromise
- Incorrect deployment
- Data disclosure
- Supply-chain compromise

---

# Analyse Risk

Risk analysis should consider:

## Impact

If the event occurs:

What happens?

Potential impacts include:

- Service disruption
- Security compromise
- Data disclosure
- Financial loss
- Regulatory breach
- Reputational damage

---

## Likelihood

How likely is the event to occur?

Factors may include:

- Existing controls
- Technical complexity
- Exposure
- Historical incidents
- Threat landscape

---

## Recoverability

How easily can the organisation recover?

Questions include:

- Is rollback possible?
- Is recovery documented?
- Are backups available?
- Can access be revoked?

Recoverability should influence risk assessment.

An easily reversible action often presents lower operational risk than an irreversible action.

---

# Evaluate Risk

Following analysis, risks should be classified.

This classification should determine governance requirements.

---

# Risk Categories

## Low Risk

Characteristics:

- Limited impact
- Easily recoverable
- Well understood
- Existing controls effective

Examples:

- Documentation generation
- Ticket creation
- Read-only monitoring

Typical Treatment:

Accept

---

## Medium Risk

Characteristics:

- Moderate operational impact
- Recoverable
- Requires oversight

Examples:

- Pull request creation
- Non-production deployments
- Operational recommendations

Typical Treatment:

Monitor

Apply controls

---

## High Risk

Characteristics:

- Significant operational impact
- Security implications
- Potential customer impact

Examples:

- Production deployments
- Infrastructure modification
- Customer data processing

Typical Treatment:

Approval required

Enhanced monitoring

---

## Critical Risk

Characteristics:

- Severe business impact
- Severe security impact
- Regulatory implications
- Difficult recovery

Examples:

- Privilege escalation
- Root-level access
- Security control modification
- Production data deletion

Typical Treatment:

Strong justification required

Multiple approvals

Additional controls

---

# Risk Assessment Factors

The following factors should be considered when assessing autonomous systems.

---

## Access Risk

Questions:

- What systems can be accessed?
- What permissions exist?
- Can permissions be escalated?

---

## Data Risk

Questions:

- What data is accessible?
- What classifications are involved?
- Can data leave the organisation?

---

## Execution Risk

Questions:

- Can actions be performed?
- Are actions reversible?
- Are approvals required?

---

## Vendor Risk

Questions:

- Who developed the system?
- How is it maintained?
- What supply-chain dependencies exist?

---

## Operational Risk

Questions:

- What happens if the system fails?
- What happens if the system behaves incorrectly?
- How quickly can it be disabled?

---

## Compliance Risk

Questions:

- Are regulatory obligations affected?
- Are contractual obligations affected?
- Are audit requirements satisfied?

---

# Inherent and Residual Risk

## Inherent Risk

Risk before controls are applied.

Example:

Production deployment by autonomous system.

---

## Residual Risk

Risk after controls are applied.

Controls may include:

- Guardrails
- Approvals
- Access restrictions
- Monitoring
- Audit logging

Risk decisions should be based on residual risk rather than inherent risk.

---

# Risk Treatment Options

Organisations should choose one of the following treatments.

---

## Accept

Risk is understood and tolerated.

---

## Reduce

Additional controls are implemented.

Examples:

- Additional approvals
- Reduced permissions
- Enhanced monitoring

---

## Transfer

Risk is transferred to another party.

Examples:

- Insurance
- Contractual agreements

---

## Avoid

Activity is not performed.

Example:

Refusing deployment of an autonomous system with excessive privileges.

---

# Risk Ownership

Every significant risk should have an owner.

Risk ownership includes:

- Understanding the risk
- Monitoring the risk
- Reviewing controls
- Escalating concerns

Risk ownership cannot be delegated entirely to an autonomous system.

---

# Continuous Review

Risk assessments should be reviewed when:

- Permissions change
- Scope changes
- New integrations are added
- Incidents occur
- Significant architectural changes occur

Risk assessments should not be considered permanent.

---

# Risk Drives Governance

The level of governance applied should be proportional to risk.

Examples:

Low Risk

→ Minimal approval

High Risk

→ Formal approval

Critical Risk

→ Multiple approvals and enhanced controls

The objective is proportionality rather than bureaucracy.

---

# Final Principle

Autonomous systems should be trusted according to demonstrated risk, not perceived intelligence.

A highly capable system may present unacceptable risk.

A simple system may present acceptable risk.

Risk decisions should be based on impact, exposure, controls, and recoverability rather than technical sophistication.
