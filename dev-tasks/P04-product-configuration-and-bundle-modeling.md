# Product And Offer Studio P04 - Product Configuration And Bundle Modeling Development Tasks

Suite: BSS Commercial

App: Product And Offer Studio

App slug: `product-and-offer-studio`

Implementation repository: `ts-bss-product-and-offer-studio`

Phase: P04 - Product Configuration And Bundle Modeling

Phase file: `P04-product-configuration-and-bundle-modeling.md`

Phase rationale: Build the Product Configuration capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work.

Phase exit gate: Product And Offer Studio can execute the Product Configuration workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests.

Out of scope for this phase: Runtime bootstrap is in P01; unrelated feature clusters and post-launch operations remain in their own phases.

Source tracker: [development-task-tracker.md](development-task-tracker.md)

Repository strategy: [TelcoSuite Repository Strategy](../../../../repository-strategy.md)

## Phase Coverage

- [Product Configuration](../features/product-configuration.md)

## Phase Tasks

### DT-02-product-and-offer-studio-P04-T001: Build Product Configuration API, data model, workflow, and event spine

| Field | Value |
| --- | --- |
| Phase | P04 - Product Configuration And Bundle Modeling |
| Priority | P0 |
| Source evidence | [Product Configuration](../features/product-configuration.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Configuration |
| Build area | API/Data/Event/Workflow/Security/Test |
| Target artifact | `backend/src/main/java/com/telcosuite/bsscommercial/productandofferstudio/ProductConfigurationController.java`, `product_offer_studio.product_configuration`, `contracts/events/ProductConfigurationStateChangedEvent.json`, and `/api/02-bss-commercial/product-and-offer-studio/v1/product-configuration` |
| Dependencies | DT-02-product-and-offer-studio-P01-T013 |
| Outputs | `ProductConfigurationController`, `ProductConfigurationService`, `product_offer_studio.product_configuration` migration, `ProductConfigurationStateChangedEvent` outbox schema, OpenAPI operations, unit/contract/migration/event replay tests |
| Missing evidence | No |

#### Implementation Notes

- Implement command and query APIs for `/api/02-bss-commercial/product-and-offer-studio/v1/product-configuration` using TMF760, with create, update, search, detail, lifecycle transition, timeline, evidence, and exception endpoints where the feature lifecycle requires them.
- Persist `Product Configuration` state in `product_offer_studio.product_configuration` with tenant, brand/market, lifecycle state, source authority, idempotency key, correlation ID, actor, reason code, audit fields, and `tmf_payload` JSONB.
- Publish `ProductConfigurationStateChangedEvent` through the transactional outbox with changed fields, replay metadata, consumer acknowledgement state, and reconciliation status for workflows: create or update, validate, close.
- Carry source details into code and tests for personas authorized operator and objects product configuration; keep cross-app references read-only unless they arrive through governed APIs/events/projections.

#### Acceptance Criteria

1. Given an authorized persona submits `POST /api/02-bss-commercial/product-and-offer-studio/v1/product-configuration`, when required fields and policy checks pass, then the API returns `201` with `$.state`, persists `product_offer_studio.product_configuration.id`, and appends `ProductConfigurationStateChangedEvent` to `product_offer_studio.event_outbox`.
2. Given a stale, duplicate, or out-of-order request hits `PATCH /api/02-bss-commercial/product-and-offer-studio/v1/product-configuration/{id}`, when optimistic locking or idempotency validation fails, then the API returns `409` with `$.error.code='stale-or-duplicate-command'` and no second event is emitted.
3. Given another app needs `Product Configuration` state, when it requests data, then it receives TMF-aligned API/event/projection output and no direct database access to `product_offer_studio.product_configuration` is required.

#### Definition Of Done

- `ProductConfigurationController`, service, repository, DTOs, validation, error model, and migration for `product_offer_studio.product_configuration` are committed under `ts-bss-product-and-offer-studio`.
- OpenAPI contract tests, unit tests, Flyway migration tests, event schema tests, and event replay tests cover `/api/02-bss-commercial/product-and-offer-studio/v1/product-configuration`, `product_offer_studio.product_configuration`, and `ProductConfigurationStateChangedEvent`.
- `development-task-tracker.md` records command output, source feature link, PR/evidence links, and any blocked downstream consumer.

#### Negative Scenarios

- Unauthorized, cross-tenant, or wrong-purpose requests to `/api/02-bss-commercial/product-and-offer-studio/v1/product-configuration` return `403` and write a denial audit row instead of exposing `Product Configuration` data.
- Missing source authority, stale dependency state, invalid lifecycle transition, or failed policy decision keeps `product_offer_studio.product_configuration` in blocked/exception state with owner and due date.
- Downstream outage or consumer rejection queues retry/replay for `ProductConfigurationStateChangedEvent` and prevents silent completion.

#### Edge Cases

- Bulk or project-scale updates to `Product Configuration` use preview, partial-failure reporting, idempotency keys, rollback/repair notes, and async export where needed.
- Historical correction preserves previous `product_offer_studio.product_configuration` values, audit reason, source timestamp, actor, and downstream recalculation/replay instructions.
- Multi-tenant, market, residency, localization, and high-volume queue cases include pagination, back-pressure, circuit breaker, and replay controls.

#### Test Expectations

- `mvn test` covers `ProductConfigurationService`, validation, authorization, idempotency, and lifecycle transition rules.
- OpenAPI contract tests call `POST/GET/PATCH /api/02-bss-commercial/product-and-offer-studio/v1/product-configuration` and verify `$.state`, `$.id`, error payloads, and pagination/filter behavior.
- Flyway migration tests verify `product_offer_studio.product_configuration` columns and indexes; event replay tests validate `contracts/events/ProductConfigurationStateChangedEvent.json` and `product_offer_studio.event_outbox` ordering.

### DT-02-product-and-offer-studio-P04-T002: Build Product Configuration workbench, controls, observability, and release tests

| Field | Value |
| --- | --- |
| Phase | P04 - Product Configuration And Bundle Modeling |
| Priority | P1 |
| Source evidence | [Product Configuration](../features/product-configuration.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Configuration |
| Build area | UI/Security/Ops/Test |
| Target artifact | `frontend/src/app/pages/product-configuration/`, `tests/e2e/product-configuration.spec.ts`, Grafana panel `product-configuration`, and `docs/operations-runbook.md#product-configuration` |
| Dependencies | DT-02-product-and-offer-studio-P04-T001 |
| Outputs | Angular workbench, queue/detail/timeline/evidence panels, role-aware guards, accessibility states, E2E tests, dashboard JSON, alert rules, runbook section |
| Missing evidence | No |

#### Implementation Notes

- Create `frontend/src/app/pages/product-configuration/` with search/intake, detail, lifecycle timeline, exception queue, evidence drawer, dependency freshness panel, and allowed-next-action controls for personas authorized operator.
- Wire route guards, tenant/brand/market context, masking, no-permission states, keyboard navigation, PrimeNG table/form patterns, and saved filters using `ts-shared-ui-design-system`.
- Add dashboard metrics and runbook steps for workflows create or update, validate, close, event replay backlog, queue aging, policy denials, consumer lag, and completion quality.

#### Acceptance Criteria

1. Given an authorized persona opens `/app/product-and-offer-studio/product-configuration`, when records exist, then the workbench returns `$.uiState='ready'` and renders `Product Configuration` rows with lifecycle state, owner, freshness, SLA/OLA timer, and action menu.
2. Given the persona lacks permission, when the same route loads, then the UI shows a no-permission state and the backend returns `403` with `$.error.code='access-denied'`.
3. Given replay backlog or queue aging exceeds threshold, when Grafana dashboard `product-configuration` refreshes, then it shows the metric and links to `docs/operations-runbook.md#product-configuration`.

#### Definition Of Done

- `frontend/src/app/pages/product-configuration/` includes route, component, service, state, fixtures, empty/loading/error/no-permission states, and accessibility labels.
- `tests/e2e/product-configuration.spec.ts`, accessibility checks, security tests, dashboard checks, and runbook review pass and are linked from the tracker.
- `development-task-tracker.md` captures screenshots, command output, PR links, dashboard/runbook links, and unresolved blockers.

#### Negative Scenarios

- Do not render `Product Configuration` details across tenant/residency boundaries; masked values stay masked in table, detail, export, timeline, and dashboard paths.
- Do not close UI actions when backend validation, event publication, reconciliation, or required evidence is incomplete.
- Do not hide downstream outage, stale source data, policy denial, or manual override behind a generic success toast.

#### Edge Cases

- Mobile or constrained layouts for `Product Configuration` collapse tables into accessible cards without losing lifecycle, owner, SLA/OLA, or evidence fields.
- Bulk/replay actions require preview, explicit confirmation, partial-failure details, rollback/repair notes, and operator evidence.
- High-volume dashboard and queue views use pagination, saved filters, async export, trace IDs, and back-pressure indicators.

#### Test Expectations

- `npm run lint`, `npm test`, and `tests/e2e/product-configuration.spec.ts` validate route, forms, guards, workbench states, and API integration.
- Accessibility tests cover keyboard navigation, focus order, screen-reader labels, color contrast, density, and responsive layout.
- Operational-readiness tests validate Grafana dashboard JSON, alert rules, event replay panel, runbook links, and release evidence.

### DT-02-product-and-offer-studio-P04-T003: Prove Product Configuration And Bundle Modeling release gate, replay, and handoff evidence

| Field | Value |
| --- | --- |
| Phase | P04 - Product Configuration And Bundle Modeling |
| Priority | P1 |
| Source evidence | [Product Configuration](../features/product-configuration.md), [Implementation usage](../implementation-file-usage.md), [App README](../README.md), [App overview](../../product-and-offer-studio.md), [Modules and features](../modules-and-features.md), [Personas and journeys](../personas-and-user-journeys.md), [Suite tech/UI guidance](../../tech-and-ui-guidance.md), [Suite data model](../../data-model.md), [Suite implementation guide](../../implementation-file-usage-guide.md), [Repository strategy](../../../../repository-strategy.md) |
| Feature or module | Product Configuration And Bundle Modeling |
| Build area | Test/Ops/Release/Event |
| Target artifact | `tests/release/product-configuration-and-bundle-modeling.spec.ts`, `docs/release-notes/product-configuration-and-bundle-modeling.md`, Grafana dashboard `product-configuration-and-bundle-modeling`, and replay fixtures |
| Dependencies | DT-02-product-and-offer-studio-P04-T002 |
| Outputs | Release-gate test, replay/reconciliation evidence, accessibility/security/performance reports, dashboard/runbook links, support handoff notes |
| Missing evidence | No |

#### Implementation Notes

- Create a release-gate checklist for `product-configuration-and-bundle-modeling` covering Product Configuration, with happy path, assisted path, negative path, edge cases, event replay, data reconciliation, security, accessibility, performance, and support evidence.
- Record producer and consumer acknowledgements for phase events, reconcile `product_offer_studio.event_outbox`, and link replay fixtures and correlation IDs.
- Update `docs/operations-runbook.md`, `docs/release-notes/product-configuration-and-bundle-modeling.md`, and `development-task-tracker.md` with release evidence and unresolved blockers.

#### Acceptance Criteria

1. Given all tasks in `P04-product-configuration-and-bundle-modeling.md` are complete, when `tests/release/product-configuration-and-bundle-modeling.spec.ts` runs, then it returns exit code `0` and links evidence for UI, API, data, event, security, ops, and test gates.
2. Given a consumer rejects an event from `product-configuration-and-bundle-modeling`, when replay is triggered, then the replay fixture preserves `$.correlationId`, `$.eventId`, and consumer acknowledgement state.
3. Given release notes are generated, when support reviews `docs/release-notes/product-configuration-and-bundle-modeling.md`, then open blockers, rollback steps, runbook links, and ownership contacts are present.

#### Definition Of Done

- `tests/release/product-configuration-and-bundle-modeling.spec.ts`, replay fixtures, dashboard/runbook links, and release notes are committed.
- Accessibility, security, contract, migration, event replay, performance, and operational-readiness evidence is linked from the tracker.
- Open blockers have owner, due date, target increment, and rollback or removal criteria.

#### Negative Scenarios

- Do not mark the phase Done if event replay, reconciliation, accessibility, security, or downstream acknowledgement evidence is missing.
- Do not release `product-configuration-and-bundle-modeling` with unresolved cross-app writes, direct schema coupling, or stale source authority assumptions.
- Do not suppress failed release gates; record failures with owner, due date, and target increment.

#### Edge Cases

- Coordinated release gates may require downstream app windows; record scheduling, owner, and fallback route in release notes.
- Historical backfill, replay, bulk update, or migration repair runs must include preview, partial failure report, and rollback evidence.
- High-volume launch periods require dashboard thresholds, alert owners, queue back-pressure, and support escalation paths.

#### Test Expectations

- `tests/release/product-configuration-and-bundle-modeling.spec.ts`, `mvn test`, OpenAPI/event replay tests, Flyway checks, Playwright/Cypress E2E, accessibility, security, and k6/performance gates pass.
- `docker compose config`, clean-checkout smoke, `helm lint`, Kubernetes dry-run, dashboard JSON validation, and runbook link checks pass.
- Tracker evidence links command output, PRs, screenshots, replay payloads, dashboards, release notes, and support handoff notes.
