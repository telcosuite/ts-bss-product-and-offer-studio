# Pricing, Promotion, And Discount Feature Specification

Reviewed: 2026-06-07

Suite: BSS Commercial

App: [Product And Offer Studio App](../README.md)

Source module detail: [Modules And Features](../modules-and-features.md)

Feature area slug: `pricing-promotion-and-discount`

## Feature Intent

Manage recurring, one-time, usage, deposit, penalty, device, installation, and discount prices. Define promotions, eligibility, validity, approval rules, and price override controls.

Pricing, Promotion, And Discount turns that intent into a controlled product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization capability: the app owns the pricing, promotion, and discount lifecycle state, validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference, and leaves sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care consumers with auditable status rather than spreadsheet or direct-database workarounds.

## Personas Covered

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

## Persona-Specific Outcomes

| Persona | Decision rights and jobs-to-be-done | Feature outcome |
| --- | --- | --- |
| Product manager | Defines and approves pricing, promotion, and discount rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Product manager can complete, approve, monitor, or audit pricing, promotion, and discount with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Pricing manager | Defines and approves pricing, promotion, and discount rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Pricing manager can complete, approve, monitor, or audit pricing, promotion, and discount with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Commercial operations user | Defines and approves pricing, promotion, and discount rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Commercial operations user can complete, approve, monitor, or audit pricing, promotion, and discount with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Catalog governance user | Defines and approves pricing, promotion, and discount rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Catalog governance user can complete, approve, monitor, or audit pricing, promotion, and discount with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |

## Core User Journeys Covered

| Step | User or system intent | Feature responsibility |
| ---: | --- | --- |
| 1 | Define product specifications, offerings, bundles, and categories. | Pricing, Promotion, And Discount captures the intake and source authority for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 2 | Define pricing, promotions, discounts, and approval rules. | Pricing, Promotion, And Discount validates eligibility, policy, and dependency state for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 3 | Define configurable options, compatibility, defaults, and guided-selling constraints. | Pricing, Promotion, And Discount orchestrates owned lifecycle updates and downstream handoffs for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 4 | Attach agreements, contract terms, commitments, penalties, renewals, and entitlements. | Pricing, Promotion, And Discount routes fallout, approval, retry, cancellation, or compensation work for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 5 | Validate catalog readiness against service/resource design, fulfillment, billing, campaign, and channels. | Pricing, Promotion, And Discount publishes completion, reconciliation, and evidence events for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 6 | Publish versioned offers to CPQ, digital commerce, partner marketplace, billing, and fulfillment. | Pricing, Promotion, And Discount keeps operational reporting current for the journey owner for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records pricing, promotion, and discount state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |

## Missing Use Cases And Scenarios

| Scenario | Required behavior |
| --- | --- |
| Happy path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: A product manager versions a product offering, pricing manager approves charge and discount structures, and commercial operations publishes the offer to sales, digital, partner, billing, and order channels. |
| Assisted path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: A catalog governance user blocks launch because service/resource realization, tax class, revenue account, or channel disclosure evidence is incomplete. |
| Automated path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: CPQ, digital commerce, and partner marketplace query the effective catalog version and receive eligibility, configuration, price, and contract-term references without local catalog writes. |
| Channel path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: Retail, dealer, self-care, and partner channels receive the same product offering version, eligibility window, price disclosure, and withdrawal rule. |
| Back-office path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: Pricing, tax, finance, and regulatory users review approval evidence, tariff filing status, revenue mapping, and launch/no-go decisions before effective date. |
| Sunset path | Pricing, Promotion, And Discount must support this path for pricing, promotion, and discount: A product sunset or migration plan identifies active customer products, contract penalties, replacement offers, communication plan, and billing/order impacts before retirement. |

## Core Workflow And Control Points

