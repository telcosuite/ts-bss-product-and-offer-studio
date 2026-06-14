# Product And Offer Studio App Modules And Features

Reviewed: 2026-06-06

This document expands each app module into feature-level planning guidance. It should be used to create epics, stories, API contracts, event contracts, screens, permissions, and test cases.

Source overview: [product-and-offer-studio.md](../product-and-offer-studio.md)

## App-Level Feature Principles

- Every feature must have an owning module and an owning app API.
- UI actions must call app APIs rather than writing directly to shared data stores.
- Cross-app reads should use APIs, subscribed events, governed projections, or data products.
- Each module should expose enough lifecycle state for operations, audit, automation, and customer/partner visibility.
- Feature design must include happy path, exception path, audit path, and reporting path.

## App Data Ownership Context

Owns commercial product models, product offerings, bundles, price definitions, promotion definitions, product configuration models, agreement templates, catalog release state, and catalog governance evidence.

## First Release Context

Deliver product/offering catalog, price and promotion model, configuration constraints, catalog approval, and publication APIs. Add richer commercial simulation, offer experiments, and automated catalog test certification later.

## Module 1: Product Catalog

Anchor: `product-catalog`

### Capability Intent

Manage product specs, offerings, bundles, categories, lifecycle, versioning, characteristics, relationships, constraints, effective dates, retirement, and commercial metadata.

### Primary Personas Supported

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

### Feature Backlog Candidates

- Manage product specs.
- Characteristics.
- Relationships.
- Effective dates.
- And commercial metadata.

### Feature Groups

| Feature group | Feature detail |
| --- | --- |
| Record and lifecycle management | Create, search, view, update, retire, reinstate, and track lifecycle state for product catalog records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. |
| Validation, policy, and eligibility | Validate product catalog changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. |
| Work queues and approvals | Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. |
| Search, timeline, and operational views | Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for product catalog work. |
| API and event behavior | Expose command, query, and event contracts for product catalog so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. |
| Audit, evidence, and reporting | Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. |

### User Journey Coverage

| Journey | Trigger | App behavior | Successful outcome |
| --- | --- | --- | --- |
| Maintain Product Catalog | User creates or updates domain information | Validate context, capture change, publish event, update projections | Accurate product catalog state available through APIs |
| Handle Product Catalog exception | Conflict, validation failure, policy exception, fallout, or missing dependency | Route to owner, capture evidence, resolve or escalate, notify dependent work | Exception closed with auditable reason and downstream handoff |
| Review Product Catalog performance | Supervisor, planner, compliance, or operations user needs visibility | Filter records, inspect trend, export/report, create follow-up task | Actionable operational insight and accountable next step |

### API And Integration Alignment

Related APIs and API areas: [TMF620](../../../../references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog)

Implementation guidance:

- Provide create, read, update, lifecycle transition, search, event notification, and audit retrieval behavior where the domain lifecycle requires it.
- Publish domain events for state changes that other apps need for projections, workflow triggers, analytics, or customer/partner communication.
- Keep integration retries, idempotency keys, correlation IDs, and external reference IDs visible to operators.

### Data, Control, And Reporting Needs

- Store app-owned operational records in the app's logical database defined in the database setup document.
- Store external IDs, source channel, owner, status reason, timestamps, and relationship references needed for traceability.
- Provide operational metrics for volume, aging, fallout, SLA/OLA status, exception rate, policy overrides, and automation success.
- Support role-based access, tenant/region boundaries, sensitive-data masking, and export controls where applicable.

### First Release Interpretation

For the first release, implement the minimum lifecycle, search, validation, API, event, audit, and operational queue behavior needed for this module to participate in the app's core workflow. Advanced automation, AI assistance, bulk optimization, simulation, and deep analytics can follow after the app proves the core operating loop.

## Module 2: Pricing, Promotion, And Discount

Anchor: `pricing-promotion-and-discount`

### Capability Intent

Manage recurring, one-time, usage, deposit, penalty, device, installation, and discount prices. Define promotions, eligibility, validity, approval rules, and price override controls.

