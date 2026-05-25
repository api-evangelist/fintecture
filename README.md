# Fintecture (fintecture)
Fintecture is a French Open Banking payments platform and ACPR-authorised payment institution (#17248) headquartered in Paris. Its API stack covers PSD2 Payment Initiation (Immediate Transfer, Smart Transfer, Request To Pay, Buy Now Pay Later, Verified Payout, Immediate Refund), PSD2 Account Information (accounts, holders, transactions, identity verification), Customers, E-Mandates, and a beta Organisation Access Credentials (OAC) surface for managing multi-tenant enterprise estates. Clients include Auchan, Bricoman, Pluxee, PMU, and Edenred, with 2M+ end payers served. The platform ships official JavaScript / TypeScript, Python, PHP, and Ruby SDKs alongside plug-and-play modules for PrestaShop, Magento (2, 1.9, Hyva), Shopify, WordPress, Odoo, Intershop, and Oasis.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/fintecture/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Open Banking, Payments, PSD2, France, Account Information, Payment Initiation, Instant Payments, SEPA, Smart Transfer, Request To Pay, Buy Now Pay Later, E-Mandates, Account-to-Account, KYC

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Environments

| Environment | Base URL | Console |
|---|---|---|
| Production | `https://api.fintecture.com` | `https://console.fintecture.com` |
| Sandbox | `https://api-sandbox.fintecture.com` | `https://console-sandbox.fintecture.com` |

Production calls **require** the `Signature`, `Digest`, `Date`, and `x-request-id` HTTP headers. See the [HTTP Signature Guide](https://doc.fintecture.com/docs/api-http-signature) and the [signature-guide](https://github.com/Fintecture/signature-guide) reference repository.

## Payment Rails

| Rail | Code | Coverage |
|---|---|---|
| SEPA Credit Transfer | `SEPA` | EEA |
| SEPA Instant Credit Transfer | `iSCT` | EEA |
| UK Faster Payments | `FPS` | United Kingdom |
| Polish ELIXIR | `PLN` | Poland |
| International | `INT` | Cross-border |

Per-provider rail availability is exposed under `pis` on `GET /res/v1/providers`.

## APIs

### Fintecture Payment Initiation Services API
PSD2 Payment Initiation Services for Immediate Transfer, Smart Transfer (auto-reconciled via merchant-allocated virtual IBANs), Request To Pay (payment links via email/SMS/QR), Buy Now Pay Later, and Verified Payout. A single `/pis/v2/connect` endpoint serves all three payment types and supports them mixed in one session via the Payment Hub.

**Human URL:** [Create A Payment Session](https://doc.fintecture.com/reference/createpisv2connect)

- [OpenAPI](openapi/fintecture-pis-api-openapi.yml)
- [JSON Schema — Payment](json-schema/fintecture-payment-schema.json)
- [JSON-LD](json-ld/fintecture-context.jsonld)
- [Naftiko Capability — Payments](capabilities/pis-payments.yaml)
- [Naftiko Capability — Request To Pay](capabilities/pis-request-to-pay.yaml)
- [Naftiko Capability — Refunds](capabilities/pis-refunds.yaml)
- [Naftiko Capability — Settlements](capabilities/pis-settlements.yaml)

### Fintecture Account Information Services API
PSD2 Account Information Services. Retrieve PSU bank accounts, holders, balances, and transaction history after the PSU authenticates with their bank via the redirect or decoupled (mobile-app) flow. Also exposes the AIS-based identity verification endpoint used to confirm the bank account holder name matches the merchant's customer record.

**Human URL:** [Get AIS Connect Session](https://doc.fintecture.com/reference/getaisv2connect)

- [OpenAPI](openapi/fintecture-ais-api-openapi.yml)
- [JSON Schema — Account](json-schema/fintecture-account-schema.json)
- [Naftiko Capability — Accounts](capabilities/ais-accounts.yaml)
- [Naftiko Capability — Transactions](capabilities/ais-transactions.yaml)
- [Naftiko Capability — Verification](capabilities/ais-verification.yaml)

### Fintecture Customers API
Register and manage merchant customers, attach their bank accounts, and run identity verifications. Persisted customer records pre-fill payment fields and accelerate repeat checkouts; verifications confirm account holder identity through the AIS rails.

**Human URL:** [Create Customer](https://doc.fintecture.com/reference/createcustomer)

- [OpenAPI](openapi/fintecture-customers-api-openapi.yml)
- [Naftiko Capability — Customers](capabilities/customers-customers.yaml)
- [Naftiko Capability — Bank Accounts](capabilities/customers-bank-accounts.yaml)
- [Naftiko Capability — Verifications](capabilities/customers-verifications.yaml)

### Fintecture E-Mandates API
Create, list, retrieve, update (cancel/revoke), and manage SEPA-style customer e-mandates identified by a unique Reference Unique Mandate (RUM). Returns 409 Conflict on duplicate RUM. Requires a dedicated E-Mandate access token.

**Human URL:** [Create E-Mandate](https://doc.fintecture.com/reference/createemandate)

- [OpenAPI](openapi/fintecture-emandates-api-openapi.yml)
- [Naftiko Capability — E-Mandates](capabilities/emandates-emandates.yaml)

### Fintecture OAuth and Tokens API
Issues access tokens via `authorization_code` and `client_credentials` grants. Distinct scopes for PIS, AIS, Customers, E-Mandates, and OAC (beta). Tokens are valid for 1 hour and can be refreshed.

**Human URL:** [Create Access Token](https://doc.fintecture.com/reference/createaccesstoken)

- [OpenAPI](openapi/fintecture-oauth-api-openapi.yml)
- [Naftiko Capability — Tokens](capabilities/oauth-tokens.yaml)

### Fintecture Resources API
Catalog of supported banks (Providers) with per-bank AIS capabilities (accountholders, accounts, transactions) and PIS rails (SEPA, iSCT, FPS, PLN, INT). Also exposes sandbox test accounts for each bank.

**Human URL:** [Get All Providers](https://doc.fintecture.com/reference/getresv1providers)

- [OpenAPI](openapi/fintecture-resources-api-openapi.yml)
- [Naftiko Capability — Providers](capabilities/resources-providers.yaml)
- [Naftiko Capability — Test Accounts](capabilities/resources-test-accounts.yaml)

### Fintecture Organisation Access Credentials API
Beta multi-tenant management API. Programmatically manage Applications, Bank Accounts, Companies, Organisation Nodes (hierarchical tree), Memberships, and Users in the Fintecture Console. Requires an OAC token with per-resource read/write scopes.

**Human URL:** [Request an OAC access token](https://doc.fintecture.com/docs/request-an-oac-access-token)

- [OpenAPI](openapi/fintecture-oac-api-openapi.yml)
- [Naftiko Capability — Applications](capabilities/oac-applications.yaml)
- [Naftiko Capability — Companies](capabilities/oac-companies.yaml)
- [Naftiko Capability — Organisation Nodes](capabilities/oac-organisation-nodes.yaml)
- [Naftiko Capability — Users](capabilities/oac-users.yaml)
- [Naftiko Capability — Bank Accounts](capabilities/oac-bank-accounts.yaml)

### Fintecture Transactions and Settlements API
Inspect transactions and settlements. Settlements represent outgoing disbursements from the merchant's Local Acquiring account to their own bank account. Sandbox includes a transaction simulator endpoint for testing event flows.

**Human URL:** [Get All Settlements](https://doc.fintecture.com/reference/getpisv2settlements)

- [OpenAPI](openapi/fintecture-transactions-api-openapi.yml)
- [Naftiko Capability — Transactions](capabilities/transactions-transactions.yaml)
- [Naftiko Capability — Simulate Transactions](capabilities/transactions-simulate.yaml)

## Plans, Rate Limits & FinOps

- [Plans & Pricing](plans/fintecture-plans-pricing.yml)
- [Rate Limits](rate-limits/fintecture-rate-limits.yml)
- [FinOps](finops/fintecture-finops.yml)

## SDKs & Sample Code

| Language | Repository |
|---|---|
| JavaScript / TypeScript | [Fintecture/fintecture-sdk-javascript](https://github.com/Fintecture/fintecture-sdk-javascript) |
| Python | [Fintecture/fintecture-sdk-python](https://github.com/Fintecture/fintecture-sdk-python) |
| PHP | [Fintecture/fintecture-sdk-php](https://github.com/Fintecture/fintecture-sdk-php) |
| Ruby | [Fintecture/fintecture-sdk-ruby](https://github.com/Fintecture/fintecture-sdk-ruby) |
| Node.js sample (Express) | [Fintecture/sample-nodejs](https://github.com/Fintecture/sample-nodejs) |
| Ruby on Rails sample | [Fintecture/sample-ror](https://github.com/Fintecture/sample-ror) |
| HTTP Signature reference | [Fintecture/signature-guide](https://github.com/Fintecture/signature-guide) |

## CMS / Plug-in Integrations

PrestaShop, Magento 2, Magento 1.9, Magento Hyva, Shopify, WordPress / WooCommerce, Odoo, Intershop, Oasis. See [CMS Overview](https://doc.fintecture.com/docs/cms-overview).