| Control point | Required behavior | Evidence captured |
| --- | --- | --- |
| Trigger | Start pricing, promotion, and discount from a product concept, price change, promotion, agreement update, launch readiness gate, sunset migration, channel publication request, or catalog API request with source channel, actor, tenant, customer/account/product/order references where applicable, and idempotency key. | Intake timestamp, source, actor, correlation ID, initiating record, and submitted payload hash. |
| Validation | Validate catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference before mutating product/offering/price/configuration/agreement catalog context state or handing work to another app. | Validation result, policy decision, source authority, missing fields, and permitted next action. |
| Orchestration | Coordinate Sales CPQ, Marketing, Order Management Hub, Service And Resource Design Studio, Billing, Usage/Charging, tax engines, finance/ERP, partner marketplace, self-care, and assurance readiness checks using APIs, events, workflow tasks, or governed projections while preserving app mastership: Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls. | Downstream owner, dependency state, request/response reference, retry counter, and event IDs. |
| Exception | Route pricing, promotion, and discount fallout, policy failures, manual approvals, retries, rollback, compensation, and cancellation to accountable queues. | Queue owner, severity, due date, customer/revenue/compliance impact, reason code, comments, and evidence links. |
| Completion | Close pricing, promotion, and discount only when owned lifecycle state, downstream handoffs, reconciliation, notifications, and reporting facts are complete or explicitly excepted. | Completion state, before/after values, reconciliation result, notification status, approver, and closure event. |
| Evidence | Preserve audit and regulatory evidence for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation with role-aware masking and retention/legal-hold controls. | Audit log, policy version, document/evidence reference, retention class, legal hold flag, and export controls. |

## Detailed Feature Backlog

| Feature ID | Feature | Parent feature area | Priority guidance |
| --- | --- | --- | --- |
| F-pricing-promotion-and-discount-01 | Manage recurring | Pricing, Promotion, And Discount | P1: required when manage recurring blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |
| F-pricing-promotion-and-discount-02 | Installation | Pricing, Promotion, And Discount | P2: required when installation blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |
| F-pricing-promotion-and-discount-03 | discount prices | Pricing, Promotion, And Discount | P2: required when discount prices blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |
| F-pricing-promotion-and-discount-04 | Define promotions | Pricing, Promotion, And Discount | P2: required when define promotions blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |
| F-pricing-promotion-and-discount-05 | Approval rules | Pricing, Promotion, And Discount | P2: required when approval rules blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |
| F-pricing-promotion-and-discount-06 | price override controls | Pricing, Promotion, And Discount | P2: required when price override controls blocks product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization; phase optimization after the app-owned lifecycle, handoff, and audit controls are stable. |

## Acceptance Criteria

### Record and lifecycle management

Feature detail: Create, search, view, update, retire, reinstate, and track lifecycle state for pricing, promotion, and discount records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-01-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete record and lifecycle management for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-01-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in record and lifecycle management, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-01-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for record and lifecycle management, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-01-04 Exception path:** Given validation, downstream response, or compliance control fails during record and lifecycle management, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-01-05 Completion evidence:** Given record and lifecycle management is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Validation, policy, and eligibility

Feature detail: Validate pricing, promotion, and discount changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-02-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete validation, policy, and eligibility for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-02-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in validation, policy, and eligibility, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-02-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for validation, policy, and eligibility, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-02-04 Exception path:** Given validation, downstream response, or compliance control fails during validation, policy, and eligibility, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-02-05 Completion evidence:** Given validation, policy, and eligibility is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Work queues and approvals

Feature detail: Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-03-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete work queues and approvals for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-03-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in work queues and approvals, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-03-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for work queues and approvals, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-03-04 Exception path:** Given validation, downstream response, or compliance control fails during work queues and approvals, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-03-05 Completion evidence:** Given work queues and approvals is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Search, timeline, and operational views

Feature detail: Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for pricing, promotion, and discount work. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-04-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete search, timeline, and operational views for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-04-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in search, timeline, and operational views, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-04-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for search, timeline, and operational views, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-04-04 Exception path:** Given validation, downstream response, or compliance control fails during search, timeline, and operational views, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-04-05 Completion evidence:** Given search, timeline, and operational views is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### API and event behavior

Feature detail: Expose command, query, and event contracts for pricing, promotion, and discount so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-05-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete API and event behavior for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-05-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in API and event behavior, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-05-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for API and event behavior, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-05-04 Exception path:** Given validation, downstream response, or compliance control fails during API and event behavior, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-05-05 Completion evidence:** Given API and event behavior is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Audit, evidence, and reporting

