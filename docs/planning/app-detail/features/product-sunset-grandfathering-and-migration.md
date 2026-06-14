# Product Sunset Grandfathering And Migration Feature Specification

Reviewed: 2026-06-07

Suite: BSS Commercial

App: [Product And Offer Studio](../README.md)

Source module detail: [Modules And Features](../modules-and-features.md)

Source gap review: [E2E Feature Gap Assessment](../../../e2e-feature-gap-assessment.md)

Feature area slug: `product-sunset-grandfathering-and-migration`

E2E gap severity: Critical

## Feature Intent

Control product retirement, grandfathering, forced migration, renewal, penalty, and customer communication rules across commercial and operational systems.

Product Sunset Grandfathering And Migration turns that intent into a controlled product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization capability: the app owns the product sunset grandfathering and migration lifecycle state, validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference, and leaves sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care consumers with auditable status rather than spreadsheet or direct-database workarounds.

## Personas Covered

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

## Persona-Specific Outcomes

| Persona | Decision rights and jobs-to-be-done | Feature outcome |
| --- | --- | --- |
| Product manager | Defines and approves product sunset grandfathering and migration rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Product manager can complete, approve, monitor, or audit product sunset grandfathering and migration with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Pricing manager | Defines and approves product sunset grandfathering and migration rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Pricing manager can complete, approve, monitor, or audit product sunset grandfathering and migration with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Commercial operations user | Defines and approves product sunset grandfathering and migration rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Commercial operations user can complete, approve, monitor, or audit product sunset grandfathering and migration with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |
| Catalog governance user | Defines and approves product sunset grandfathering and migration rules inside offer lifecycle, price/promotion approval, configuration rule, agreement term, launch readiness, tax, revenue, and regulatory filing decisions before publication to consuming channels. | Catalog governance user can complete, approve, monitor, or audit product sunset grandfathering and migration with product/offering/price/configuration/agreement catalog context state, sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff status, and immutable policy/evidence trail. |

## Core User Journeys Covered

| Step | User or system intent | Feature responsibility |
| ---: | --- | --- |
| 1 | Intake request, signal, or dependency from the upstream app, user, partner, event, or API consumer. | Product Sunset Grandfathering And Migration captures the intake and source authority for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records product sunset grandfathering and migration state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 2 | Validate eligibility, policy, commercial, operational, regulatory, and data-quality context. | Product Sunset Grandfathering And Migration validates eligibility, policy, and dependency state for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records product sunset grandfathering and migration state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 3 | Coordinate downstream tasks, events, notifications, and state transitions across the owning apps. | Product Sunset Grandfathering And Migration orchestrates owned lifecycle updates and downstream handoffs for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records product sunset grandfathering and migration state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 4 | Resolve exceptions, retries, approvals, compensation, or manual intervention. | Product Sunset Grandfathering And Migration routes fallout, approval, retry, cancellation, or compensation work for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records product sunset grandfathering and migration state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |
| 5 | Close the journey with reconciliation, evidence, reporting, and feedback into planning or operations. | Product Sunset Grandfathering And Migration publishes completion, reconciliation, and evidence events for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; it records product sunset grandfathering and migration state, correlation ID, source channel, owner, policy decision, and sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care handoff evidence. |

## Missing Use Cases And Scenarios

| Scenario | Required behavior |
| --- | --- |
| Happy path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: A product manager versions a product offering, pricing manager approves charge and discount structures, and commercial operations publishes the offer to sales, digital, partner, billing, and order channels. |
| Assisted path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: A catalog governance user blocks launch because service/resource realization, tax class, revenue account, or channel disclosure evidence is incomplete. |
| Automated path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: CPQ, digital commerce, and partner marketplace query the effective catalog version and receive eligibility, configuration, price, and contract-term references without local catalog writes. |
| Channel path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: Retail, dealer, self-care, and partner channels receive the same product offering version, eligibility window, price disclosure, and withdrawal rule. |
| Back-office path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: Pricing, tax, finance, and regulatory users review approval evidence, tariff filing status, revenue mapping, and launch/no-go decisions before effective date. |
| Sunset path | Product Sunset Grandfathering And Migration must support this path for product sunset grandfathering and migration: A product sunset or migration plan identifies active customer products, contract penalties, replacement offers, communication plan, and billing/order impacts before retirement. |

## Core Workflow And Control Points

