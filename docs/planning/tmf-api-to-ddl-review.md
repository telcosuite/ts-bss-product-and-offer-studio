# Product And Offer Studio TMF API To DDL Review

Reviewed: 2026-06-14

Status: Complete for baseline app implementation. Endpoint-specific contract tests and final story-level field promotion still happen during build.

## Scope

This review covers `product_offer_studio` in suite database `ts_bss_commercial`. It uses the local TMF Open API reference set, the suite data model, the API-to-DDL traceability matrix, and the V001 starter DDL.

The review confirms that the app can move into implementation with a V002 typed DDL baseline while preserving full TMF payload compatibility through validated `tmf_payload`, typed common TMF columns, and normalized support tables.

## TMF API Baseline Selection

| TMF API | Local baseline spec | Resources/path roots reviewed | V001 table groups |
| --- | --- | --- | --- |
| TMF620 | `references/tmforum-open-apis/openapi-specs/TMF620_ProductCatalog/TMF620-Product_Catalog_Management-v5.0.0.oas.yaml` | `category`, `exportJob`, `importJob`, `productCatalog`, `productOffering`, `productOfferingPrice`, `productSpecification` | product_specification; product_offering; product_bundle; marketplace_listing; partner_catalog_submission |
| TMF671 | `references/tmforum-open-apis/openapi-specs/TMF671_Promotion/TMF671_Promotion_Management_API_v4.1.0_swagger.json` | `promotion` | promotion; campaign references |
| TMF760 | `references/tmforum-open-apis/openapi-specs/TMF760_ProductConfigurationManagement/TMF760-ProductConfiguration-v5.0.0.oas.yaml` | `checkProductConfiguration`, `queryProductConfiguration` | product_configuration_model |
| TMF651 | `references/tmforum-open-apis/openapi-specs/TMF651_AgreementManagement/TMF651_Agreement_Management_API_v4.0.0_swagger.json` | `agreement`, `agreementSpecification` | agreement_template; commercial_term_version; partner agreement references |
| TMF633 | `references/tmforum-open-apis/openapi-specs/TMF633_ServiceCatalog/TMF633_Service_Catalog_Management_API_v4.0.0_swagger.json` | `exportJob`, `importJob`, `serviceCandidate`, `serviceCatalog`, `serviceCategory`, `serviceSpecification` | service_specification; partner_catalog_submission references |
| TMF634 | `references/tmforum-open-apis/openapi-specs/TMF634_ResourceCatalog/TMF634-Resource_Catalog_Management-v5.0.0.oas.yaml` | `exportJob`, `importJob`, `resourceCandidate`, `resourceCatalog`, `resourceCategory`, `resourceSpecification` | resource_specification; capacity_model references |

## Current DDL Coverage

Current starter DDL is in `database/postgres/suites/ts_bss_commercial/V001__create_app_schemas_and_starter_tables.sql` under schema `product_offer_studio`.