### Primary Personas Supported

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

### Feature Backlog Candidates

- Manage recurring.
- Installation.
- And discount prices.
- Define promotions.
- Approval rules.
- And price override controls.

### Feature Groups

| Feature group | Feature detail |
| --- | --- |
| Record and lifecycle management | Create, search, view, update, retire, reinstate, and track lifecycle state for pricing, promotion, and discount records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. |
| Validation, policy, and eligibility | Validate pricing, promotion, and discount changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. |
| Work queues and approvals | Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. |
| Search, timeline, and operational views | Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for pricing, promotion, and discount work. |
| API and event behavior | Expose command, query, and event contracts for pricing, promotion, and discount so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. |
| Audit, evidence, and reporting | Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. |

### User Journey Coverage

| Journey | Trigger | App behavior | Successful outcome |
| --- | --- | --- | --- |
| Maintain Pricing, Promotion, And Discount | User creates or updates domain information | Validate context, capture change, publish event, update projections | Accurate pricing, promotion, and discount state available through APIs |
| Handle Pricing, Promotion, And Discount exception | Conflict, validation failure, policy exception, fallout, or missing dependency | Route to owner, capture evidence, resolve or escalate, notify dependent work | Exception closed with auditable reason and downstream handoff |
| Review Pricing, Promotion, And Discount performance | Supervisor, planner, compliance, or operations user needs visibility | Filter records, inspect trend, export/report, create follow-up task | Actionable operational insight and accountable next step |

### API And Integration Alignment

Related APIs and API areas: [TMF671](../../../../references/tmforum-open-apis/openapi-specs/TMF671_Promotion), [TMF620](../../../../references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog)

Implementation guidance:

- Provide create, read, update, lifecycle transition, search, event notification, and audit retrieval behavior where the domain lifecycle requires it.
- Publish domain events for state changes that other apps need for projections, workflow triggers, analytics, or customer/partner communication.
- Keep integration retries, idempotency keys, correlation IDs, and external reference IDs visible to operators.

### Data, Control, And Reporting Needs

- Store app-owned operational records in the app's logical database defined in the database setup document.
- Store external IDs, source channel, owner, status reason, timestamps, and relationship references needed for traceability.
- Provide operational metrics for volume, aging, fallout, SLA/OLA status, exception rate, policy overrides, and automation success.
- Support role-based access, tenant/region boundaries, sensitive-data masking, and export controls where applicable.

### First Release Interpretation

For the first release, implement the minimum lifecycle, search, validation, API, event, audit, and operational queue behavior needed for this module to participate in the app's core workflow. Advanced automation, AI assistance, bulk optimization, simulation, and deep analytics can follow after the app proves the core operating loop.

## Module 3: Product Configuration

Anchor: `product-configuration`

### Capability Intent

Define configurable options, default configurations, compatibility rules, product constraints, guided selling, quote/cart/order validation, and service/resource design links.

### Primary Personas Supported

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

### Feature Backlog Candidates

- Define configurable options.
- Default configurations.
- Compatibility rules.
- Product constraints.
- Guided selling.
- Quote/cart/order validation.
- And service/resource design links.

### Feature Groups

| Feature group | Feature detail |
| --- | --- |
| Record and lifecycle management | Create, search, view, update, retire, reinstate, and track lifecycle state for product configuration records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. |
| Validation, policy, and eligibility | Validate product configuration changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. |
| Work queues and approvals | Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. |
| Search, timeline, and operational views | Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for product configuration work. |
| API and event behavior | Expose command, query, and event contracts for product configuration so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. |
| Audit, evidence, and reporting | Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. |

### User Journey Coverage

| Journey | Trigger | App behavior | Successful outcome |
| --- | --- | --- | --- |
| Maintain Product Configuration | User creates or updates domain information | Validate context, capture change, publish event, update projections | Accurate product configuration state available through APIs |
| Handle Product Configuration exception | Conflict, validation failure, policy exception, fallout, or missing dependency | Route to owner, capture evidence, resolve or escalate, notify dependent work | Exception closed with auditable reason and downstream handoff |
| Review Product Configuration performance | Supervisor, planner, compliance, or operations user needs visibility | Filter records, inspect trend, export/report, create follow-up task | Actionable operational insight and accountable next step |