Feature detail: Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. For pricing, promotion, and discount, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-pricing-promotion-and-discount-06-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete audit, evidence, and reporting for pricing, promotion, and discount, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-pricing-promotion-and-discount-06-02 Assisted path:** Given pricing, promotion, and discount needs manual review, when a persona resolves missing data, approval, or policy conflict in audit, evidence, and reporting, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-pricing-promotion-and-discount-06-03 Automated path:** Given an API consumer or event submits pricing, promotion, and discount data for audit, evidence, and reporting, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-pricing-promotion-and-discount-06-04 Exception path:** Given validation, downstream response, or compliance control fails during audit, evidence, and reporting, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-pricing-promotion-and-discount-06-05 Completion evidence:** Given audit, evidence, and reporting is ready to close for pricing, promotion, and discount, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

## Negative Scenarios

| Scenario | Expected behavior |
| --- | --- |
| Unauthorized pricing, promotion, and discount access or mutation | Reject the request, mask product/offering/price/configuration/agreement catalog context data, and record actor, channel, tenant, policy decision, and correlation ID. |
| Missing mandatory pricing, promotion, and discount context | Keep pricing, promotion, and discount in draft, blocked, or rejected state with field-level errors for catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and do not publish downstream handoff events. |
| Invalid pricing, promotion, and discount lifecycle transition | Block the transition, show allowed next states, preserve prior state/version, and require permitted role or automated policy to resubmit. |
| Conflicting master data for pricing, promotion, and discount | Route correction to the owning app named by data mastery and prevent local shadow updates to customer, catalog, order, inventory, billing, usage, risk, or partner masters. |
| Downstream sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency unavailable | Fail fast for synchronous decisions or queue controlled retry with owner, due date, backoff policy, and customer/revenue impact flag. |
| Duplicate, stale, or out-of-order pricing, promotion, and discount request | Use optimistic locking, event version, source timestamp, and idempotency key so retries cannot duplicate work or corrupt current state. |
| Policy, consent, regulatory, or geography breach | Stop the transaction, preserve the policy decision, notify only permitted roles, and enforce tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation. |
| Manual override for pricing, promotion, and discount | Require approval role, reason code, expiry, compensating action, post-action review, and searchable audit evidence. |
| Sensitive evidence requested for pricing, promotion, and discount | Mask or deny restricted KYC, payment, fraud, complaint, usage, tax, or legal evidence while keeping operational task status visible. |
| Reconciliation mismatch after pricing, promotion, and discount completion | Reopen or hold closure until sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care state agrees or an approved exception with finance/customer/compliance impact is recorded. |

## Edge Cases

| Edge case | Expected handling |
| --- | --- |
| Bulk or project-scale pricing, promotion, and discount processing | Support validation preview, staged commit, partial failure report, throttling, replay, and rollback or repair plan before production release. |
| Long-running pricing, promotion, and discount journey | Expose waiting, blocked, retrying, escalated, compensated, corrected, and completed states with timers, owners, and customer/revenue impact. |
| Historical pricing, promotion, and discount correction | Allow effective-dated correction with reason, old/new values, approver, downstream recalculation trigger, and retention/legal-hold validation. |
| Multi-brand, multi-tenant, or data-residency boundary | Apply tenant, brand, market, geography, language, currency, and data-residency controls consistently in UI, API, event, and reporting paths. |
| High-volume operational period for pricing, promotion, and discount | Protect critical flows with pagination, async export, queue back-pressure, circuit breakers, dashboard filters, and runbook-defined load-shedding. |
| Overlapping catalog effective dates | Prevent ambiguous product offering, price, promotion, or agreement versions from being published to CPQ, order, billing, charging, or partner channels. |
| Discount stack conflict | Reject incompatible discounts, promotions, tax rules, or commitment penalties and send the pricing manager an auditable approval or correction task. |
| Service/resource realization gap | Hold launch readiness until OSS design confirms product-to-service/resource mapping and order decomposition can execute. |
| Regulatory filing not approved | Block sellable state for regulated offers and preserve tariff, disclosure, and approval evidence. |
| Grandfathered customer base | Keep existing customer products billable and serviceable while blocking new sales and driving approved migration treatments. |

## Suite Gap Review Closure Addendum

Source review: [02 Bss Commercial Gap Review](../../../../suite-gap-reviews/02-bss-commercial-gap-review.md)

This addendum applies the suite gap-review findings tied to this feature file. It supplements the baseline feature specification and should be carried into epic, story, API, event, data, and test refinement.