| Current table | TMF purpose | V002 decision |
| --- | --- | --- |
| `product_offer_studio.product_specification` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.product_offering` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.product_bundle` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.product_price` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.promotion` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.product_configuration_model` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.agreement_template` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.commercial_term_version` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.catalog_version` | Starter table for Product And Offer Studio; V002 promotes common TMF fields and keeps full validated payload support. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| `product_offer_studio.event_outbox` | App outbox for domain and TMF notification events. | Keep and refine through `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |

## Resource To Table Decisions

| TMF API/resource | Master or anchor table | Path coverage | Promoted field candidates | Field handling strategy |
| --- | --- | --- | --- | --- |
| TMF620 `category` | `product_offer_studio.product_specification` | `/category`, `/category/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `exportJob` | `product_offer_studio.product_specification` | `/exportJob`, `/exportJob/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `importJob` | `product_offer_studio.product_specification` | `/importJob`, `/importJob/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `productCatalog` | `product_offer_studio.product_specification` | `/productCatalog`, `/productCatalog/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `productOffering` | `product_offer_studio.product_offering` | `/productOffering`, `/productOffering/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `productOfferingPrice` | `product_offer_studio.product_offering` | `/productOfferingPrice`, `/productOfferingPrice/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF620 `productSpecification` | `product_offer_studio.product_specification` | `/productSpecification`, `/productSpecification/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF671 `promotion` | `product_offer_studio.promotion` | `/promotion`, `/promotion/{id}` | `id`, `href`, `description`, `lastUpdate`, `lifecycleStatus`, `name`, `promotionType`, `attachment` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF760 `checkProductConfiguration` | `product_offer_studio.product_configuration_model` | `/checkProductConfiguration`, `/checkProductConfiguration/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF760 `queryProductConfiguration` | `product_offer_studio.product_configuration_model` | `/queryProductConfiguration`, `/queryProductConfiguration/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF651 `agreement` | `product_offer_studio.agreement_template` | `/agreement`, `/agreement/{id}` | `id`, `href`, `agreementType`, `description`, `documentNumber`, `initialDate`, `name`, `statementOfIntent` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF651 `agreementSpecification` | `product_offer_studio.agreement_template` | `/agreementSpecification`, `/agreementSpecification/{id}` | `id`, `href`, `description`, `isBundle`, `lastUpdate`, `lifecycleStatus`, `name`, `version` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `exportJob` | `product_offer_studio.product_specification` | `/exportJob`, `/exportJob/{id}` | `id`, `href`, `completionDate`, `contentType`, `creationDate`, `errorLog`, `path`, `query` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `importJob` | `product_offer_studio.product_specification` | `/importJob`, `/importJob/{id}` | `id`, `href`, `completionDate`, `contentType`, `creationDate`, `errorLog`, `path`, `url` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `serviceCandidate` | `product_offer_studio.product_specification` | `/serviceCandidate`, `/serviceCandidate/{id}` | `id`, `href`, `description`, `lastUpdate`, `lifecycleStatus`, `name`, `version`, `category` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `serviceCatalog` | `product_offer_studio.catalog_version` | `/serviceCatalog`, `/serviceCatalog/{id}` | `id`, `href`, `description`, `lastUpdate`, `lifecycleStatus`, `name`, `version`, `category` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `serviceCategory` | `product_offer_studio.product_specification` | `/serviceCategory`, `/serviceCategory/{id}` | `id`, `href`, `description`, `isRoot`, `lastUpdate`, `lifecycleStatus`, `name`, `parentId` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF633 `serviceSpecification` | `product_offer_studio.product_specification` | `/serviceSpecification`, `/serviceSpecification/{id}` | `id`, `href`, `description`, `isBundle`, `lastUpdate`, `lifecycleStatus`, `name`, `version` | Promote common TMF lifecycle/reference fields; store remaining validated resource fields in tmf_payload and characteristics tables. |
| TMF634 `exportJob` | `product_offer_studio.product_specification` | `/exportJob`, `/exportJob/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF634 `importJob` | `product_offer_studio.product_specification` | `/importJob`, `/importJob/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF634 `resourceCandidate` | `product_offer_studio.product_specification` | `/resourceCandidate`, `/resourceCandidate/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF634 `resourceCatalog` | `product_offer_studio.catalog_version` | `/resourceCatalog`, `/resourceCatalog/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF634 `resourceCategory` | `product_offer_studio.product_specification` | `/resourceCategory`, `/resourceCategory/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |
| TMF634 `resourceSpecification` | `product_offer_studio.product_specification` | `/resourceSpecification`, `/resourceSpecification/{id}` | Common TMF metadata plus payload validation | Promote common TMF metadata; store resource-specific fields in tmf_payload until query patterns justify additional typed columns. |

## V002 DDL Refinement

Migration: `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql`

The migration adds this implementation baseline for the app:

| Area | Decision |
| --- | --- |
| Common TMF fields | Add reusable typed columns such as `tmf_id`, `tmf_href`, `tmf_type`, `tmf_base_type`, `tmf_schema_location`, `tmf_referred_type`, `tmf_name`, `tmf_description`, `tmf_lifecycle_status`, `tmf_state`, dates, priority, and external ID to every V001 app table. |
| Full TMF compatibility | Keep the V001 `tmf_payload` column as the complete validated TMF resource snapshot for fields that are not yet promoted to typed columns. |
| Characteristics and references | Add normalized `tmf_characteristic`, `tmf_resource_reference`, `tmf_external_identifier`, `tmf_related_party`, `tmf_note`, `tmf_attachment`, and `tmf_relationship` support tables. |
| API/resource map | Add `tmf_api_resource_map` rows for the selected local TMF APIs and resource roots. |
| Event contracts | Add baseline event contract rows for create, update, state-change, and delete events per reviewed API resource. |
| Privacy and audit | Add table-level privacy, retention, legal-hold, residency, masking, and audit policy rows. |
| High-volume candidates | `product_offer_studio.catalog_version`, `product_offer_studio.event_outbox` |

## Event Contract Baseline

Events are registered in `product_offer_studio.event_contract` using `product_offer_studio.event_outbox` as the publication basis. Consumers must be added when integrations are designed; no app should directly write another app schema.

## Privacy, Retention, And Audit Baseline

| Table | Data classification | Retention class | Audit level |
| --- | --- | --- | --- |
| `product_offer_studio.product_specification` | internal | domain_lifecycle | standard |
| `product_offer_studio.product_offering` | internal | domain_lifecycle | standard |
| `product_offer_studio.product_bundle` | internal | domain_lifecycle | standard |
| `product_offer_studio.product_price` | internal | domain_lifecycle | standard |
| `product_offer_studio.promotion` | internal | domain_lifecycle | standard |
| `product_offer_studio.product_configuration_model` | internal | domain_lifecycle | standard |
| `product_offer_studio.agreement_template` | internal | domain_lifecycle | standard |
| `product_offer_studio.commercial_term_version` | internal | domain_lifecycle | standard |
| `product_offer_studio.catalog_version` | internal | operational_telemetry | standard |
| `product_offer_studio.event_outbox` | internal | operational_telemetry | standard |

## Build Gate Result

| Gate item | Result |
| --- | --- |
| API/resource review | Complete for baseline implementation |
| V002 typed DDL | Complete: `database/postgres/suites/ts_bss_commercial/V003__refine_product_offer_studio_tmf_core.sql` |
| Event contract register | Baseline complete |
| Privacy/retention/audit classification | Baseline complete |
| Remaining implementation control | Validate exact endpoint operations and contract tests as Angular/Spring Boot features are built |