### API And Integration Alignment

Related APIs and API areas: [TMF760](../../../../references/tmforum-open-apis/openapi-specs/TMF760_ProductConfigurationManagement)

Implementation guidance:

- Provide create, read, update, lifecycle transition, search, event notification, and audit retrieval behavior where the domain lifecycle requires it.
- Publish domain events for state changes that other apps need for projections, workflow triggers, analytics, or customer/partner communication.
- Keep integration retries, idempotency keys, correlation IDs, and external reference IDs visible to operators.

### Data, Control, And Reporting Needs

- Store app-owned operational records in the app's logical database defined in the database setup document.
- Store external IDs, source channel, owner, status reason, timestamps, and relationship references needed for traceability.
- Provide operational metrics for volume, aging, fallout, SLA/OLA status, exception rate, policy overrides, and automation success.
- Support role-based access, tenant/region boundaries, sensitive-data masking, and export controls where applicable.

### First Release Interpretation

For the first release, implement the minimum lifecycle, search, validation, API, event, audit, and operational queue behavior needed for this module to participate in the app's core workflow. Advanced automation, AI assistance, bulk optimization, simulation, and deep analytics can follow after the app proves the core operating loop.

## Module 4: Agreement And Contract

Anchor: `agreement-and-contract`

### Capability Intent

Manage agreements, master service agreements, contract terms, commitments, penalties, renewals, entitlements, enterprise child agreements, and links to quotes/orders/bills.

### Primary Personas Supported

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

### Feature Backlog Candidates

- Manage agreements.
- Master service agreements.
- Contract terms.
- Entitlements.
- Enterprise child agreements.
- And links to quotes/orders/bills.

### Feature Groups

| Feature group | Feature detail |
| --- | --- |
| Record and lifecycle management | Create, search, view, update, retire, reinstate, and track lifecycle state for agreement and contract records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. |
| Validation, policy, and eligibility | Validate agreement and contract changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. |
| Work queues and approvals | Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. |
| Search, timeline, and operational views | Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for agreement and contract work. |
| API and event behavior | Expose command, query, and event contracts for agreement and contract so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. |
| Audit, evidence, and reporting | Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. |

### User Journey Coverage

| Journey | Trigger | App behavior | Successful outcome |
| --- | --- | --- | --- |
| Maintain Agreement And Contract | User creates or updates domain information | Validate context, capture change, publish event, update projections | Accurate agreement and contract state available through APIs |
| Handle Agreement And Contract exception | Conflict, validation failure, policy exception, fallout, or missing dependency | Route to owner, capture evidence, resolve or escalate, notify dependent work | Exception closed with auditable reason and downstream handoff |
| Review Agreement And Contract performance | Supervisor, planner, compliance, or operations user needs visibility | Filter records, inspect trend, export/report, create follow-up task | Actionable operational insight and accountable next step |

### API And Integration Alignment

Related APIs and API areas: [TMF651](../../../../references/tmforum-open-apis/openapi-specs/TMF651_AgreementManagement)

Implementation guidance:

- Provide create, read, update, lifecycle transition, search, event notification, and audit retrieval behavior where the domain lifecycle requires it.
- Publish domain events for state changes that other apps need for projections, workflow triggers, analytics, or customer/partner communication.
- Keep integration retries, idempotency keys, correlation IDs, and external reference IDs visible to operators.

### Data, Control, And Reporting Needs

- Store app-owned operational records in the app's logical database defined in the database setup document.
- Store external IDs, source channel, owner, status reason, timestamps, and relationship references needed for traceability.
- Provide operational metrics for volume, aging, fallout, SLA/OLA status, exception rate, policy overrides, and automation success.
- Support role-based access, tenant/region boundaries, sensitive-data masking, and export controls where applicable.

