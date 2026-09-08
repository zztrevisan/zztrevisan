# Hiperion Protocolos — where the product began

[← Home](../../README.md) · [🇧🇷 Ler em português](../pt-br/hiperion-protocolos.md) · [View repository ↗](https://github.com/zztrevisan/ProtocolosHiperion) · [Next: ProtoVia →](./protovia.md)

**Hiperion Protocolos** is the original project: the system that emerged after I identified a real operational problem at my current workplace, Hiperion Assessoria Contábil. Document deliveries depended on paper controls, and I saw an opportunity to turn that routine into software.

What started as a way to register deliveries became an end-to-end operational system. It is now my public portfolio version: a working record of how I translated a real process into rules, permissions, interfaces, evidence and infrastructure. Its commercial evolution is being developed separately as **[ProtoVia](./protovia.md)**.

[**Open the Hiperion Protocolos public repository →**](https://github.com/zztrevisan/ProtocolosHiperion)

## More than a protocol CRUD

- **Unified requests:** every authenticated profile can start a new protocol or request a document pickup from the same flow.
- **Protocol lifecycle:** creation, automatic or manual numbering, multiple documents, individual due dates, assignment, delivery, cancellation and recoverable deletion.
- **Pickup workflow:** request documents from a company, assign a courier, register collection and complete an office-side document-by-document review.
- **QR Code confirmation:** labels carry a QR Code used to validate the correct protocol at delivery, with an emergency manual-number alternative controlled by administrators.
- **Delivery evidence:** recipient name, digital signature, confirmation method, server timestamps and optionally GPS or a required justification.
- **Configurable policies:** administrators decide whether GPS is disabled, mandatory or replaceable by justification, whether QR validation is required and whether manual confirmation is allowed.
- **Roles and permissions:** administrator, issuer, courier and explicit department exceptions, enforced by the server rather than only hidden in the interface.
- **Offline-capable PWA:** cached resources, queued delivery operations, synchronization after reconnection and server-side revalidation of the preserved evidence.
- **Communication:** notifications for new assignments, delivery receipts and alerts for documents nearing expiration, with delivery status and errors recorded.
- **Physical operation:** A4 protocols, QR labels, envelopes and print flows bridge the digital system with documents that still move physically.
- **Traceability:** history, audit records, conditional state transitions and completed pickup reviews that cannot simply be overwritten.
- **Two operating modes:** Express API with Vercel/Turso in the hosted version or an internal server with SQLite, plus migration, backup and environment-verification scripts.

This is why Hiperion matters in my portfolio: it demonstrates not just screens, but the relationship between a business rule, the user who is allowed to act, the state stored in the database, the evidence produced and the conditions of the real environment.

## Main stack

`JavaScript` · `Node.js` · `Express` · `SQLite` · `Turso` · `HTML` · `CSS` · `REST API` · `PWA` · `Service Worker` · `QR Code` · `Resend`

## Simplified flow

```text
User
  ↓
Authentication → Role and permissions
  ↓
New request → Protocol or document pickup
  ↓
Assign responsibility → Track state → Validate action
  ↓
QR / signature / evidence → Complete or synchronize
  ↓
REST API → SQLite or Turso → History and audit records
```

## Offline and synchronization work

The application needs to remain useful in environments where mobile connectivity may be limited. This led me to work with cached application resources, locally queued operations and later synchronization with the server.

Offline support is not simply an “offline mode” switch. It introduces questions about pending operations, duplicate submissions, ordering, conflicts, user feedback and what should happen when the connection returns. Working through these cases has been one of the project's most valuable technical lessons.

## Infrastructure, security and testing

Testing on mobile devices exposed network restrictions, firewall limitations and access differences between development machines and the real environment. I worked with **Vercel, Turso and Cloudflare** for hosted access while also preparing internal operation with SQLite, environment verification, migration and backup routines.

The API uses protected session cookies, server-side RBAC, origin validation, rate limiting, salted password derivation and environment-based secrets. Automated tests cover delivery policies, pickup state transitions and request-list behavior without using operational data.

This work reinforced that an application is more than its source code. Reliability also depends on its network, security boundaries, data integrity, deployment strategy and the way real users interact with it.

## What this project is teaching me

- Translating a paper process into explicit software rules
- Modeling roles, permissions and auditable state changes
- Designing APIs around a real workflow
- Handling connectivity as part of application design
- Connecting QR Codes, signatures, GPS policy and immutable evidence
- Designing safe transitions for pickup and office review workflows
- Testing across desktop and mobile environments
- Supporting both hosted and internal infrastructure
- Improving a system through real feedback instead of hypothetical requirements

> **Writing code is only one part of building software.**

---

[← About](./about.md) · [ProtoVia](./protovia.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Repository ↗](https://github.com/zztrevisan/ProtocolosHiperion)
