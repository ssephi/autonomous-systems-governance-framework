# Data Classification

> **Document:** Data Classification  
> **Status:** Draft  
> **Last Reviewed:** 2026-06-06  
> **Author:** Gary Titchmarsh  
> **Maintainer:** Gary Titchmarsh  
> **Applies To:** Autonomous Systems  

---


## Purpose

This document defines how autonomous systems should interact with organisational data classifications.

This document intentionally does not define a specific classification scheme.

Organisations should map their existing classification model onto the requirements described here.

---

# Core Principle

Autonomous systems must understand the sensitivity of information before accessing, processing, storing, transmitting, or acting upon that information.

Data classification determines:

- Whether access is permitted
- Whether approval is required
- Whether external processing is permitted
- Whether retention restrictions apply
- Whether audit requirements apply

---

# Classification Requirements

Every organisation should maintain a documented classification scheme.

At minimum, classifications should answer:

1. Who may access the data?
2. Can the data leave the organisation?
3. What would happen if the data were disclosed?
4. Are legal or regulatory requirements present?
5. Is customer consent required?

---

# Recommended Classification Structure

A classification model should include:

- Public information
- Internal information
- Restricted information
- Highly sensitive information

Organisations may use different names.

The number of levels is less important than consistency.

---

# Autonomous System Requirements

## Public Information

Examples:

- Public documentation
- Marketing content
- Published APIs
- Open-source repositories

Typical Controls:

- May be processed by autonomous systems
- May be transmitted externally
- Minimal restrictions

---

## Internal Information

Examples:

- Internal procedures
- Architecture documentation
- Inventory data
- Service catalogues

Typical Controls:

- Access limited to authorised systems
- Processing permitted
- External transmission controlled

---

## Restricted Information

Examples:

- Customer information
- Commercial agreements
- Financial information
- Security documentation

Typical Controls:

- Explicit access approval
- Audit logging
- Retention controls
- Data minimisation

---

## Highly Sensitive Information

Examples:

- Secrets
- Authentication credentials
- Encryption keys
- Personal data requiring special protection
- Regulatory protected data

Typical Controls:

- Strong justification required
- Access minimised
- Continuous monitoring
- Enhanced audit requirements

---

# Data Minimisation

Autonomous systems should only receive the data required to perform their task.

Providing complete datasets when subsets would suffice should be avoided.

Example:

Preferred:

"Provide error logs for Service A."

Avoid:

"Provide all logs for the organisation."

---

# Classification Inheritance

Derived data should inherit the classification of the most sensitive source data used to create it.

Example:

A report containing confidential customer information should be treated as confidential even if the report itself did not previously exist.

---

# External Processing

Before transmitting data to external services, organisations should determine:

- Data classification
- Regulatory requirements
- Contractual obligations
- Customer commitments

Classification alone does not determine whether external processing is acceptable.

---

# Unknown Classification

Where classification cannot be determined:

Treat the information as sensitive.

Autonomous systems should not assume information is public.

---

# Classification Mapping

Organisations should maintain a mapping between their classification scheme and autonomous system controls.

Example:

| Organisation Classification | Autonomous System Controls |
|----------------------------|---------------------------|
| Public | No restrictions |
| Internal | Authenticated access |
| Confidential | Approval required |
| Restricted | Approval + audit |
| Secret | Exceptional access only |

The specific labels are not important.

The controls are.