| Control point | Required behavior | Evidence captured |
| --- | --- | --- |
| Trigger | Start product sunset grandfathering and migration from a product concept, price change, promotion, agreement update, launch readiness gate, sunset migration, channel publication request, or catalog API request with source channel, actor, tenant, customer/account/product/order references where applicable, and idempotency key. | Intake timestamp, source, actor, correlation ID, initiating record, and submitted payload hash. |
| Validation | Validate catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference before mutating product/offering/price/configuration/agreement catalog context state or handing work to another app. | Validation result, policy decision, source authority, missing fields, and permitted next action. |
| Orchestration | Coordinate Sales CPQ, Marketing, Order Management Hub, Service And Resource Design Studio, Billing, Usage/Charging, tax engines, finance/ERP, partner marketplace, self-care, and assurance readiness checks using APIs, events, workflow tasks, or governed projections while preserving app mastership: Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls. | Downstream owner, dependency state, request/response reference, retry counter, and event IDs. |
| Exception | Route product sunset grandfathering and migration fallout, policy failures, manual approvals, retries, rollback, compensation, and cancellation to accountable queues. | Queue owner, severity, due date, customer/revenue/compliance impact, reason code, comments, and evidence links. |
| Completion | Close product sunset grandfathering and migration only when owned lifecycle state, downstream handoffs, reconciliation, notifications, and reporting facts are complete or explicitly excepted. | Completion state, before/after values, reconciliation result, notification status, approver, and closure event. |
| Evidence | Preserve audit and regulatory evidence for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation with role-aware masking and retention/legal-hold controls. | Audit log, policy version, document/evidence reference, retention class, legal hold flag, and export controls. |

## Detailed Feature Backlog

| Feature ID | Feature | Parent feature area | Priority guidance |
| --- | --- | --- | --- |
| F-product-sunset-grandfathering-and-migration-01 | Sunset decision workflow | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when sunset decision workflow gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |
| F-product-sunset-grandfathering-and-migration-02 | Grandfathered eligibility rules | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when grandfathered eligibility rules gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |
| F-product-sunset-grandfathering-and-migration-03 | Forced migration plan | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when forced migration plan gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |
| F-product-sunset-grandfathering-and-migration-04 | Renewal and penalty rules | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when renewal and penalty rules gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |
| F-product-sunset-grandfathering-and-migration-05 | Customer communication trigger | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when customer communication trigger gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |
| F-product-sunset-grandfathering-and-migration-06 | Inventory and billing impact review | Product Sunset Grandfathering And Migration | P1: closes Critical E2E gap when inventory and billing impact review gates lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping; implementation must include API/event contract, exception queue, and evidence before pilot exit. |

## Acceptance Criteria

### Intake and ownership

Feature detail: Accept requests from UI, API, event, workflow, partner channel, or upstream app while assigning a clear owner and lifecycle state. For product sunset grandfathering and migration, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-product-sunset-grandfathering-and-migration-01-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete intake and ownership for product sunset grandfathering and migration, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-product-sunset-grandfathering-and-migration-01-02 Assisted path:** Given product sunset grandfathering and migration needs manual review, when a persona resolves missing data, approval, or policy conflict in intake and ownership, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-product-sunset-grandfathering-and-migration-01-03 Automated path:** Given an API consumer or event submits product sunset grandfathering and migration data for intake and ownership, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-product-sunset-grandfathering-and-migration-01-04 Exception path:** Given validation, downstream response, or compliance control fails during intake and ownership, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-product-sunset-grandfathering-and-migration-01-05 Completion evidence:** Given intake and ownership is ready to close for product sunset grandfathering and migration, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Validation and policy control

Feature detail: Validate required data, source authority, permissions, consent, regulatory policy, tenant/geography boundary, and dependency references. For product sunset grandfathering and migration, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-product-sunset-grandfathering-and-migration-02-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete validation and policy control for product sunset grandfathering and migration, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-product-sunset-grandfathering-and-migration-02-02 Assisted path:** Given product sunset grandfathering and migration needs manual review, when a persona resolves missing data, approval, or policy conflict in validation and policy control, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-product-sunset-grandfathering-and-migration-02-03 Automated path:** Given an API consumer or event submits product sunset grandfathering and migration data for validation and policy control, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-product-sunset-grandfathering-and-migration-02-04 Exception path:** Given validation, downstream response, or compliance control fails during validation and policy control, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-product-sunset-grandfathering-and-migration-02-05 Completion evidence:** Given validation and policy control is ready to close for product sunset grandfathering and migration, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Cross-app orchestration

