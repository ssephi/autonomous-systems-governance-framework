# Running Autonomous Systems in Production

A governance framework for operating autonomous systems safely in production environments.

## Introduction

This repository provides a practical framework for operating autonomous systems within production environments.

An autonomous system is any software capable of making decisions and performing actions without direct human intervention. This includes AI agents, workflow engines, automation platforms, scripts, orchestration systems, and future technologies that may not yet exist.

The objective is not to prevent automation. The objective is to enable automation safely.

The principles described here have been derived from real-world operation of cloud infrastructure, security programmes, production platforms, incident response processes, and regulated environments.

---

## How to Read This Framework

This framework is intended to be read in layers.

Recommended reading order:

1. Governance Model
2. Governance Matrix
3. Risk Model
4. Access Model
5. Approval Model

The remaining documents provide operational, security, and assurance controls that support the governance model.

Organisations adopting the framework should begin with governance requirements before implementing operational controls.

---

## Framework Structure

The framework is organised into five layers:

1. Principles
2. Governance Controls
3. Operational Controls
4. Security Controls
5. Assurance Controls

Governance requirements determine what is permitted.

Operational controls determine how activities occur.

Security controls define protective constraints.

Assurance controls demonstrate accountability and effectiveness.

The Governance Matrix provides the authoritative relationship between governance classifications used throughout the framework.

---

## Framework Documentation

The following documents provide detailed requirements for each area of the framework.

| Document | Description |
|----------|-------------|
| [Governance Model](docs/governance-model.md) | Overarching governance structure and authority hierarchy |
| [Governance Matrix](docs/governance-matrix.md) | Mapping between risk, access, approvals, and oversight |
| [Risk Model](docs/risk-model.md) | Risk identification, assessment, and treatment |
| [Access Model](docs/access-model.md) | Access levels and permitted actions |
| [Approval Model](docs/approval-model.md) | When and how approvals must be obtained |
| [Execution Model](docs/execution-model.md) | Lifecycle for autonomous action |
| [Change Management](docs/change-management.md) | Change classification, approval, and review |
| [Audit Requirements](docs/audit-requirements.md) | Mandatory audit events and record requirements |
| [Guardrails](docs/guardrails.md) | Absolute safety constraints |
| [Prompt Security](docs/prompt-security.md) | Protecting against prompt injection and context poisoning |
| [Data Classification](docs/data-classification.md) | Data sensitivity and handling requirements |
| [Secrets Management](docs/secrets-management.md) | Credential and secret handling |
| [Incident Response](docs/incident-response.md) | Identifying and managing incidents |
| [Agent Lifecycle](docs/agent-lifecycle.md) | Lifecycle from request to retirement |
| [Multi-Agent Governance](docs/multi-agent-governance.md) | Governance requirements for systems that delegate to or invoke other autonomous systems |
| [Vendor Management](docs/vendor-management.md) | Assessment and oversight of third-party systems |
| [Testing and Validation](docs/testing-and-validation.md) | Validating that controls operate as intended before deployment and throughout operation |

---

# Principle 1: Least Privilege

An autonomous system must be granted only the permissions required to perform its intended function.

Access should be granted incrementally.

The preferred progression is:

1. No access
2. Read-only access
3. Suggested actions
4. Human-approved execution
5. Limited autonomous execution

Direct administrative access should be considered exceptional.

---

# Principle 2: Human Accountability

Responsibility cannot be delegated to an autonomous system.

A human owner must exist for:

- Configuration
- Permissions
- Outputs
- Decisions
- Actions

Autonomous systems may assist with decisions.

They do not own decisions.

---

# Principle 3: Separation of Duties

No autonomous system should be capable of:

- Detecting a problem
- Creating a solution
- Approving the solution
- Deploying the solution

without independent review.

Critical functions should be separated across systems or human approval stages.

---

# Principle 4: Default Read-Only Operation

The safest autonomous system is one that can observe but cannot modify.

New systems should initially be deployed with:

- Read-only cloud access
- Read-only source code access
- Read-only monitoring access
- Read-only documentation access

Write access should only be introduced when a business case exists.

---

# Principle 5: Auditability

Every action must be attributable.

The following must be recorded:

- Who initiated the request
- What information was supplied
- What decision was made
- What action was performed
- When it occurred

Actions that cannot be audited should not be automated.

---

# Principle 6: Fail Safe

If uncertainty exists:

The system must stop.

It must not guess.

It must not assume.

It must request clarification or human intervention.

---

# Principle 7: Capability Is Not Permission

Just because a system can perform an action does not mean it should be allowed to perform that action.

A model may be perfectly capable of:

- Deploying to production
- Modifying DNS
- Changing IAM policies
- Reading customer data

That says nothing about whether it should be permitted to do so.

---

## Framework Status

Current Version: v0.1.2

Status: Draft

This framework is under active development.

Feedback, discussion, and contributions are encouraged.

---

Licensed under CC BY 4.0.
Attribution appreciated.

---