### Review Backlog Items Addressed

| Severity | Gap-review item | Closure expectation |
| --- | --- | --- |
| High | Tariff/tax/revenue filing approval gate before publication. | Add concrete happy path, negative path, edge-case, API/event/data control, reporting, and test evidence for this feature area. |

### Acceptance Criteria Additions

1. Given an offer is ready to publish, when CPQ, cart, order, fulfillment, activation, billing, care, self-care, partner, and reporting certification has not passed for the target channel/market, then publication is blocked.
2. Given a price or tax mapping changes, when tariff, tax, revenue account, contract, and bill-rendering controls are incomplete, then the offer cannot be sold or migrated.
3. Given a product is retired, when active customers remain, then permitted MACD actions, migration offer, billing treatment, communications, and exception owners are published.

### Negative Scenario Additions

1. New bundle publishes without a service/resource mapping; block orders and roll back catalog version.
2. Promotion discount exceeds approved margin or regulatory disclosure; require approval or deny sale.
3. Grandfathered plan customer attempts an unsupported add-on; return allowed alternatives and preserve customer communication evidence.

### API, Event, Data, And Reporting Updates

- Add or refine command/query APIs so the owning app remains the system of record and consumers do not bypass app APIs.
- Add lifecycle events for the reviewed gap, including created, validated, blocked, approved, completed, failed, corrected, replayed, and reconciliation-failed variants where applicable.
- Capture idempotency keys, correlation IDs, source freshness, lineage, confidence, policy version, owner, SLA/OLA timers, and audit evidence.
- Add dashboards or operational reports for aging, failure reason, confidence/quality, consumer impact, exception backlog, and closure proof.
- Extend the test approach with happy-path, negative, edge-case, contract, event replay, data reconciliation, security, accessibility, and operational-readiness tests for the listed review items.

## API, Event, And Data Requirements

Related APIs and API areas: [TMF671](../../../../../references/tmforum-open-apis/openapi-specs/TMF671_Promotion), [TMF620](../../../../../references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog)

TMF API fit and extension notes:

- Use TMF671, TMF620 for the TMF resource areas already identified in this feature specification; do not replace those resources with local-only contracts when the TMF API covers the lifecycle or query behavior.
- Extension APIs are allowed only for launch readiness gates, test catalog certification, no-go/rollback decisioning, tax class mapping, revenue account mapping, grandfathering rules, and forced migration orchestration where no direct TMF resource exists; each extension must be explicitly labelled non-TMF, documented with OpenAPI, and aligned to TMF-style id, href, lifecycle state, relatedParty, relatedEntity, error, pagination, and event-envelope patterns where practical.
- Command APIs for pricing, promotion, and discount must cover create/initiate, validate, update, approve/reject, hold/release, cancel, rollback or compensate where applicable, retry, correct, and close.
- Query APIs for pricing, promotion, and discount must cover search, detail, timeline, related product/offering/price/configuration/agreement catalog context references, dependency graph, work queue, metrics, and audit/evidence retrieval with role-aware masking.
- Domain events for pricing, promotion, and discount must include created, validated, blocked, approved, rejected, updated, handoff requested, exception raised, exception resolved, cancelled, compensated, completed, corrected, and reconciliation failed where the lifecycle uses those states.

Data and ownership requirements:

- Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls; other apps consume pricing, promotion, and discount state through APIs, events, governed projections, workflow tasks, or certified data products.
- Store source channel, actor, tenant/brand/market, external references, status reason, timestamps, policy decision, before/after values, related customer/account/product/order/bill/usage/ticket references where applicable, and evidence links.
- Keep read projections, analytics extracts, and DWH/lakehouse outputs separate from operational writes so Pricing, Promotion, And Discount does not create shadow mastership.
- Provide reconciliation outputs that prove sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependencies have completed, failed, or remain explicitly owned.

Integration and handoff requirements:

- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Sales CPQ through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Marketing through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Order Management Hub through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Service And Resource Design Studio through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Billing through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with Usage/Charging through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with tax engines through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with finance/ERP through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with partner marketplace through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with self-care through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Pricing, Promotion, And Discount must exchange pricing, promotion, and discount state or evidence with assurance readiness checks through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.

## Non-Functional Requirements