Feature detail: Coordinate APIs, events, tasks, projections, notifications, and retry behavior with each downstream owner. For product sunset grandfathering and migration, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-product-sunset-grandfathering-and-migration-03-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete cross-app orchestration for product sunset grandfathering and migration, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-product-sunset-grandfathering-and-migration-03-02 Assisted path:** Given product sunset grandfathering and migration needs manual review, when a persona resolves missing data, approval, or policy conflict in cross-app orchestration, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-product-sunset-grandfathering-and-migration-03-03 Automated path:** Given an API consumer or event submits product sunset grandfathering and migration data for cross-app orchestration, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-product-sunset-grandfathering-and-migration-03-04 Exception path:** Given validation, downstream response, or compliance control fails during cross-app orchestration, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-product-sunset-grandfathering-and-migration-03-05 Completion evidence:** Given cross-app orchestration is ready to close for product sunset grandfathering and migration, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Exception and compensation

Feature detail: Route fallout, partial failure, rollback, cancellation, amendment, or compensation to accountable queues with evidence. For product sunset grandfathering and migration, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-product-sunset-grandfathering-and-migration-04-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete exception and compensation for product sunset grandfathering and migration, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-product-sunset-grandfathering-and-migration-04-02 Assisted path:** Given product sunset grandfathering and migration needs manual review, when a persona resolves missing data, approval, or policy conflict in exception and compensation, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-product-sunset-grandfathering-and-migration-04-03 Automated path:** Given an API consumer or event submits product sunset grandfathering and migration data for exception and compensation, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-product-sunset-grandfathering-and-migration-04-04 Exception path:** Given validation, downstream response, or compliance control fails during exception and compensation, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-product-sunset-grandfathering-and-migration-04-05 Completion evidence:** Given exception and compensation is ready to close for product sunset grandfathering and migration, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

### Reporting and closure

Feature detail: Close only after reconciliation, evidence capture, operational metrics, and downstream completion signals are available. For product sunset grandfathering and migration, this controls product/offering/price/configuration/agreement catalog context through product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization while respecting that Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls.

Acceptance criteria:

1. **AC-product-sunset-grandfathering-and-migration-05-01 Happy path:** Given a permitted Product manager has valid product/offering/price/configuration/agreement catalog context, when they complete reporting and closure for product sunset grandfathering and migration, then the app validates catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and stores the accepted lifecycle state with owner, timestamp, source channel, and correlation ID.
2. **AC-product-sunset-grandfathering-and-migration-05-02 Assisted path:** Given product sunset grandfathering and migration needs manual review, when a persona resolves missing data, approval, or policy conflict in reporting and closure, then the app shows the blocking sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency, captures comments/evidence, and resumes the same lifecycle instance without duplicate work.
3. **AC-product-sunset-grandfathering-and-migration-05-03 Automated path:** Given an API consumer or event submits product sunset grandfathering and migration data for reporting and closure, when the payload is valid and idempotent, then the app returns a contract-compliant state, emits the required event, and keeps read projections separate from app-owned writes.
4. **AC-product-sunset-grandfathering-and-migration-05-04 Exception path:** Given validation, downstream response, or compliance control fails during reporting and closure, when the exception is raised, then the app assigns an accountable queue with severity, due date, retry/rollback/compensation option, customer or revenue impact, and evidence requirements.
5. **AC-product-sunset-grandfathering-and-migration-05-05 Completion evidence:** Given reporting and closure is ready to close for product sunset grandfathering and migration, when downstream handoffs and reconciliation are complete, then the app records before/after values, approval or policy decision, related entity references, metrics, and evidence links for audit and reporting.

## Negative Scenarios

