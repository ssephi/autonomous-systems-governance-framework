# Access Model

> **Document:** Access Model  
> **Version:** 0.1  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how autonomous systems should be granted access to production environments, business systems, source code repositories, cloud platforms, and sensitive data.

The objective is to maximise utility while minimising risk.

This model applies equally to:

- AI agents
- Automation platforms
- Workflow engines
- Bots
- Scripts
- Future autonomous systems

---

# Core Principle

Access is granted based on:

1. Required function
2. Data sensitivity
3. Potential impact
4. Recoverability

Access must never be granted solely because a capability exists.

---

# Access Levels

All autonomous systems must be assigned a single access level.

Systems may only perform actions permitted by their assigned level.

---

## Level 0 - No Access

The system has no direct access to organisational resources.

### Examples

- Public LLMs
- External chatbots
- Public AI services

### Permitted

- General discussion
- Documentation generation
- Public information analysis

### Prohibited

- Internal systems
- Source code
- Cloud platforms
- Monitoring systems
- Business data

---

## Level 1 - Read Only

The system may observe but may not modify.

### Examples

- Monitoring assistants
- Documentation assistants
- CMDB assistants

### Permitted

- Read dashboards
- Read logs
- Read repositories
- Read documentation
- Read inventories
- Read ticket systems

### Prohibited

- Creating resources
- Modifying resources
- Approving changes
- Accessing secrets

### Typical Permissions

- CloudWatch ReadOnlyAccess
- Git repository read access
- Read-only database replicas
- Monitoring APIs

---

## Level 2 - Advisory

The system may propose actions but may not execute them.

### Examples

- Incident response assistants
- Cost optimisation assistants
- Security review assistants

### Permitted

- Generate reports
- Recommend remediations
- Create draft pull requests
- Create draft tickets
- Suggest infrastructure changes

### Prohibited

- Merge code
- Execute changes
- Modify production systems

### Examples

Allowed:

"Scale the worker ASG from 4 to 8 instances."

Not allowed:

Actually scaling the ASG.

---

## Level 3 - Controlled Execution

The system may perform low-risk actions within defined boundaries.

Human approval is required for high-impact actions.

### Examples

- Ticket automation
- User lifecycle automation
- Scheduled maintenance tooling

### Permitted

- Create tickets
- Update tickets
- Restart approved services
- Run diagnostics
- Execute approved runbooks
- Create pull requests

### Approval Required

- Infrastructure changes
- IAM changes
- Production deployments
- Database modifications
- DNS modifications

### Mandatory Controls

- Audit logging
- Change tracking
- Rollback capability

---

## Level 4 - Restricted Autonomous Operation

The system may perform predefined operational actions without human approval.

Only low-risk and reversible actions are permitted.

### Examples

- Auto-scaling
- Self-healing infrastructure
- Certificate renewal
- Queue management

### Conditions

The action must be:

- Well understood
- Reversible
- Logged
- Tested
- Bound by guardrails

### Examples

Allowed:

- Add web servers to an auto-scaling group
- Renew certificates
- Restart failed workers

Not allowed:

- Modify IAM policies
- Delete databases
- Disable security controls

---

## Level 5 - Privileged Autonomous Operation

Reserved for exceptional cases.

Very few organisations should operate systems at this level.

### Requirements

- Executive approval
- Security review
- Risk assessment
- Continuous monitoring
- Periodic review

### Examples

Potentially acceptable:

- Automated trading systems
- Industrial control systems
- Mission-critical recovery systems

### Strong Recommendation

Avoid Level 5 where possible.

---

# Access Categories

Permissions should be evaluated independently across categories.

A system may be Level 3 for one category and Level 1 for another.

---

## Cloud Platforms

Examples:

- AWS
- Azure
- GCP

Preferred Maximum Level:

Level 2

Recommended Access:

- Read-only monitoring
- Cost reporting
- Resource inventory

Avoid:

- Administrator permissions
- Root-equivalent access

---

## Source Control

Examples:

- GitHub
- GitLab
- Bitbucket

Preferred Maximum Level:

Level 3

Recommended Access:

- Read repositories
- Create branches
- Open pull requests

Avoid:

- Direct merge rights
- Branch protection bypass

---

## Monitoring

Examples:

- Prometheus
- Datadog
- Grafana
- CloudWatch

Preferred Maximum Level:

Level 4

Monitoring systems are generally low risk and highly valuable.

---

## Secrets Management

Examples:

- Vault
- AWS Secrets Manager
- Azure Key Vault

Preferred Maximum Level:

Level 0

Default Position:

Autonomous systems should not have access to secrets.

Where unavoidable:

- Scope access narrowly
- Use temporary credentials
- Log all access

---

## Identity Systems

Examples:

- Active Directory
- IAM Identity Center
- Okta

Preferred Maximum Level:

Level 2

Identity systems represent a high-value target and should be treated accordingly.

---

# Prohibited Access Patterns

The following patterns should be considered unsafe.

## God Mode

One identity with unrestricted access to:

- Cloud
- Source control
- Secrets
- Identity systems

Risk: Critical

---

## Hidden Access

Permissions granted without documentation.

Risk: High

---

## Shared Identities

Multiple autonomous systems using the same credentials.

Risk: High

---

## Unreviewed Escalation

Systems capable of granting themselves additional permissions.

Risk: Critical

---

# Capability Is Not Permission

A system's ability to perform an action does not imply authorisation to perform that action.

Access decisions must be based on business requirements, risk, and governance requirements rather than technical capability.