### First Release Interpretation

For the first release, implement the minimum lifecycle, search, validation, API, event, audit, and operational queue behavior needed for this module to participate in the app's core workflow. Advanced automation, AI assistance, bulk optimization, simulation, and deep analytics can follow after the app proves the core operating loop.

## Module 5: Catalog Governance

Anchor: `catalog-governance`

### Capability Intent

Manage catalog workflows, approvals, testing, release windows, publication channels, dependency validation, service/resource spec mapping, and retirement readiness.

### Primary Personas Supported

- Product manager: defines offers, bundles, eligibility, lifecycle, and launch plans.
- Pricing manager: owns recurring, usage, one-time, penalty, device, discount, and promotional price structures.
- Commercial operations user: governs release windows, approvals, and channel publication.
- Catalog governance user: checks product-to-service/resource realization and launch readiness.

### Feature Backlog Candidates

- Manage catalog workflows.
- Release windows.
- Publication channels.
- Dependency validation.
- Service/resource spec mapping.
- And retirement readiness.

### Feature Groups

| Feature group | Feature detail |
| --- | --- |
| Record and lifecycle management | Create, search, view, update, retire, reinstate, and track lifecycle state for catalog governance records. Maintain ownership, status reason, timestamps, and relationships to upstream and downstream entities. |
| Validation, policy, and eligibility | Validate catalog governance changes against catalog rules, customer/account context, serviceability, inventory state, compliance policy, role permissions, and data-quality constraints relevant to this app. |
| Work queues and approvals | Provide queues for draft, pending approval, blocked, exception, fallout, rejected, completed, and archived work. Support assignment, SLA/OLA tracking, escalation, comments, and handoff. |
| Search, timeline, and operational views | Offer filtered search, saved views, dependency views, lifecycle timeline, related orders/tickets/events, and persona-specific dashboards for catalog governance work. |
| API and event behavior | Expose command, query, and event contracts for catalog governance so UIs, workflows, partner channels, analytics, and downstream apps do not bypass the owning app. |
| Audit, evidence, and reporting | Capture actor, reason, before/after state, source channel, approval evidence, policy decisions, and reporting measures needed for operations, compliance, and continuous improvement. |

### User Journey Coverage

| Journey | Trigger | App behavior | Successful outcome |
| --- | --- | --- | --- |
| Maintain Catalog Governance | User creates or updates domain information | Validate context, capture change, publish event, update projections | Accurate catalog governance state available through APIs |
| Handle Catalog Governance exception | Conflict, validation failure, policy exception, fallout, or missing dependency | Route to owner, capture evidence, resolve or escalate, notify dependent work | Exception closed with auditable reason and downstream handoff |
| Review Catalog Governance performance | Supervisor, planner, compliance, or operations user needs visibility | Filter records, inspect trend, export/report, create follow-up task | Actionable operational insight and accountable next step |

### API And Integration Alignment

Related APIs and API areas: [TMF620](../../../../references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog), [TMF633](../../../../references/tmforum-open-apis/openapi-specs/TMF633_ServiceCatalog), [TMF634](../../../../references/tmforum-open-apis/openapi-specs/TMF634_ResourceCatalog)

Implementation guidance:

- Provide create, read, update, lifecycle transition, search, event notification, and audit retrieval behavior where the domain lifecycle requires it.
- Publish domain events for state changes that other apps need for projections, workflow triggers, analytics, or customer/partner communication.
- Keep integration retries, idempotency keys, correlation IDs, and external reference IDs visible to operators.

### Data, Control, And Reporting Needs

- Store app-owned operational records in the app's logical database defined in the database setup document.
- Store external IDs, source channel, owner, status reason, timestamps, and relationship references needed for traceability.
- Provide operational metrics for volume, aging, fallout, SLA/OLA status, exception rate, policy overrides, and automation success.
- Support role-based access, tenant/region boundaries, sensitive-data masking, and export controls where applicable.

### First Release Interpretation