| Scenario | Expected behavior |
| --- | --- |
| Unauthorized product sunset grandfathering and migration access or mutation | Reject the request, mask product/offering/price/configuration/agreement catalog context data, and record actor, channel, tenant, policy decision, and correlation ID. |
| Missing mandatory product sunset grandfathering and migration context | Keep product sunset grandfathering and migration in draft, blocked, or rejected state with field-level errors for catalog version, effective date, eligibility, compatibility, price charge type, discount stack, promotion limit, tax/revenue mapping, regulatory filing evidence, and service/resource realization reference and do not publish downstream handoff events. |
| Invalid product sunset grandfathering and migration lifecycle transition | Block the transition, show allowed next states, preserve prior state/version, and require permitted role or automated policy to resubmit. |
| Conflicting master data for product sunset grandfathering and migration | Route correction to the owning app named by data mastery and prevent local shadow updates to customer, catalog, order, inventory, billing, usage, risk, or partner masters. |
| Downstream sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependency unavailable | Fail fast for synchronous decisions or queue controlled retry with owner, due date, backoff policy, and customer/revenue impact flag. |
| Duplicate, stale, or out-of-order product sunset grandfathering and migration request | Use optimistic locking, event version, source timestamp, and idempotency key so retries cannot duplicate work or corrupt current state. |
| Policy, consent, regulatory, or geography breach | Stop the transaction, preserve the policy decision, notify only permitted roles, and enforce tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation. |
| Manual override for product sunset grandfathering and migration | Require approval role, reason code, expiry, compensating action, post-action review, and searchable audit evidence. |
| Sensitive evidence requested for product sunset grandfathering and migration | Mask or deny restricted KYC, payment, fraud, complaint, usage, tax, or legal evidence while keeping operational task status visible. |
| Reconciliation mismatch after product sunset grandfathering and migration completion | Reopen or hold closure until sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care state agrees or an approved exception with finance/customer/compliance impact is recorded. |

## Edge Cases

| Edge case | Expected handling |
| --- | --- |
| Bulk or project-scale product sunset grandfathering and migration processing | Support validation preview, staged commit, partial failure report, throttling, replay, and rollback or repair plan before production release. |
| Long-running product sunset grandfathering and migration journey | Expose waiting, blocked, retrying, escalated, compensated, corrected, and completed states with timers, owners, and customer/revenue impact. |
| Historical product sunset grandfathering and migration correction | Allow effective-dated correction with reason, old/new values, approver, downstream recalculation trigger, and retention/legal-hold validation. |
| Multi-brand, multi-tenant, or data-residency boundary | Apply tenant, brand, market, geography, language, currency, and data-residency controls consistently in UI, API, event, and reporting paths. |
| High-volume operational period for product sunset grandfathering and migration | Protect critical flows with pagination, async export, queue back-pressure, circuit breakers, dashboard filters, and runbook-defined load-shedding. |
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
| High | Product lifecycle impact simulator for launch, price change, and retirement. | Add concrete happy path, negative path, edge-case, API/event/data control, reporting, and test evidence for this feature area. |
| Medium | Grandfathered-product MACD eligibility rules. | Add concrete happy path, negative path, edge-case, API/event/data control, reporting, and test evidence for this feature area. |

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

Related APIs and API areas: [TMF620](../../../../../references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog), [TMF760](../../../../../references/tmforum-open-apis/openapi-specs/TMF760_ProductConfigurationManagement), [TMF651](../../../../../references/tmforum-open-apis/openapi-specs/TMF651_AgreementManagement), [TMF637](../../../../../references/tmforum-open-apis/openapi-specs/TMF637_ProductInventory), [TMF681](../../../../../references/tmforum-open-apis/openapi-specs/TMF681_Communication)

TMF API fit and extension notes:

- Use TMF620, TMF760, TMF651, TMF637, TMF681 for the TMF resource areas already identified in this feature specification; do not replace those resources with local-only contracts when the TMF API covers the lifecycle or query behavior.
- Extension APIs are allowed only for launch readiness gates, test catalog certification, no-go/rollback decisioning, tax class mapping, revenue account mapping, grandfathering rules, and forced migration orchestration where no direct TMF resource exists; each extension must be explicitly labelled non-TMF, documented with OpenAPI, and aligned to TMF-style id, href, lifecycle state, relatedParty, relatedEntity, error, pagination, and event-envelope patterns where practical.
- Command APIs for product sunset grandfathering and migration must cover create/initiate, validate, update, approve/reject, hold/release, cancel, rollback or compensate where applicable, retry, correct, and close.
- Query APIs for product sunset grandfathering and migration must cover search, detail, timeline, related product/offering/price/configuration/agreement catalog context references, dependency graph, work queue, metrics, and audit/evidence retrieval with role-aware masking.
- Domain events for product sunset grandfathering and migration must include created, validated, blocked, approved, rejected, updated, handoff requested, exception raised, exception resolved, cancelled, compensated, completed, corrected, and reconciliation failed where the lifecycle uses those states.

