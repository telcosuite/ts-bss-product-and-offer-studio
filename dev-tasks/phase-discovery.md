# Product And Offer Studio Phase Discovery

## App Identity

| Field | Value |
| --- | --- |
| Suite | BSS Commercial |
| App | Product And Offer Studio |
| App slug | `product-and-offer-studio` |
| Implementation repo | `ts-bss-product-and-offer-studio` |
| Database | `ts_bss_commercial` |
| Schema | `product_offer_studio` |
| APIs | TMF620, TMF671, TMF760, TMF651, TMF633, TMF634 |
| Generated date | 2026-06-17 |
| Phase/task signature | 7 phases / P01=14, P02=5, P03=3, P04=3, P05=5, P06=3, P07=3 |

Phase count decision: 7 phases are evidence-derived from the current app-repo state, P01 runtime bootstrap requirements, and 8 build-ready feature files grouped by lifecycle, UI/API/data/event ownership, integration risk, and release gates.

Repeated skeleton audit: Evidence-derived and accepted for this app. Even when another app shares a phase/task-count signature, this discovery file cites this app's feature files, phase files, current repo state, and split/merge decisions; regenerate and split or merge phases if those inputs change.

## Input Evidence Inventory

| Evidence | Link | Status |
| --- | --- | --- |
| App implementation usage | [../implementation-file-usage.md](../implementation-file-usage.md) | Present |
| App README | [../README.md](../README.md) | Present |
| Modules and features | [../modules-and-features.md](../modules-and-features.md) | Present |
| Personas and journeys | [../personas-and-user-journeys.md](../personas-and-user-journeys.md) | Present |
| Suite data model | [../../data-model.md](../../data-model.md) | Present |
| Suite tech/UI guidance | [../../tech-and-ui-guidance.md](../../tech-and-ui-guidance.md) | Present |
| Suite implementation guide | [../../implementation-file-usage-guide.md](../../implementation-file-usage-guide.md) | Present |
| Repository strategy | [../../../../repository-strategy.md](../../../../repository-strategy.md) | Present |
| Feature: Agreement And Contract | [../features/agreement-and-contract.md](../features/agreement-and-contract.md) | Present |
| Feature: Catalog Governance | [../features/catalog-governance.md](../features/catalog-governance.md) | Present |
| Feature: Offer Launch Readiness And Test Catalog | [../features/offer-launch-readiness-and-test-catalog.md](../features/offer-launch-readiness-and-test-catalog.md) | Present |
| Feature: Pricing, Promotion, And Discount | [../features/pricing-promotion-and-discount.md](../features/pricing-promotion-and-discount.md) | Present |
| Feature: Product Catalog | [../features/product-catalog.md](../features/product-catalog.md) | Present |
| Feature: Product Configuration | [../features/product-configuration.md](../features/product-configuration.md) | Present |
| Feature: Product Sunset Grandfathering And Migration | [../features/product-sunset-grandfathering-and-migration.md](../features/product-sunset-grandfathering-and-migration.md) | Present |
| Feature: Tax Revenue Account And Regulatory Filing | [../features/tax-revenue-account-and-regulatory-filing.md](../features/tax-revenue-account-and-regulatory-filing.md) | Present |

## App Repository Current State Inventory

| Marker | Value |
| --- | --- |
| Repo exists | Yes |
| Runnable frontend: | No |
| Runnable backend: | No |
| App-specific migrations: | Yes |
| OpenAPI contract | Yes |
| Event contracts | Yes |
| Deployment skeleton | Yes |
| CI workflow | No |
| Current implementation conclusion: | Keep the zero-to-one foundation explicit until runnable frontend, backend, migrations, contracts, CI, deployment, and proof-slice evidence are all present in `ts-bss-product-and-offer-studio`. |

## Feature/Module Cluster Analysis