For the first release, implement the minimum lifecycle, search, validation, API, event, audit, and operational queue behavior needed for this module to participate in the app's core workflow. Advanced automation, AI assistance, bulk optimization, simulation, and deep analytics can follow after the app proves the core operating loop.

## Critical Feature Review Enhancements (2026-06-14)

### Critical Assessment

The baseline catalog modules are correct, but implementation needs stronger product governance. This app must control catalog versions, sellability, pricing, promotion eligibility, configuration validity, agreement terms, launch readiness, and rollback so CPQ/order/billing do not invent their own commercial rules.

### Enhancements To Add

| Enhancement | Modules | Implementation need |
| --- | --- | --- |
| Catalog version and release workspace | Product Catalog; Catalog Governance | Manage draft, review, approved, active, retired, superseded, and rollback catalog versions with effective dates, markets, brands, channels, and dependency impact. |
| Offer readiness checklist | Product Catalog; Pricing, Promotion, And Discount; Agreement And Contract | Require price, tax category, eligibility, configuration model, terms, fulfillment mapping, billing/charging mapping, channel availability, and serviceability dependencies before launch. |
| Price and promotion governance | Pricing, Promotion, And Discount | Validate stacking rules, discount authority, margin guardrails, effective dates, customer segment eligibility, channel rules, and approval evidence. |
| Configuration model workbench | Product Configuration | Maintain configurable characteristics, compatibility rules, option dependencies, defaulting rules, validation responses, and CPQ error messages. |
| Commercial terms and agreement library | Agreement And Contract | Version agreement templates, commitment terms, penalties, renewal, cancellation, regulatory clauses, and partner/channel terms. |
| Catalog impact analysis | Catalog Governance | Show which quotes, carts, campaigns, orders, billing mappings, charging mappings, partners, and markets are affected by a catalog change. |
| Fulfillment and billing mapping readiness | Catalog Governance | Link product offering/specification to service/resource candidates, order decomposition hints, bill item mapping, rating/charging references, and settlement rules. |

### Required Screens

| Screen | Required behavior |
| --- | --- |
| Catalog release board | Version status, launch blockers, owner, approval aging, impacted channels, and rollback plan. |
| Offer builder | Product, price, promotion, eligibility, configuration, terms, fulfillment, billing, and channel tabs in one governed flow. |
| Pricing and promotion guardrail view | Discount limits, stacking, margin, segment/channel eligibility, approval trail, and effective-date conflict warnings. |
| Impact analysis panel | Affected offers, quotes, carts, campaigns, billing/charging mappings, partners, and markets before activation. |

### Open-Source Decision Points

| Need | Candidate options | Decision prompt |
| --- | --- | --- |
| Rules and configuration validation | Spring/PostgreSQL rules; Drools/Kogito; lightweight JSON rule model | Ask before adding a rules engine; use one only if offer/configuration rules need business-owned authoring. |
| Catalog search | PostgreSQL full-text; OpenSearch | Start with PostgreSQL; add search engine only if catalog size and fuzzy discovery demand it. |
| Document/template storage | PostgreSQL metadata plus object adapter; MinIO | Ask before storing large agreement templates or attachments outside PostgreSQL. |

### API/Event/Data Additions

| Area | Additions |
| --- | --- |
| APIs | Catalog version clone/approve/activate/retire, offer readiness validate, price guardrail evaluate, configuration validate, launch impact analysis, rollback candidate. |
| Events | `CatalogVersionApproved`, `ProductOfferingLaunched`, `ProductOfferingRetired`, `PriceChanged`, `PromotionChanged`, `ConfigurationModelChanged`, `OfferReadinessBlocked`. |
| Data | Product/offer/price/promotion/term versions are mastered here; sales and order apps must snapshot exact versions at transaction time. |

### First Release Scope

Include catalog versioning, offer builder, readiness checklist, price/promotion guardrails, configuration validation, and catalog activation events. Defer complex product lifecycle analytics and visual bundle modeling until CPQ/order integration proves the core flow.
