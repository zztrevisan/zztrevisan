# ProtoVia — a evolução comercial

[← Início](../../README.pt-BR.md) · [🇺🇸 Read in English](../en/protovia.md) · [Hiperion Protocolos](./hiperion-protocolos.md)

A **ProtoVia** é o produto comercial atualmente em desenvolvimento a partir dos aprendizados técnicos e operacionais do Hiperion Protocolos.

O Hiperion permanece como o projeto original e público de portfólio, ligado ao problema que deu origem à ideia. A ProtoVia separa o produto reutilizável daquele contexto inicial: uma instalação nova começa sem empresas, usuários, protocolos ou credenciais da Hiperion e recebe a identidade de cada organização cliente.

```text
Problema real na Hiperion
        ↓
Hiperion Protocolos — solução original e portfólio público
        ↓
Aprendizado técnico e operacional
        ↓
ProtoVia — produto comercial independente em desenvolvimento
```

## O que muda

- Fluxo de instalação independente com token e primeiro administrador
- Nome e logo da organização configuráveis na interface, impressões e e-mails
- Banco, credenciais, domínio e configuração de e-mail separados por instalação
- Ausência de fallback para credenciais de banco provisionadas por outra instalação
- Criação automática de esquema vazio para SQLite e para o modo hospedado com Turso
- Módulo de retiradas opcional, controlado pelo administrador
- Identidade visual própria, separada da marca Hiperion
- Testes automatizados para isolamento do banco, proteção da instalação, login, identidade, políticas de entrega, e-mails, retiradas e listas de solicitações

## Direção do produto

A arquitetura atual utiliza uma instalação e um banco isolados para cada cliente. Ela não é apresentada como um SaaS multi-tenant com banco compartilhado. Antes da operação comercial, implantação, backup e restauração, monitoramento, privacidade, retenção de assinaturas e a infraestrutura de cada cliente ainda precisam de homologação adequada.

A ProtoVia representa um passo importante no meu desenvolvimento: sair da solução de um problema de uma única organização e passar a pensar em configuração, isolamento, instalação e repetibilidade como requisitos de produto.

> **O Hiperion provou o fluxo. A ProtoVia está transformando esse aprendizado em produto.**

O repositório comercial permanece privado enquanto o produto está em desenvolvimento.

---

[← Hiperion Protocolos](./hiperion-protocolos.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Início](../../README.pt-BR.md)
