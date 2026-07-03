# Signaturely (signaturely)

Signaturely is simple electronic signature software for sending, signing, and managing legally binding documents online. In addition to its web application, Signaturely offers a documented public REST API for developers who want to embed and automate signing.

**Does Signaturely have a public API? Yes.** Signaturely exposes a documented REST API at base URL `https://api.signaturely.com/api/v1`. Access is gated behind separately billed **API plans** (Gold, Platinum, Titanium) that are not part of Signaturely's regular subscription plans. You can create API keys and test the API for free; you do not pay until you actually send a signature request.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/signaturely/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/signaturely/refs/heads/main/apis.yml)

## Access Model

- **Base URL:** `https://api.signaturely.com/api/v1`
- **Authentication:** API key sent in the `Authorization: Api-Key {API_KEY}` header. Keys are created and managed in the account API settings at `https://app.signaturely.com/settings/api`.
- **OAuth / Embedded:** OAuth, embedded signing, and embedded requesting are available on the Platinum and Titanium API plans.
- **Plans:** API access is a separate paid product. Gold ($49/mo), Platinum ($99/mo), and Titanium ($199/mo) differ by monthly API signature-request quota and included templates. See `plans/signaturely-plans-pricing.yml`.
- **No-code alternative:** A Zapier integration lets non-developers automate Signaturely without using the API directly.
- **No "contacts" resource:** Signaturely's API has no standalone contacts endpoint. Signers (name + email) are supplied inline on each signature request or in the bulk-send CSV.

## Tags

- Electronic Signature
- eSignature
- Document Signing
- E-Signature API
- Contracts
- Signature Requests
- SaaS

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Signaturely Signature Requests API

Create signature requests by populating a saved template with signers and field values, and bulk-send a single-signer template against CSV data to generate many signature requests at once.

- **Base URL:** `https://api.signaturely.com/api/v1`
- `POST /document_sign/api/request_by_template` — create a signature request from a template
- `POST /document_sign/api/bulk_send` — bulk-send a single-signer template using CSV data

### Signaturely Documents API

List, download, share, remind on, and manage documents.

- `GET /documents` — list documents
- `DELETE /documents` — delete a document
- `GET /documents/{documentId}/signers` — list a document's signers
- `GET /documents/{id}/activities` — document activity log
- `PATCH /documents/{documentId}/revert` — revert a document
- `GET /document_sign/documents/{documentId}/signed_download_url/api` — signed-document download URL
- `GET /document_sign/documents/{id}/share_url` — get a shareable signing link
- `POST /document_sign/documents/{id}/share` — share a document
- `POST /document_sign/documents/{id}/send_reminders` — send signing reminders
- `GET /api-integrations/recent_document?recentDocumentType=sent` — most recent sent document

### Signaturely Templates API

Work with the reusable templates that signature requests are generated from.

- `GET /documents/api/templates` — list templates
- `DELETE /documents/api/templates` — delete a template
- `GET /document_sign/documents/{templateId}/signed_download_url/api` — download a template file

### Signaturely Folders API

Organize documents and folders.

- `POST /api-integrations/folders` — create a folder
- `GET /api-integrations/folders` — list folders (paginated)
- `GET /api-integrations/folders/{id}` — get a folder
- `PATCH /api-integrations/folders/{id}` — rename a folder
- `PATCH /api-integrations/folders/move` — move documents/folders into a folder

### Signaturely Team API

Manage team members directly via the API.

- `GET /teams/members` — list team members
- `POST /add-teammates/with-role` — add a team member with a role
- `PATCH /teams/members/role` — change a team member's role
- `DELETE /remove-teammates/email` — remove a team member by email

### Signaturely Webhooks API

Subscribe to document lifecycle events.

- `POST /hooks/subscribe` — subscribe a webhook URL (events: `document_sent`, `document_completed`)
- `POST /hooks/unsubscribe` — unsubscribe a webhook URL

### Signaturely User API

- `GET /user/by-api` — get the user account tied to your API key

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/signaturely)
- [Website](https://signaturely.com)
- [Documentation](https://docs.signaturely.com/)
- [API Overview](https://signaturely.com/api)
- [Help Center - API](https://help.signaturely.com/category/53-api)
- [Plans](plans/signaturely-plans-pricing.yml)
- [Rate Limits](rate-limits/signaturely-rate-limits.yml)
- [Fin Ops](finops/signaturely-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