- Scale and latency: catalog search P95 below 500 ms, offer eligibility rule response P95 below 300 ms for CPQ paths, 99.9% catalog API availability during selling hours, versioned publication with rollback, and immutable audit for prices and agreement terms.
- Availability and resilience: Pricing, Promotion, And Discount must support 99.9% or higher availability for interactive and API paths that gate lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping, with queue back-pressure, retry, replay, and circuit-breaker controls for downstream integrations.
- Auditability and retention: pricing, promotion, and discount history must preserve actor, channel, reason, old/new value, policy version, approval, event ID, external reference, and retention/legal-hold class for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation.
- Localization and accessibility: Pricing, Promotion, And Discount user tasks, customer/partner communications, currency/date formats, invoice or offer disclosures where applicable, and error messages must support market localization, WCAG-aligned accessibility, and role-aware data masking.
- Data protection: API, event, export, and dashboard paths must enforce tenant isolation, data residency, purpose limitation, least privilege, field-level masking, and secure evidence storage for product/offering/price/configuration/agreement catalog context.

## Compliance, Security, And Privacy

- Pricing, Promotion, And Discount must enforce tariff filing for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce advertised price controls for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce tax jurisdiction mapping for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce revenue code mapping for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce contract term evidence for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce accessibility of offer disclosures for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce approval audit for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce retention for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce data residency for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Pricing, Promotion, And Discount must enforce tenant isolation for pricing, promotion, and discount records, UI actions, API payloads, events, reports, and evidence exports.
- Privileged actions on pricing, promotion, and discount require role-based approval, reason code, expiration where relevant, and post-action review by commercial operations, catalog governance, pricing governance, and product lifecycle management.
- Sensitive product/offering/price/configuration/agreement catalog context evidence must be masked in search, timelines, exports, analytics, partner views, and operational dashboards unless the persona has a permitted purpose.

## Observability And Operations

- Metrics: track pricing, promotion, and discount intake volume, validation failure rate, policy rejection rate, automation rate, manual override rate, queue aging, retry count, cancellation/rollback/compensation count, reconciliation mismatch, and completion quality by tenant, market, channel, product, partner, and owning team.
- Queues: provide work queues for draft, pending validation, pending approval, blocked dependency, exception, retrying, customer-impacting, revenue-impacting, compliance-impacting, compensated, corrected, completed, and archived pricing, promotion, and discount records.
- Alerts: alert commercial operations, catalog governance, pricing governance, and product lifecycle management when pricing, promotion, and discount queue aging, downstream failure, event publication failure, reconciliation mismatch, abnormal policy override, or SLA/OLA breach risk exceeds threshold.
- Runbooks: document triage, retry, replay, rollback, compensation, manual approval, customer/partner communication, evidence export, and reconciliation steps for Pricing, Promotion, And Discount.
- Replay and reconciliation: support idempotent replay for events, files, callbacks, and workflow tasks so Pricing, Promotion, And Discount can recover without duplicate product/offering/price/configuration/agreement catalog context state or lost audit history.
- Ownership: commercial operations, catalog governance, pricing governance, and product lifecycle management owns first-line operational health; architecture, data, security, and compliance teams own policy and conformance review for the pricing, promotion, and discount lifecycle.

## Test Approach

| Test layer | Required coverage |
| --- | --- |
| Unit tests | Field rules, lifecycle transitions, policy decisions, duplicate detection, effective dating, masking, and product/offering/price/configuration/agreement catalog context state calculations for pricing, promotion, and discount. |
| API contract tests | Commands, queries, errors, idempotency, pagination, filtering, version compatibility, and TMF-aligned payloads for TMF671, TMF620 plus documented extension APIs. |
| Event contract tests | pricing, promotion, and discount event names, payload shape, changed fields, correlation ID, idempotency key, ordering metadata, replay behavior, and subscriber compatibility. |
| Workflow tests | Happy path, assisted path, automated path, partner/channel path, approval, exception, timeout, retry, cancellation, rollback, compensation, correction, and closure for product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization. |
| Integration tests | Handoffs with sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care owners, external provider unavailability, eventual consistency, reconciliation, and no direct database access. |
| Security and privacy tests | Tenant isolation, role permissions, consent/purpose checks, sensitive-data masking, malicious payloads, audit logging, legal hold, retention, and export controls for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation. |
| Data tests | Source authority, referential integrity, historical correction, projection refresh, DWH/lakehouse extract, reporting metrics, and data-quality stewardship for product/offering/price/configuration/agreement catalog context. |
| Performance and resilience tests | Search, list, bulk import/export, queue throughput, API throughput, event replay, retry storm, downstream outage, and batch recovery under realistic telecom volumes. |
| Operational acceptance tests | Dashboards, alerts, runbooks, queue ownership, SLA/OLA reporting, reconciliation reports, and evidence export for commercial operations, catalog governance, pricing governance, and product lifecycle management. |

