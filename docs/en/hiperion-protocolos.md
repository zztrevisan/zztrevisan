# Hiperion Protocolos

[← Home](../../README.md) · [🇧🇷 Ler em português](../pt-br/hiperion-protocolos.md) · [Next: NFSe Hiperion →](./nfse-hiperion.md)

**Hiperion Protocolos** is an internal web application created to replace a paper-based document delivery process with a digital and traceable workflow.

It began as a direct response to an operational problem, not as a technology demonstration. As the real workflow became clearer, the application grew beyond basic CRUD operations and required decisions across the frontend, backend, database and infrastructure.

## What the application covers

- Authentication and session handling
- Users, roles and permission-based access
- Protocol creation and automatic or manual numbering
- Multiple documents and individual expiration dates
- Delivery and cancellation workflows
- Digital signatures
- Logical deletion, history and audit records
- REST API and SQLite persistence
- Installable PWA behavior and a mobile-oriented interface
- Offline operation, a synchronization queue and reconnection handling

Some parts continue to evolve, particularly the mobile experience, infrastructure architecture and production deployment. The project is active learning grounded in a real use case, not a claim that every production concern has already been solved.

## Main stack

`JavaScript` · `Node.js` · `Express` · `SQLite` · `HTML` · `CSS` · `REST API` · `PWA`

## Simplified flow

```text
User
  ↓
Authentication → Role and permissions
  ↓
Create protocol → Attach documents → Deliver and sign
  ↓
REST API → SQLite → History and audit records
```

## Offline and synchronization work

The application needs to remain useful in environments where mobile connectivity may be limited. This led me to work with cached application resources, locally queued operations and later synchronization with the server.

Offline support is not simply an “offline mode” switch. It introduces questions about pending operations, duplicate submissions, ordering, conflicts, user feedback and what should happen when the connection returns. Working through these cases has been one of the project's most valuable technical lessons.

## Infrastructure and testing

Testing on mobile devices exposed network restrictions, firewall limitations and access differences between development machines and the real environment. I experimented with services such as **Vercel, Turso and Cloudflare** for development and external-access tests while evaluating a longer-term local or internal deployment model.

This work reinforced that an application is more than its source code. Reliability also depends on its network, security boundaries, data integrity, deployment strategy and the way real users interact with it.

## What this project is teaching me

- Translating a paper process into explicit software rules
- Modeling roles, permissions and auditable state changes
- Designing APIs around a real workflow
- Handling connectivity as part of application design
- Testing across desktop and mobile environments
- Evaluating local infrastructure and temporary cloud services
- Improving a system through real feedback instead of hypothetical requirements

> **Writing code is only one part of building software.**

---

[← About](./about.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Learning](./learning.md)

