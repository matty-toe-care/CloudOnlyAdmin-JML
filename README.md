# Custom Extensions in Entra Identity Governance

Custom extensions allow you to inject **external logic** into Microsoft Entra Identity Governance workflows. They enable scenarios that go beyond native capabilities by calling out to your own systems, APIs, or business logic at key points in the identity lifecycle.

---

## What Is a Custom Extension?

A **custom extension** is an integration point that allows Entra Identity Governance to invoke external services during governance workflows.

With custom extensions, you can:

- Execute external logic during identity lifecycle events  
- Integrate with systems that are not natively supported  
- Enforce organization-specific policies and controls  
- Extend governance workflows without modifying core platform behavior  

Conceptually, custom extensions act as **event-driven hooks** that allow Entra to delegate decisions or actions to your own services.

---

## Where Custom Extensions Are Used

Custom extensions are primarily used in two areas of Entra Identity Governance:

- **Lifecycle Workflows**
- **Entitlement Management**

Each serves a different purpose but follows the same core principle: extending governance decisions beyond Microsoft Entra.

---

## Lifecycle Workflows

Lifecycle workflows automate identity-related processes such as onboarding, offboarding, and job changes.  
Custom extensions allow these workflows to interact with external systems at specific stages.

### What You Can Do

Using custom extensions in lifecycle workflows, you can:

- Trigger downstream processes when users join, leave, or change roles  
- Notify HR, ITSM, or ticketing platforms of lifecycle events  
- Apply custom compliance or validation checks  
- Provision or deprovision access in legacy or non-native systems  

### Example Scenarios

- Send a request to HR to prepare onboarding materials for a new employee  
- Disable accounts in a legacy application during offboarding  
- Update physical access or badge systems when a user changes departments  

---

## Entitlement Management

Entitlement Management governs access packages, approvals, and access reviews.  
Custom extensions allow you to introduce **external decision-making and auditing** into these access flows.

### What You Can Do

With custom extensions in Entitlement Management, you can:

- Perform external risk or compliance checks before granting access  
- Notify third-party systems when access is approved or revoked  
- Record entitlement decisions in external audit or logging systems  
- Enforce business rules that are not supported by built-in policies  

### Example Scenarios

- Require a risk assessment from an external system before approving access to sensitive resources  
- Notify a custom management system when an access package is assigned  
- Log access decisions to an external database for compliance and audit purposes  

---

## Getting Started

1. Review the sample templates provided in this repository  
2. Adapt the templates to match your organization’s requirements  
3. Test all extensions thoroughly in **non-production environments**  
4. Do **not** deploy directly to production without security review and validation  

---

## Key Considerations

- Custom extensions run **outside** of Entra — availability and reliability depend on your external services  
- Failures in external logic can impact governance workflows  
- Proper authentication, authorization, and logging are critical  

Design custom extensions with **resilience, security, and observability** in mind.
