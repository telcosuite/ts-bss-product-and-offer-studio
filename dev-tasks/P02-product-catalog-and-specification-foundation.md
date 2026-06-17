# Product And Offer Studio P02 - Product Catalog And Specification Foundation Development Tasks

Suite: BSS Commercial

App: Product And Offer Studio

App slug: `product-and-offer-studio`

Implementation repository: `ts-bss-product-and-offer-studio`

Phase: P02 - Product Catalog And Specification Foundation

Phase file: `P02-product-catalog-and-specification-foundation.md`

Phase rationale: Build the Product Catalog, Catalog Governance capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work.

Phase exit gate: Product And Offer Studio can execute the Product Catalog, Catalog Governance workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests.

Out of scope for this phase: Runtime bootstrap is in P01; unrelated feature clusters and post-launch operations remain in their own phases.

Source tracker: [development-task-tracker.md](development-task-tracker.md)

Repository strategy: [TelcoSuite Repository Strategy](../../../../repository-strategy.md)

## Phase Coverage

- [Product Catalog](../features/product-catalog.md)
- [Catalog Governance](../features/catalog-governance.md)

## Phase Tasks

### DT-02-product-and-offer-studio-P02-T001: Build Product Catalog API, data model, workflow, and event spine

| Field | Value |
| --- | --- |
| Phase | P02 - Product Catalog And Specification Foundation |
| Priority | P0 |
| Source evidence | [Product Catalog](../features/product-catalog.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Catalog |
| Build area | API/Data/Event/Workflow/Security/Test |
| Target artifact | `backend/src/main/java/com/telcosuite/bsscommercial/productandofferstudio/ProductCatalogController.java`, `product_offer_studio.product_catalog`, `contracts/events/ProductCatalogStateChangedEvent.json`, and `/api/02-bss-commercial/product-and-offer-studio/v1/product-catalog` |
| Dependencies | DT-02-product-and-offer-studio-P01-T013 |
| Outputs | `ProductCatalogController`, `ProductCatalogService`, `product_offer_studio.product_catalog` migration, `ProductCatalogStateChangedEvent` outbox schema, OpenAPI operations, unit/contract/migration/event replay tests |
| Missing evidence | No |

#### Implementation Notes

- Implement command and query APIs for `/api/02-bss-commercial/product-and-offer-studio/v1/product-catalog` using TMF620, with create, update, search, detail, lifecycle transition, timeline, evidence, and exception endpoints where the feature lifecycle requires them.
- Persist `Product Catalog` state in `product_offer_studio.product_catalog` with tenant, brand/market, lifecycle state, source authority, idempotency key, correlation ID, actor, reason code, audit fields, and `tmf_payload` JSONB.
- Publish `ProductCatalogStateChangedEvent` through the transactional outbox with changed fields, replay metadata, consumer acknowledgement state, and reconciliation status for workflows: create or update, validate, close.
- Carry source details into code and tests for personas authorized operator and objects product catalog; keep cross-app references read-only unless they arrive through governed APIs/events/projections.

#### Acceptance Criteria

1. Given an authorized persona submits `POST /api/02-bss-commercial/product-and-offer-studio/v1/product-catalog`, when required fields and policy checks pass, then the API returns `201` with `$.state`, persists `product_offer_studio.product_catalog.id`, and appends `ProductCatalogStateChangedEvent` to `product_offer_studio.event_outbox`.
2. Given a stale, duplicate, or out-of-order request hits `PATCH /api/02-bss-commercial/product-and-offer-studio/v1/product-catalog/{id}`, when optimistic locking or idempotency validation fails, then the API returns `409` with `$.error.code='stale-or-duplicate-command'` and no second event is emitted.
3. Given another app needs `Product Catalog` state, when it requests data, then it receives TMF-aligned API/event/projection output and no direct database access to `product_offer_studio.product_catalog` is required.

#### Definition Of Done

- `ProductCatalogController`, service, repository, DTOs, validation, error model, and migration for `product_offer_studio.product_catalog` are committed under `ts-bss-product-and-offer-studio`.
- OpenAPI contract tests, unit tests, Flyway migration tests, event schema tests, and event replay tests cover `/api/02-bss-commercial/product-and-offer-studio/v1/product-catalog`, `product_offer_studio.product_catalog`, and `ProductCatalogStateChangedEvent`.
- `development-task-tracker.md` records command output, source feature link, PR/evidence links, and any blocked downstream consumer.

#### Negative Scenarios

- Unauthorized, cross-tenant, or wrong-purpose requests to `/api/02-bss-commercial/product-and-offer-studio/v1/product-catalog` return `403` and write a denial audit row instead of exposing `Product Catalog` data.
- Missing source authority, stale dependency state, invalid lifecycle transition, or failed policy decision keeps `product_offer_studio.product_catalog` in blocked/exception state with owner and due date.
- Downstream outage or consumer rejection queues retry/replay for `ProductCatalogStateChangedEvent` and prevents silent completion.

#### Edge Cases

- Bulk or project-scale updates to `Product Catalog` use preview, partial-failure reporting, idempotency keys, rollback/repair notes, and async export where needed.
- Historical correction preserves previous `product_offer_studio.product_catalog` values, audit reason, source timestamp, actor, and downstream recalculation/replay instructions.
- Multi-tenant, market, residency, localization, and high-volume queue cases include pagination, back-pressure, circuit breaker, and replay controls.

#### Test Expectations

- `mvn test` covers `ProductCatalogService`, validation, authorization, idempotency, and lifecycle transition rules.
- OpenAPI contract tests call `POST/GET/PATCH /api/02-bss-commercial/product-and-offer-studio/v1/product-catalog` and verify `$.state`, `$.id`, error payloads, and pagination/filter behavior.
- Flyway migration tests verify `product_offer_studio.product_catalog` columns and indexes; event replay tests validate `contracts/events/ProductCatalogStateChangedEvent.json` and `product_offer_studio.event_outbox` ordering.

### DT-02-product-and-offer-studio-P02-T002: Build Product Catalog workbench, controls, observability, and release tests

| Field | Value |
| --- | --- |
| Phase | P02 - Product Catalog And Specification Foundation |
| Priority | P1 |
| Source evidence | [Product Catalog](../features/product-catalog.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Catalog |
| Build area | UI/Security/Ops/Test |
| Target artifact | `frontend/src/app/pages/product-catalog/`, `tests/e2e/product-catalog.spec.ts`, Grafana panel `product-catalog`, and `docs/operations-runbook.md#product-catalog` |
| Dependencies | DT-02-product-and-offer-studio-P02-T001 |
| Outputs | Angular workbench, queue/detail/timeline/evidence panels, role-aware guards, accessibility states, E2E tests, dashboard JSON, alert rules, runbook section |
| Missing evidence | No |

#### Implementation Notes

- Create `frontend/src/app/pages/product-catalog/` with search/intake, detail, lifecycle timeline, exception queue, evidence drawer, dependency freshness panel, and allowed-next-action controls for personas authorized operator.
- Wire route guards, tenant/brand/market context, masking, no-permission states, keyboard navigation, PrimeNG table/form patterns, and saved filters using `ts-shared-ui-design-system`.
- Add dashboard metrics and runbook steps for workflows create or update, validate, close, event replay backlog, queue aging, policy denials, consumer lag, and completion quality.

#### Acceptance Criteria

1. Given an authorized persona opens `/app/product-and-offer-studio/product-catalog`, when records exist, then the workbench returns `$.uiState='ready'` and renders `Product Catalog` rows with lifecycle state, owner, freshness, SLA/OLA timer, and action menu.
2. Given the persona lacks permission, when the same route loads, then the UI shows a no-permission state and the backend returns `403` with `$.error.code='access-denied'`.
3. Given replay backlog or queue aging exceeds threshold, when Grafana dashboard `product-catalog` refreshes, then it shows the metric and links to `docs/operations-runbook.md#product-catalog`.

#### Definition Of Done

- `frontend/src/app/pages/product-catalog/` includes route, component, service, state, fixtures, empty/loading/error/no-permission states, and accessibility labels.
- `tests/e2e/product-catalog.spec.ts`, accessibility checks, security tests, dashboard checks, and runbook review pass and are linked from the tracker.
- `development-task-tracker.md` captures screenshots, command output, PR links, dashboard/runbook links, and unresolved blockers.

#### Negative Scenarios

- Do not render `Product Catalog` details across tenant/residency boundaries; masked values stay masked in table, detail, export, timeline, and dashboard paths.
- Do not close UI actions when backend validation, event publication, reconciliation, or required evidence is incomplete.
- Do not hide downstream outage, stale source data, policy denial, or manual override behind a generic success toast.

#### Edge Cases

- Mobile or constrained layouts for `Product Catalog` collapse tables into accessible cards without losing lifecycle, owner, SLA/OLA, or evidence fields.
- Bulk/replay actions require preview, explicit confirmation, partial-failure details, rollback/repair notes, and operator evidence.
- High-volume dashboard and queue views use pagination, saved filters, async export, trace IDs, and back-pressure indicators.

#### Test Expectations

- `npm run lint`, `npm test`, and `tests/e2e/product-catalog.spec.ts` validate route, forms, guards, workbench states, and API integration.
- Accessibility tests cover keyboard navigation, focus order, screen-reader labels, color contrast, density, and responsive layout.
- Operational-readiness tests validate Grafana dashboard JSON, alert rules, event replay panel, runbook links, and release evidence.

### DT-02-product-and-offer-studio-P02-T003: Build Catalog Governance API, data model, workflow, and event spine

| Field | Value |
| --- | --- |
| Phase | P02 - Product Catalog And Specification Foundation |
| Priority | P0 |
| Source evidence | [Catalog Governance](../features/catalog-governance.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Catalog Governance |
| Build area | API/Data/Event/Workflow/Security/Test |
| Target artifact | `backend/src/main/java/com/telcosuite/bsscommercial/productandofferstudio/CatalogGovernanceController.java`, `product_offer_studio.catalog_governance`, `contracts/events/CatalogGovernanceStateChangedEvent.json`, and `/api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance` |
| Dependencies | DT-02-product-and-offer-studio-P02-T001 |
| Outputs | `CatalogGovernanceController`, `CatalogGovernanceService`, `product_offer_studio.catalog_governance` migration, `CatalogGovernanceStateChangedEvent` outbox schema, OpenAPI operations, unit/contract/migration/event replay tests |
| Missing evidence | No |

#### Implementation Notes

- Implement command and query APIs for `/api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance` using TMF620, TMF633, TMF634, with create, update, search, detail, lifecycle transition, timeline, evidence, and exception endpoints where the feature lifecycle requires them.
- Persist `Catalog Governance` state in `product_offer_studio.catalog_governance` with tenant, brand/market, lifecycle state, source authority, idempotency key, correlation ID, actor, reason code, audit fields, and `tmf_payload` JSONB.
- Publish `CatalogGovernanceStateChangedEvent` through the transactional outbox with changed fields, replay metadata, consumer acknowledgement state, and reconciliation status for workflows: create or update, validate, close.
- Carry source details into code and tests for personas authorized operator and objects catalog governance; keep cross-app references read-only unless they arrive through governed APIs/events/projections.

#### Acceptance Criteria

1. Given an authorized persona submits `POST /api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance`, when required fields and policy checks pass, then the API returns `201` with `$.state`, persists `product_offer_studio.catalog_governance.id`, and appends `CatalogGovernanceStateChangedEvent` to `product_offer_studio.event_outbox`.
2. Given a stale, duplicate, or out-of-order request hits `PATCH /api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance/{id}`, when optimistic locking or idempotency validation fails, then the API returns `409` with `$.error.code='stale-or-duplicate-command'` and no second event is emitted.
3. Given another app needs `Catalog Governance` state, when it requests data, then it receives TMF-aligned API/event/projection output and no direct database access to `product_offer_studio.catalog_governance` is required.

#### Definition Of Done

- `CatalogGovernanceController`, service, repository, DTOs, validation, error model, and migration for `product_offer_studio.catalog_governance` are committed under `ts-bss-product-and-offer-studio`.
- OpenAPI contract tests, unit tests, Flyway migration tests, event schema tests, and event replay tests cover `/api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance`, `product_offer_studio.catalog_governance`, and `CatalogGovernanceStateChangedEvent`.
- `development-task-tracker.md` records command output, source feature link, PR/evidence links, and any blocked downstream consumer.

#### Negative Scenarios

- Unauthorized, cross-tenant, or wrong-purpose requests to `/api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance` return `403` and write a denial audit row instead of exposing `Catalog Governance` data.
- Missing source authority, stale dependency state, invalid lifecycle transition, or failed policy decision keeps `product_offer_studio.catalog_governance` in blocked/exception state with owner and due date.
- Downstream outage or consumer rejection queues retry/replay for `CatalogGovernanceStateChangedEvent` and prevents silent completion.

#### Edge Cases

- Bulk or project-scale updates to `Catalog Governance` use preview, partial-failure reporting, idempotency keys, rollback/repair notes, and async export where needed.
- Historical correction preserves previous `product_offer_studio.catalog_governance` values, audit reason, source timestamp, actor, and downstream recalculation/replay instructions.
- Multi-tenant, market, residency, localization, and high-volume queue cases include pagination, back-pressure, circuit breaker, and replay controls.

#### Test Expectations

- `mvn test` covers `CatalogGovernanceService`, validation, authorization, idempotency, and lifecycle transition rules.
- OpenAPI contract tests call `POST/GET/PATCH /api/02-bss-commercial/product-and-offer-studio/v1/catalog-governance` and verify `$.state`, `$.id`, error payloads, and pagination/filter behavior.
- Flyway migration tests verify `product_offer_studio.catalog_governance` columns and indexes; event replay tests validate `contracts/events/CatalogGovernanceStateChangedEvent.json` and `product_offer_studio.event_outbox` ordering.

### DT-02-product-and-offer-studio-P02-T004: Build Catalog Governance workbench, controls, observability, and release tests

| Field | Value |
| --- | --- |
| Phase | P02 - Product Catalog And Specification Foundation |
| Priority | P1 |
| Source evidence | [Catalog Governance](../features/catalog-governance.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Catalog Governance |
| Build area | UI/Security/Ops/Test |
| Target artifact | `frontend/src/app/pages/catalog-governance/`, `tests/e2e/catalog-governance.spec.ts`, Grafana panel `catalog-governance`, and `docs/operations-runbook.md#catalog-governance` |
| Dependencies | DT-02-product-and-offer-studio-P02-T003 |
| Outputs | Angular workbench, queue/detail/timeline/evidence panels, role-aware guards, accessibility states, E2E tests, dashboard JSON, alert rules, runbook section |
| Missing evidence | No |

#### Implementation Notes

- Create `frontend/src/app/pages/catalog-governance/` with search/intake, detail, lifecycle timeline, exception queue, evidence drawer, dependency freshness panel, and allowed-next-action controls for personas authorized operator.
- Wire route guards, tenant/brand/market context, masking, no-permission states, keyboard navigation, PrimeNG table/form patterns, and saved filters using `ts-shared-ui-design-system`.
- Add dashboard metrics and runbook steps for workflows create or update, validate, close, event replay backlog, queue aging, policy denials, consumer lag, and completion quality.

#### Acceptance Criteria

1. Given an authorized persona opens `/app/product-and-offer-studio/catalog-governance`, when records exist, then the workbench returns `$.uiState='ready'` and renders `Catalog Governance` rows with lifecycle state, owner, freshness, SLA/OLA timer, and action menu.
2. Given the persona lacks permission, when the same route loads, then the UI shows a no-permission state and the backend returns `403` with `$.error.code='access-denied'`.
3. Given replay backlog or queue aging exceeds threshold, when Grafana dashboard `catalog-governance` refreshes, then it shows the metric and links to `docs/operations-runbook.md#catalog-governance`.

#### Definition Of Done

- `frontend/src/app/pages/catalog-governance/` includes route, component, service, state, fixtures, empty/loading/error/no-permission states, and accessibility labels.
- `tests/e2e/catalog-governance.spec.ts`, accessibility checks, security tests, dashboard checks, and runbook review pass and are linked from the tracker.
- `development-task-tracker.md` captures screenshots, command output, PR links, dashboard/runbook links, and unresolved blockers.

#### Negative Scenarios

- Do not render `Catalog Governance` details across tenant/residency boundaries; masked values stay masked in table, detail, export, timeline, and dashboard paths.
- Do not close UI actions when backend validation, event publication, reconciliation, or required evidence is incomplete.
- Do not hide downstream outage, stale source data, policy denial, or manual override behind a generic success toast.

#### Edge Cases

- Mobile or constrained layouts for `Catalog Governance` collapse tables into accessible cards without losing lifecycle, owner, SLA/OLA, or evidence fields.
- Bulk/replay actions require preview, explicit confirmation, partial-failure details, rollback/repair notes, and operator evidence.
- High-volume dashboard and queue views use pagination, saved filters, async export, trace IDs, and back-pressure indicators.

#### Test Expectations

- `npm run lint`, `npm test`, and `tests/e2e/catalog-governance.spec.ts` validate route, forms, guards, workbench states, and API integration.
- Accessibility tests cover keyboard navigation, focus order, screen-reader labels, color contrast, density, and responsive layout.
- Operational-readiness tests validate Grafana dashboard JSON, alert rules, event replay panel, runbook links, and release evidence.

### DT-02-product-and-offer-studio-P02-T005: Prove Product Catalog And Specification Foundation release gate, replay, and handoff evidence

| Field | Value |
| --- | --- |
| Phase | P02 - Product Catalog And Specification Foundation |
| Priority | P1 |
| Source evidence | [Product Catalog](../features/product-catalog.md), [Catalog Governance](../features/catalog-governance.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Catalog And Specification Foundation |
| Build area | Test/Ops/Release/Event |
| Target artifact | `tests/release/product-catalog-and-specification-foundation.spec.ts`, `docs/release-notes/product-catalog-and-specification-foundation.md`, Grafana dashboard `product-catalog-and-specification-foundation`, and replay fixtures |
| Dependencies | DT-02-product-and-offer-studio-P02-T002, DT-02-product-and-offer-studio-P02-T004 |
| Outputs | Release-gate test, replay/reconciliation evidence, accessibility/security/performance reports, dashboard/runbook links, support handoff notes |
| Missing evidence | No |

#### Implementation Notes

- Create a release-gate checklist for `product-catalog-and-specification-foundation` covering Product Catalog, Catalog Governance, with happy path, assisted path, negative path, edge cases, event replay, data reconciliation, security, accessibility, performance, and support evidence.
- Record producer and consumer acknowledgements for phase events, reconcile `product_offer_studio.event_outbox`, and link replay fixtures and correlation IDs.
- Update `docs/operations-runbook.md`, `docs/release-notes/product-catalog-and-specification-foundation.md`, and `development-task-tracker.md` with release evidence and unresolved blockers.

#### Acceptance Criteria

1. Given all tasks in `P02-product-catalog-and-specification-foundation.md` are complete, when `tests/release/product-catalog-and-specification-foundation.spec.ts` runs, then it returns exit code `0` and links evidence for UI, API, data, event, security, ops, and test gates.
2. Given a consumer rejects an event from `product-catalog-and-specification-foundation`, when replay is triggered, then the replay fixture preserves `$.correlationId`, `$.eventId`, and consumer acknowledgement state.
3. Given release notes are generated, when support reviews `docs/release-notes/product-catalog-and-specification-foundation.md`, then open blockers, rollback steps, runbook links, and ownership contacts are present.

#### Definition Of Done

- `tests/release/product-catalog-and-specification-foundation.spec.ts`, replay fixtures, dashboard/runbook links, and release notes are committed.
- Accessibility, security, contract, migration, event replay, performance, and operational-readiness evidence is linked from the tracker.
- Open blockers have owner, due date, target increment, and rollback or removal criteria.

#### Negative Scenarios

- Do not mark the phase Done if event replay, reconciliation, accessibility, security, or downstream acknowledgement evidence is missing.
- Do not release `product-catalog-and-specification-foundation` with unresolved cross-app writes, direct schema coupling, or stale source authority assumptions.
- Do not suppress failed release gates; record failures with owner, due date, and target increment.

#### Edge Cases

- Coordinated release gates may require downstream app windows; record scheduling, owner, and fallback route in release notes.
- Historical backfill, replay, bulk update, or migration repair runs must include preview, partial failure report, and rollback evidence.
- High-volume launch periods require dashboard thresholds, alert owners, queue back-pressure, and support escalation paths.

#### Test Expectations

- `tests/release/product-catalog-and-specification-foundation.spec.ts`, `mvn test`, OpenAPI/event replay tests, Flyway checks, Playwright/Cypress E2E, accessibility, security, and k6/performance gates pass.
- `docker compose config`, clean-checkout smoke, `helm lint`, Kubernetes dry-run, dashboard JSON validation, and runbook link checks pass.
- Tracker evidence links command output, PRs, screenshots, replay payloads, dashboards, release notes, and support handoff notes.