Data and ownership requirements:

- Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls; other apps consume product sunset grandfathering and migration state through APIs, events, governed projections, workflow tasks, or certified data products.
- Store source channel, actor, tenant/brand/market, external references, status reason, timestamps, policy decision, before/after values, related customer/account/product/order/bill/usage/ticket references where applicable, and evidence links.
- Keep read projections, analytics extracts, and DWH/lakehouse outputs separate from operational writes so Product Sunset Grandfathering And Migration does not create shadow mastership.
- Provide reconciliation outputs that prove sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care dependencies have completed, failed, or remain explicitly owned.

Integration and handoff requirements:

- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Sales CPQ through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Marketing through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Order Management Hub through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Service And Resource Design Studio through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Billing through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with Usage/Charging through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with tax engines through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with finance/ERP through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with partner marketplace through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with self-care through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.
- Product Sunset Grandfathering And Migration must exchange product sunset grandfathering and migration state or evidence with assurance readiness checks through APIs, events, workflow tasks, files, or governed projections as appropriate to that owner.

## Non-Functional Requirements

- Scale and latency: catalog search P95 below 500 ms, offer eligibility rule response P95 below 300 ms for CPQ paths, 99.9% catalog API availability during selling hours, versioned publication with rollback, and immutable audit for prices and agreement terms.
- Availability and resilience: Product Sunset Grandfathering And Migration must support 99.9% or higher availability for interactive and API paths that gate lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping, with queue back-pressure, retry, replay, and circuit-breaker controls for downstream integrations.
- Auditability and retention: product sunset grandfathering and migration history must preserve actor, channel, reason, old/new value, policy version, approval, event ID, external reference, and retention/legal-hold class for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation.
- Localization and accessibility: Product Sunset Grandfathering And Migration user tasks, customer/partner communications, currency/date formats, invoice or offer disclosures where applicable, and error messages must support market localization, WCAG-aligned accessibility, and role-aware data masking.
- Data protection: API, event, export, and dashboard paths must enforce tenant isolation, data residency, purpose limitation, least privilege, field-level masking, and secure evidence storage for product/offering/price/configuration/agreement catalog context.

## Compliance, Security, And Privacy

- Product Sunset Grandfathering And Migration must enforce tariff filing for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce advertised price controls for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce tax jurisdiction mapping for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce revenue code mapping for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce contract term evidence for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce accessibility of offer disclosures for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce approval audit for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce retention for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce data residency for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Product Sunset Grandfathering And Migration must enforce tenant isolation for product sunset grandfathering and migration records, UI actions, API payloads, events, reports, and evidence exports.
- Privileged actions on product sunset grandfathering and migration require role-based approval, reason code, expiration where relevant, and post-action review by commercial operations, catalog governance, pricing governance, and product lifecycle management.
- Sensitive product/offering/price/configuration/agreement catalog context evidence must be masked in search, timelines, exports, analytics, partner views, and operational dashboards unless the persona has a permitted purpose.

## Observability And Operations

- Metrics: track product sunset grandfathering and migration intake volume, validation failure rate, policy rejection rate, automation rate, manual override rate, queue aging, retry count, cancellation/rollback/compensation count, reconciliation mismatch, and completion quality by tenant, market, channel, product, partner, and owning team.
- Queues: provide work queues for draft, pending validation, pending approval, blocked dependency, exception, retrying, customer-impacting, revenue-impacting, compliance-impacting, compensated, corrected, completed, and archived product sunset grandfathering and migration records.
- Alerts: alert commercial operations, catalog governance, pricing governance, and product lifecycle management when product sunset grandfathering and migration queue aging, downstream failure, event publication failure, reconciliation mismatch, abnormal policy override, or SLA/OLA breach risk exceeds threshold.
- Runbooks: document triage, retry, replay, rollback, compensation, manual approval, customer/partner communication, evidence export, and reconciliation steps for Product Sunset Grandfathering And Migration.
- Replay and reconciliation: support idempotent replay for events, files, callbacks, and workflow tasks so Product Sunset Grandfathering And Migration can recover without duplicate product/offering/price/configuration/agreement catalog context state or lost audit history.
- Ownership: commercial operations, catalog governance, pricing governance, and product lifecycle management owns first-line operational health; architecture, data, security, and compliance teams own policy and conformance review for the product sunset grandfathering and migration lifecycle.