| Feature | Feature ID | Source detail carried into tasks | Implementing task IDs | Phase |
| --- | --- | --- | --- | --- |
| [Agreement And Contract](../features/agreement-and-contract.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P05-T001, DT-02-product-and-offer-studio-P05-T002, DT-02-product-and-offer-studio-P05-T005 | P05 - Agreement Contract And Launch Readiness |
| [Catalog Governance](../features/catalog-governance.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P02-T003, DT-02-product-and-offer-studio-P02-T004, DT-02-product-and-offer-studio-P02-T005 | P02 - Product Catalog And Specification Foundation |
| [Offer Launch Readiness And Test Catalog](../features/offer-launch-readiness-and-test-catalog.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P05-T003, DT-02-product-and-offer-studio-P05-T004, DT-02-product-and-offer-studio-P05-T005 | P05 - Agreement Contract And Launch Readiness |
| [Pricing, Promotion, And Discount](../features/pricing-promotion-and-discount.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P03-T001, DT-02-product-and-offer-studio-P03-T002, DT-02-product-and-offer-studio-P03-T003 | P03 - Pricing Promotion And Discount Engine |
| [Product Catalog](../features/product-catalog.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P02-T001, DT-02-product-and-offer-studio-P02-T002, DT-02-product-and-offer-studio-P02-T005 | P02 - Product Catalog And Specification Foundation |
| [Product Configuration](../features/product-configuration.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P04-T001, DT-02-product-and-offer-studio-P04-T002, DT-02-product-and-offer-studio-P04-T003 | P04 - Product Configuration And Bundle Modeling |
| [Product Sunset Grandfathering And Migration](../features/product-sunset-grandfathering-and-migration.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P07-T001, DT-02-product-and-offer-studio-P07-T002, DT-02-product-and-offer-studio-P07-T003 | P07 - Product Sunset Grandfathering And Migration |
| [Tax Revenue Account And Regulatory Filing](../features/tax-revenue-account-and-regulatory-filing.md) | F-product-and-offer-studio-001 |  | DT-02-product-and-offer-studio-P06-T001, DT-02-product-and-offer-studio-P06-T002, DT-02-product-and-offer-studio-P06-T003 | P06 - Tax Revenue Account And Regulatory Filing |

## Phase Decision Matrix

| Phase file | Task count | Evidence basis | Exit gate |
| --- | --- | --- | --- |
| [P01-from-scratch-app-foundation-and-delivery-runtime.md](P01-from-scratch-app-foundation-and-delivery-runtime.md) | 14 | The planning pack and local repo inspection do not prove a complete runnable implementation for `ts-bss-product-and-offer-studio`; this from-scratch foundation phase creates the app-root runtime, governance, contracts, data, CI, deployment, observability, and proof slice before feature delivery. | A clean checkout of `ts-bss-product-and-offer-studio` can run Angular and Spring Boot, apply `product_offer_studio` migrations, validate contracts/events, run Docker Compose and Helm checks, and prove one UI/API/data/event slice. |
| [P02-product-catalog-and-specification-foundation.md](P02-product-catalog-and-specification-foundation.md) | 5 | Build the Product Catalog, Catalog Governance capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Product Catalog, Catalog Governance workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |
| [P03-pricing-promotion-and-discount-engine.md](P03-pricing-promotion-and-discount-engine.md) | 3 | Build the Pricing, Promotion, And Discount capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Pricing, Promotion, And Discount workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |
| [P04-product-configuration-and-bundle-modeling.md](P04-product-configuration-and-bundle-modeling.md) | 3 | Build the Product Configuration capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Product Configuration workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |
| [P05-agreement-contract-and-launch-readiness.md](P05-agreement-contract-and-launch-readiness.md) | 5 | Build the Agreement And Contract, Offer Launch Readiness And Test Catalog capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Agreement And Contract, Offer Launch Readiness And Test Catalog workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |
| [P06-tax-revenue-account-and-regulatory-filing.md](P06-tax-revenue-account-and-regulatory-filing.md) | 3 | Build the Tax Revenue Account And Regulatory Filing capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Tax Revenue Account And Regulatory Filing workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |
| [P07-product-sunset-grandfathering-and-migration.md](P07-product-sunset-grandfathering-and-migration.md) | 3 | Build the Product Sunset Grandfathering And Migration capability cluster for Product And Offer Studio, carrying source workflows, APIs, events, tables, controls, and tests from the feature files into implementable work. | Product And Offer Studio can execute the Product Sunset Grandfathering And Migration workflows through UI, API, `product_offer_studio` persistence, outbox events, audit evidence, and release tests. |

## Split/Merge Decisions

- P01 remains the app-runtime foundation because the local repo inspection does not prove a complete runnable implementation for `ts-bss-product-and-offer-studio`.
- Feature phases are grouped from source `features/*.md` files by lifecycle ownership, UI workbench/API/data/event coupling, security/privacy controls, observability, and release-test needs.
- Every feature file appears in task `Source evidence`, the tracker coverage matrix, and this discovery artifact; tracker-only feature references are not accepted as coverage.
- Generic phase names from older task packs are retired by this refresh and replaced with feature-derived phase names.

## Validator and Regeneration Notes

- Run `python3 telcosuite-skills/skills/tmf-dev-task-planner/scripts/validate_dev_tasks.py --root ts-planning/planning/suite-details/02-bss-commercial/product-and-offer-studio --strict` after refresh.
- Re-run the mirror driver after validation so `ts-bss-product-and-offer-studio/dev-tasks/` remains byte-identical to the planning source.
- If a source feature changes, refresh this app pack and verify phase count, feature coverage, task detail quality, and mirror parity again.
