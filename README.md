# Fintecture (fintecture)

Fintecture is a French Open Banking payments platform and ACPR-authorised payment institution (#17248). Its API stack covers PSD2 Payment Initiation (Immediate Transfer, Smart Transfer, Request To Pay, Buy Now Pay Later, Verified Payout, Immediate Refund), PSD2 Account Information (accounts, holders, transactions, identity verification), Customers, E-Mandates, and a beta Organisation Access Credentials surface for managing multi-tenant enterprise estates. Clients include Auchan, Bricoman, Pluxee, PMU, and Edenred, with 2M+ end payers served. Plug-and-play modules for PrestaShop, Magento, Shopify, WordPress, Odoo, Intershop, and Oasis sit on top of official JavaScript, Python, PHP, and Ruby SDKs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fintecture/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fintecture/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Open Banking
- Payments
- PSD2
- France
- Account Information
- Payment Initiation
- Instant Payments
- SEPA
- Smart Transfer
- Request To Pay
- Buy Now Pay Later
- E-Mandates
- Account-to-Account
- KYC

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Fintecture Payment Initiation Services API

PSD2 Payment Initiation Services for Immediate Transfer, Smart Transfer (auto-reconciled with virtual IBANs), Request To Pay (payment links via email/SMS/QR), Buy Now Pay Later, and Verified Payout. The same /pis/v2/connect endpoint serves immediate transfers, smart transfers, and BNPL via a single Payment Hub abstraction. Production calls require HTTP message signature (RFC draft-cavage-http-signatures), digest, date, and x-request-id headers.

- **Human URL:** [https://doc.fintecture.com/reference/createpisv2connect](https://doc.fintecture.com/reference/createpisv2connect)

#### Tags

- Open Banking
- Payments
- PIS
- PSD2
- Bank Transfers
- Account-to-Account

#### Properties

- [Documentation](https://doc.fintecture.com/reference/createpisv2connect)
- [Documentation](https://doc.fintecture.com/docs/api-initiate-an-immediate-payment)
- [Documentation](https://doc.fintecture.com/docs/api-initiate-a-smart-transfer)
- [Documentation](https://doc.fintecture.com/docs/api-initiate-a-request-to-pay)
- [OpenAPI](openapi/fintecture-pis-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-pis-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-pis-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/fintecture-payment-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/fintecture-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Fintecture Account Information Services API

PSD2 Account Information Services. Retrieve PSU bank accounts, holders, balances, and transaction history after the PSU authenticates with their bank via the redirect or decoupled (mobile app) flow. Includes an AIS-based identity verification endpoint used to confirm the bank account holder name matches the merchant's customer record.

- **Human URL:** [https://doc.fintecture.com/reference/getaisv2connect](https://doc.fintecture.com/reference/getaisv2connect)

#### Tags

- Open Banking
- AIS
- PSD2
- Account Information
- Bank Data

#### Properties

- [Documentation](https://doc.fintecture.com/reference/getaisv2connect)
- [Documentation](https://doc.fintecture.com/docs/api-recover-bank-accounts)
- [Documentation](https://doc.fintecture.com/docs/api-recover-bank-account-transactions)
- [OpenAPI](openapi/fintecture-ais-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-ais-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-ais-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/fintecture-account-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Fintecture Customers API

Register and manage merchant customers, attach their bank accounts, and run identity verifications. Persisted customer records pre-fill payment fields and accelerate repeat checkouts; verifications confirm account holder identity through the AIS rails.

- **Human URL:** [https://doc.fintecture.com/reference/createcustomer](https://doc.fintecture.com/reference/createcustomer)

#### Tags

- Customers
- KYC
- Bank Accounts
- Verification

#### Properties

- [Documentation](https://doc.fintecture.com/reference/createcustomer)
- [Documentation](https://doc.fintecture.com/docs/api-verify-a-customer)
- [OpenAPI](openapi/fintecture-customers-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-customers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-customers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fintecture E-Mandates API

Create, list, retrieve, update (cancel/revoke), and manage SEPA-style customer e-mandates identified by a unique Reference Unique Mandate (RUM). Returns 409 Conflict on duplicate RUM. Requires a dedicated E-Mandate access token.

- **Human URL:** [https://doc.fintecture.com/reference/createemandate](https://doc.fintecture.com/reference/createemandate)

#### Tags

- E-Mandates
- SEPA
- Direct Debit
- Recurring Payments

#### Properties

- [Documentation](https://doc.fintecture.com/reference/createemandate)
- [Documentation](https://doc.fintecture.com/docs/request-e-mandate-access-token)
- [OpenAPI](openapi/fintecture-emandates-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-emandates-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-emandates-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fintecture OAuth and Tokens API

Issues access tokens via authorization_code and client_credentials grants. Distinct scopes for PIS, AIS, Customers, E-Mandates, and OAC (Organisation Access Credentials, beta). Access tokens are valid for 1 hour and can be refreshed.

- **Human URL:** [https://doc.fintecture.com/reference/createaccesstoken](https://doc.fintecture.com/reference/createaccesstoken)

#### Tags

- OAuth
- Authentication
- Access Tokens
- Security

#### Properties

- [Documentation](https://doc.fintecture.com/reference/createaccesstoken)
- [Documentation](https://doc.fintecture.com/docs/api-request-a-pis-access-token)
- [Documentation](https://doc.fintecture.com/docs/api-request-an-ais-token)
- [OpenAPI](openapi/fintecture-oauth-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-oauth-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-oauth-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fintecture Resources API

Catalog of supported banks (Providers) with per-bank AIS capabilities (accountholders, accounts, transactions) and PIS rails (SEPA, iSCT instant, FPS, PLN, INT). Also exposes sandbox test accounts for each bank.

- **Human URL:** [https://doc.fintecture.com/reference/getresv1providers](https://doc.fintecture.com/reference/getresv1providers)

#### Tags

- Banks
- Providers
- Reference Data
- Sandbox

#### Properties

- [Documentation](https://doc.fintecture.com/reference/getresv1providers)
- [OpenAPI](openapi/fintecture-resources-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-resources-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-resources-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fintecture Organisation Access Credentials API

Beta multi-tenant management API for enterprise customers. Programmatically manage Applications, Bank Accounts, Companies, Organisation Nodes (hierarchical tree), Memberships, and Users in the Fintecture Console. Requires an OAC access token with per-resource read/write scopes.

- **Human URL:** [https://doc.fintecture.com/docs/request-an-oac-access-token](https://doc.fintecture.com/docs/request-an-oac-access-token)

#### Tags

- Organisations
- Access Control
- Beta
- Multi-Tenant
- Console Management

#### Properties

- [Documentation](https://doc.fintecture.com/docs/request-an-oac-access-token)
- [OpenAPI](openapi/fintecture-oac-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-oac-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-oac-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fintecture Transactions and Settlements API

Inspect transactions and settlements. Settlements represent outgoing disbursements from the merchant's Local Acquiring account to their own bank account. Sandbox includes a transaction simulator endpoint.

- **Human URL:** [https://doc.fintecture.com/reference/getpisv2settlements](https://doc.fintecture.com/reference/getpisv2settlements)

#### Tags

- Transactions
- Settlements
- Local Acquiring
- Reconciliation
- Reporting

#### Properties

- [Documentation](https://doc.fintecture.com/reference/getpisv2settlements)
- [Documentation](https://doc.fintecture.com/reference/listalltransactions)
- [OpenAPI](openapi/fintecture-transactions-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fintecture-transactions-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fintecture-transactions-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [LinkedIn](https://www.linkedin.com/company/fintecture)
- [Portal](https://fintecture.com)
- [Documentation](https://doc.fintecture.com)
- [Documentation](https://doc.fintecture.com/docs/api-overview)
- [Getting Started](https://doc.fintecture.com/docs/api-overview)
- [Documentation](https://doc.fintecture.com/docs/api-http-signature)
- [Documentation](https://doc.fintecture.com/docs/api-webhooks)
- [Documentation](https://doc.fintecture.com/docs/demo-bank)
- [Documentation](https://doc.fintecture.com/docs/testing-complete-payment-flows-in-sandbox)
- [Changelog](https://doc.fintecture.com/changelog)
- [Sign Up](https://console.fintecture.com/)
- [Sandbox](https://console-sandbox.fintecture.com/)
- [Postman](https://doc.fintecture.com/docs/api-take-on-our-postman-collection) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [GitHub Organization](https://github.com/Fintecture)
- [SDK](https://github.com/Fintecture/fintecture-sdk-javascript)
- [SDK](https://github.com/Fintecture/fintecture-sdk-python)
- [SDK](https://github.com/Fintecture/fintecture-sdk-php)
- [SDK](https://github.com/Fintecture/fintecture-sdk-ruby)
- [Sample Code](https://github.com/Fintecture/sample-nodejs)
- [Sample Code](https://github.com/Fintecture/sample-ror)
- [Sample Code](https://github.com/Fintecture/signature-guide)
- [Plugins](https://github.com/Fintecture/magento)
- [Plugins](https://github.com/Fintecture/magento-hyva)
- [Plugins](https://github.com/Fintecture/magento19)
- [Plugins](https://github.com/Fintecture/odoo)
- [Integrations](https://doc.fintecture.com/docs/cms-overview)
- [Pricing](https://fintecture.com/tarifs)
- [Terms of Service](https://fintecture.com/mentions-legales)
- [Privacy Policy](https://fintecture.com/politique-de-confidentialite)
- [Support](https://fintecture.com/contact)
- [Status Page](https://status.fintecture.com)
- [Blog](https://fintecture.com/blog)
- [Regions](undefined)
- [Regulator](https://acpr.banque-france.fr/)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