## Test Approach

| Test layer | Required coverage |
| --- | --- |
| Unit tests | Field rules, lifecycle transitions, policy decisions, duplicate detection, effective dating, masking, and product/offering/price/configuration/agreement catalog context state calculations for product sunset grandfathering and migration. |
| API contract tests | Commands, queries, errors, idempotency, pagination, filtering, version compatibility, and TMF-aligned payloads for TMF620, TMF760, TMF651, TMF637, TMF681 plus documented extension APIs. |
| Event contract tests | product sunset grandfathering and migration event names, payload shape, changed fields, correlation ID, idempotency key, ordering metadata, replay behavior, and subscriber compatibility. |
| Workflow tests | Happy path, assisted path, automated path, partner/channel path, approval, exception, timeout, retry, cancellation, rollback, compensation, correction, and closure for product concept to launch, lead-to-order readiness, offer sunset, and commercial-to-technical realization. |
| Integration tests | Handoffs with sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care owners, external provider unavailability, eventual consistency, reconciliation, and no direct database access. |
| Security and privacy tests | Tenant isolation, role permissions, consent/purpose checks, sensitive-data masking, malicious payloads, audit logging, legal hold, retention, and export controls for tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation. |
| Data tests | Source authority, referential integrity, historical correction, projection refresh, DWH/lakehouse extract, reporting metrics, and data-quality stewardship for product/offering/price/configuration/agreement catalog context. |
| Performance and resilience tests | Search, list, bulk import/export, queue throughput, API throughput, event replay, retry storm, downstream outage, and batch recovery under realistic telecom volumes. |
| Operational acceptance tests | Dashboards, alerts, runbooks, queue ownership, SLA/OLA reporting, reconciliation reports, and evidence export for commercial operations, catalog governance, pricing governance, and product lifecycle management. |

## Out Of Scope And Dependencies

- Product Sunset Grandfathering And Migration does not master entities assigned to another app in the data mastery document; it stores only its app-owned product sunset grandfathering and migration state, transaction snapshots, references, projections, and evidence.
- Direct writes to another app database, reference database, external engine, payment gateway, tax engine, credit bureau, fraud provider, clearinghouse, ERP, network controller, or partner platform remain out of scope.
- Downstream execution by sales, marketing, order, OSS design, billing, charging, tax, finance, partner, and self-care owners remains with those apps; Product Sunset Grandfathering And Migration must track dependency state, retry status, and reconciliation evidence.
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

This refinement converts the feature review material for Product Sunset Grandfathering And Migration into delivery slices that can become epics, stories, API contracts, migrations, and test cases. Treat Product And Offer Studio as the owning application for this feature within Suite BSS Commercial and schema `product_offer_studio`.