## Out Of Scope And Dependencies

- Pricing, Promotion, And Discount does not master entities assigned to another app in the data mastery document; it stores only its app-owned pricing, promotion, and discount state, transaction snapshots, references, projections, and evidence.
- Direct writes to another app database, reference database, external engine, payment gateway, tax engine, credit bureau, fraud provider, clearinghouse, ERP, network controller, or partner platform remain out of scope.
- Downstream execution by sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care owners remains with those apps; Pricing, Promotion, And Discount must track dependency state, retry status, and reconciliation evidence.
- Platform identity, authorization, policy, audit, notification, eventing, API gateway, workflow, reporting, data retention, and data residency capabilities must be available before production rollout.
- Any non-TMF extension API must be documented, reviewed by architecture, and tested alongside TMF Open API contracts before external exposure.

## Feature Detail Review Implementation Alignment (2026-06-14)

Source: [App Feature Detail Review Alignment](README.md#feature-detail-review-alignment-2026-06-14) and [Suite Feature Detail Review](../../feature-detail-review.md).

Apply this app review scope to this feature: catalog versioning, price and promotion governance, configuration validation, launch readiness, and agreement or terms control.

Implementation updates required for this feature:

- Re-check the core workflows and add or adjust happy paths, approval paths, exception queues, rollback or compensation behavior, and handoffs so the review scope is directly represented in build stories.
- Add or refine UI workbench expectations, including operator queues, evidence panels, policy decision traces, preview/simulation views, and status dashboards where this feature owns the behavior.
- Add or refine command APIs, query APIs, events, app-owned data fields, DDL gap notes, and integration handoffs needed to support the review scope without crossing app data ownership boundaries.
- Add acceptance criteria for source authority, tenant and residency controls, lifecycle state, approval evidence, idempotency, correlation IDs, SLA/OLA timers, and downstream acknowledgement where applicable.
- Add negative scenarios for stale data, duplicate events, policy denial, missing evidence, downstream outage, unauthorized access, bulk/replay risk, and manual override misuse.
- Extend tests to include happy path, negative path, edge case, API contract, event replay, data reconciliation, security, accessibility, observability, runbook, and release-gate evidence for the review scope.

## Build-Ready Refinement (2026-06-14)

This refinement converts the feature review material for Pricing, Promotion, And Discount into delivery slices that can become epics, stories, API contracts, migrations, and test cases. Treat Product And Offer Studio App as the owning application for this feature within Suite BSS Commercial and schema `product_offer_studio`.

| Workstream | Build-ready delivery guidance |
| --- | --- |
| UX and workflow | Build the Pricing, Promotion, And Discount workbench for Product manager, Pricing manager, Commercial operations user, Catalog governance user. Include search or intake, guided validation, detail view, lifecycle timeline, decision panel, evidence drawer, exception queue, bulk or replay controls where relevant, saved filters, SLA/OLA aging, empty/error states, and role-aware masking. The UI must expose create, validate, approve, correct, close, and audit pricing, promotion, and discount state and block closure when required evidence, approval, reconciliation, or downstream acknowledgement is missing. |
| API and events | Implement command and query APIs around pricing-promotion-and-discount using TMF671, TMF620. Command APIs for pricing, promotion, and discount must cover create/initiate, validate, update, approve/reject, hold/release, cancel, rollback or compensate where applicable, retry, correct, and close. Query APIs for pricing, promotion, and discount must cover search, detail, timeline, related product/offering/price/configuration/agreement catalog context references, dependency graph, work queue, metrics, and... Domain events for pricing, promotion, and discount must include created, validated, blocked, approved, rejected, updated, handoff requested, exception raised, exception resolved, cancelled, compensated, completed... Extension APIs are allowed only for launch readiness gates, test catalog certification, no-go/rollback decisioning, tax class mapping, revenue account mapping, grandfathering rules, and forced migration orchestration... Every command, query, and event must carry tenant/brand/market where applicable, actor, source channel, reason code, idempotency key, correlation ID, external reference, lifecycle state, and version metadata. |
| Data and controls | Persist pricing, promotion, and discount record inside `product_offer_studio` with typed lifecycle, owner, status reason, timestamps, policy decision, source freshness, confidence, old/new value, evidence, and reconciliation fields. Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls; other apps consume pricing... Keep TMF payloads, extension characteristics, imported evidence, and low-stability metadata in JSONB while promoting operationally searched lifecycle fields to typed columns. |
| Integration and handoff | Exchange not yet specified with the upstream and downstream owners named in the app README, modules-and-features, suite data model, TMF review, and DDL traceability files only through APIs, events, workflow tasks, governed projections, adapters, evidence packages, or certified data products. Show source owner, freshness, confidence, dependency state, retry status, blocked consumer, and completion evidence so the app does not create shadow mastership or direct cross-schema coupling. |
| Security, privacy, and compliance | Enforce RBAC/ABAC, tenant and residency boundaries, least privilege, separation of duties, masking, purpose limitation, retention, legal hold, export control, manual override expiry, immutable audit, and evidence chain of custody for Pricing, Promotion, And Discount. Sensitive customer, revenue, partner, security, network, credential, or regulatory evidence must be masked unless the persona has explicit operational purpose. |
| Tests and operations | Create unit, API contract, event replay/idempotency, workflow, integration, migration, data reconciliation, security/privacy, accessibility/localization, performance, dashboard, alert, and runbook tests for Pricing, Promotion, And Discount. Cover happy path, assisted path, automated path, exception path, bulk/project path, stale or duplicate input, downstream outage, policy denial, manual override, and reconciliation mismatch. Use the existing review scope - catalog versioning, price and promotion governance, configuration validation, launch readiness, and agreement or terms control. - as mandatory backlog and test evidence. |

Implementation notes:

- Treat Product And Offer Studio App as the lifecycle owner for pricing, promotion, and discount record; referenced data such as not yet specified must remain references, snapshots, projections, evidence packages, or consumer acknowledgements unless the source file explicitly gives this app mastership.
- Make TMF alignment visible in every story: use named TMF resources where they fit, document non-TMF extension APIs with OpenAPI, and keep extension payloads compatible with TMF-style identifiers, lifecycle state, related entities, pagination, errors, and event envelopes.
- Build UI and API behavior around decision evidence, not only CRUD: surface the permitted next actions, policy decision, state reason, owner, SLA/OLA timer, blocked dependency, retry or compensation path, and closure proof.
- Add development tasks for route/page/component work, command/query handlers, DTO validation, entity/repository/migration changes, outbox/event contracts, projection refresh, privacy/security checks, and operational dashboards.
- Definition-of-done evidence must show downstream consumers can use published state through APIs, events, projections, workflow tasks, or certified data products without direct database reads or manual spreadsheet reconciliation.

## Definition Of Done

1. Product owner has approved Pricing, Promotion, And Discount scope for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping with personas, decision rights, happy path, assisted path, automated path, partner/channel path, and back-office path covered.
2. Architecture owner has approved ODA boundaries, TMF671, TMF620 usage, extension API notes, event contracts, integration handoffs, and private app database assumptions for pricing, promotion, and discount.
3. QA owner has automated or explicitly documented acceptance, negative, edge, API, event, workflow, integration, security, privacy, data, performance, resilience, and regression tests for pricing, promotion, and discount.
4. Operations owner has dashboards, queues, alerts, runbooks, replay/reconciliation procedures, SLA/OLA measures, and ownership model ready for commercial operations, catalog governance, pricing governance, and product lifecycle management.
5. Data owner has confirmed source authority, app-owned fields, related entity references, projection/data-product behavior, lineage, retention, legal hold, and reporting measures for product/offering/price/configuration/agreement catalog context.
6. Compliance and security owners have approved tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation controls, evidence retention, masking, tenant/data-residency enforcement, and privileged-action review.
