# ProtoVia — the commercial evolution

[← Home](../../README.md) · [🇧🇷 Ler em português](../pt-br/protovia.md) · [Hiperion Protocolos](./hiperion-protocolos.md)

**ProtoVia** is the commercial product currently being developed from the technical and operational lessons of Hiperion Protocolos.

Hiperion remains the original public portfolio project, tied to the problem that inspired it. ProtoVia separates the reusable product from that original context: a clean installation starts without Hiperion's companies, users, protocols or credentials and receives the identity of each client organization.

```text
Real problem at Hiperion
        ↓
Hiperion Protocolos — original solution and public portfolio
        ↓
Technical and operational learning
        ↓
ProtoVia — independent commercial product in development
```

## What is different

- Independent setup flow with an installation token and first administrator
- Configurable organization name and logo across the interface, printing and e-mails
- Separate database, credentials, domain and e-mail configuration for each installation
- No fallback to another installation's provisioned database credentials
- Automatic empty-schema creation for SQLite and the hosted Turso mode
- Optional pickup module controlled by administrators
- Its own visual identity, separated from Hiperion's brand
- Automated tests for database isolation, setup protection, login, identity, delivery policies, e-mail rendering, pickup workflow and request lists

## Product direction

The current architecture uses one isolated installation and database per client. It is not being presented as a shared-database multi-tenant SaaS. Before commercial operation, deployment, backup and restoration, monitoring, privacy, signature retention and each client's infrastructure still require proper validation.

ProtoVia demonstrates an important step in my development: moving from solving one organization's problem to thinking about configuration, isolation, installation and repeatability as product requirements.

> **Hiperion proved the workflow. ProtoVia is turning that learning into a product.**

The commercial source repository remains private while the product is under development.

---

[← Hiperion Protocolos](./hiperion-protocolos.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Home](../../README.md)