| Workstream | Build-ready delivery guidance |
| --- | --- |
| UX and workflow | Build the Product Sunset Grandfathering And Migration workbench for Product manager, Pricing manager, Commercial operations user, Catalog governance user. Include search or intake, guided validation, detail view, lifecycle timeline, decision panel, evidence drawer, exception queue, bulk or replay controls where relevant, saved filters, SLA/OLA aging, empty/error states, and role-aware masking. The UI must expose create, validate, approve, correct, close, and audit product sunset grandfathering and migration state and block closure when required evidence, approval, reconciliation, or downstream acknowledgement is missing. |
| API and events | Implement command and query APIs around product-sunset-grandfathering-and-migration using TMF620, TMF760, TMF651, TMF637, TMF681. Command APIs for product sunset grandfathering and migration must cover create/initiate, validate, update, approve/reject, hold/release, cancel, rollback or compensate where applicable, retry, correct, and close. Query APIs for product sunset grandfathering and migration must cover search, detail, timeline, related product/offering/price/configuration/agreement catalog context references, dependency graph, work queue, metrics... Domain events for product sunset grandfathering and migration must include created, validated, blocked, approved, rejected, updated, handoff requested, exception raised, exception resolved, cancelled, compensated... Extension APIs are allowed only for launch readiness gates, test catalog certification, no-go/rollback decisioning, tax class mapping, revenue account mapping, grandfathering rules, and forced migration orchestration... Every command, query, and event must carry tenant/brand/market where applicable, actor, source channel, reason code, idempotency key, correlation ID, external reference, lifecycle state, and version metadata. |
| Data and controls | Persist product sunset grandfathering and migration record inside `product_offer_studio` with typed lifecycle, owner, status reason, timestamps, policy decision, source freshness, confidence, old/new value, evidence, and reconciliation fields. Product And Offer Studio remains master for commercial product specifications, offerings, bundles, prices, promotions, discounts, product configuration models, agreement templates, and launch/sunset controls; other apps consume product... Keep TMF payloads, extension characteristics, imported evidence, and low-stability metadata in JSONB while promoting operationally searched lifecycle fields to typed columns. |
| Integration and handoff | Exchange not yet specified with the upstream and downstream owners named in the app README, modules-and-features, suite data model, TMF review, and DDL traceability files only through APIs, events, workflow tasks, governed projections, adapters, evidence packages, or certified data products. Show source owner, freshness, confidence, dependency state, retry status, blocked consumer, and completion evidence so the app does not create shadow mastership or direct cross-schema coupling. |
| Security, privacy, and compliance | Enforce RBAC/ABAC, tenant and residency boundaries, least privilege, separation of duties, masking, purpose limitation, retention, legal hold, export control, manual override expiry, immutable audit, and evidence chain of custody for Product Sunset Grandfathering And Migration. Sensitive customer, revenue, partner, security, network, credential, or regulatory evidence must be masked unless the persona has explicit operational purpose. |
| Tests and operations | Create unit, API contract, event replay/idempotency, workflow, integration, migration, data reconciliation, security/privacy, accessibility/localization, performance, dashboard, alert, and runbook tests for Product Sunset Grandfathering And Migration. Cover happy path, assisted path, automated path, exception path, bulk/project path, stale or duplicate input, downstream outage, policy denial, manual override, and reconciliation mismatch. Use the existing review scope - catalog versioning, price and promotion governance, configuration validation, launch readiness, and agreement or terms control. - as mandatory backlog and test evidence. |

Implementation notes:

- Treat Product And Offer Studio as the lifecycle owner for product sunset grandfathering and migration record; referenced data such as not yet specified must remain references, snapshots, projections, evidence packages, or consumer acknowledgements unless the source file explicitly gives this app mastership.
- Make TMF alignment visible in every story: use named TMF resources where they fit, document non-TMF extension APIs with OpenAPI, and keep extension payloads compatible with TMF-style identifiers, lifecycle state, related entities, pagination, errors, and event envelopes.
- Build UI and API behavior around decision evidence, not only CRUD: surface the permitted next actions, policy decision, state reason, owner, SLA/OLA timer, blocked dependency, retry or compensation path, and closure proof.
- Add development tasks for route/page/component work, command/query handlers, DTO validation, entity/repository/migration changes, outbox/event contracts, projection refresh, privacy/security checks, and operational dashboards.
- Definition-of-done evidence must show downstream consumers can use published state through APIs, events, projections, workflow tasks, or certified data products without direct database reads or manual spreadsheet reconciliation.

## Definition Of Done

1. Product owner has approved Product Sunset Grandfathering And Migration scope for lead-to-order offer readiness, order-to-activate catalog handoff, and govern-to-comply tariff, tax, and revenue mapping with personas, decision rights, happy path, assisted path, automated path, partner/channel path, and back-office path covered.
2. Architecture owner has approved ODA boundaries, TMF620, TMF760, TMF651, TMF637, TMF681 usage, extension API notes, event contracts, integration handoffs, and private app database assumptions for product sunset grandfathering and migration.
3. QA owner has automated or explicitly documented acceptance, negative, edge, API, event, workflow, integration, security, privacy, data, performance, resilience, and regression tests for product sunset grandfathering and migration.
4. Operations owner has dashboards, queues, alerts, runbooks, replay/reconciliation procedures, SLA/OLA measures, and ownership model ready for commercial operations, catalog governance, pricing governance, and product lifecycle management.
5. Data owner has confirmed source authority, app-owned fields, related entity references, projection/data-product behavior, lineage, retention, legal hold, and reporting measures for product/offering/price/configuration/agreement catalog context.
6. Compliance and security owners have approved tariff filing, advertised price controls, tax jurisdiction mapping, revenue code mapping, contract term evidence, accessibility of offer disclosures, approval audit, retention, data residency, and tenant isolation controls, evidence retention, masking, tenant/data-residency enforcement, and privileged-action review.
