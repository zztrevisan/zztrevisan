# Hiperion Protocolos — onde o produto começou

[← Início](../../README.pt-BR.md) · [🇺🇸 Read in English](../en/hiperion-protocolos.md) · [Acessar repositório ↗](https://github.com/zztrevisan/ProtocolosHiperion) · [Próximo: ProtoVia →](./protovia.md)

O **Hiperion Protocolos** é o projeto original: o sistema que surgiu quando identifiquei um problema operacional real no meu trabalho atual, na Hiperion Assessoria Contábil. As entregas de documentos dependiam de controles em papel, e eu enxerguei a oportunidade de transformar aquela rotina em software.

O que começou como uma forma de registrar entregas tornou-se um sistema operacional de ponta a ponta. Hoje, ele é minha versão pública de portfólio: um registro funcional de como transformei um processo real em regras, permissões, interfaces, evidências e infraestrutura. Sua evolução comercial está sendo desenvolvida separadamente como **[ProtoVia](./protovia.md)**.

[**Abrir o repositório público do Hiperion Protocolos →**](https://github.com/zztrevisan/ProtocolosHiperion)

## Muito além de um CRUD de protocolos

- **Solicitações unificadas:** todo perfil autenticado pode iniciar um novo protocolo ou solicitar a retirada de documentos pelo mesmo fluxo.
- **Ciclo completo do protocolo:** criação, numeração automática ou manual, múltiplos documentos, vencimentos individuais, atribuição, entrega, cancelamento e exclusão recuperável.
- **Fluxo de retiradas:** solicitar documentos de uma empresa, atribuir entregador, registrar a coleta e concluir no escritório uma conferência documento por documento.
- **Confirmação por QR Code:** etiquetas levam um QR Code que valida o protocolo correto na entrega, com alternativa emergencial por número controlada pelo administrador.
- **Evidência de entrega:** nome do recebedor, assinatura digital, método de confirmação, horários do servidor e, opcionalmente, GPS ou justificativa obrigatória.
- **Políticas configuráveis:** o administrador define se o GPS fica desligado, obrigatório ou substituível por justificativa, se o QR é exigido e se a confirmação manual é permitida.
- **Papéis e permissões:** administrador, emissor, entregador e exceções explícitas por departamento, aplicados no servidor e não apenas escondidos na interface.
- **PWA com suporte offline:** recursos em cache, operações de entrega enfileiradas, sincronização após reconexão e revalidação das evidências preservadas pelo servidor.
- **Comunicação:** avisos de novas atribuições, comprovantes de entrega e alertas de documentos próximos do vencimento, com status e erros registrados.
- **Operação física:** protocolos A4, etiquetas com QR Code, envelopes e fluxos de impressão conectam o sistema digital aos documentos que ainda circulam fisicamente.
- **Rastreabilidade:** histórico, auditoria, transições condicionais de estado e conferências concluídas que não podem ser simplesmente sobrescritas.
- **Dois modos de operação:** API Express com Vercel/Turso na versão hospedada ou servidor interno com SQLite, além de rotinas de migração, backup e verificação do ambiente.

É por isso que o Hiperion tem peso no meu portfólio: ele demonstra não apenas telas, mas a relação entre uma regra de negócio, o usuário autorizado a agir, o estado salvo no banco, a evidência produzida e as condições do ambiente real.

## Stack principal

`JavaScript` · `Node.js` · `Express` · `SQLite` · `Turso` · `HTML` · `CSS` · `API REST` · `PWA` · `Service Worker` · `QR Code` · `Resend`

## Fluxo simplificado

```text
Usuário
  ↓
Autenticação → Papel e permissões
  ↓
Nova solicitação → Protocolo ou retirada de documentos
  ↓
Atribuir responsável → Acompanhar estado → Validar ação
  ↓
QR / assinatura / evidência → Concluir ou sincronizar
  ↓
API REST → SQLite ou Turso → Histórico e auditoria
```

## Trabalho offline e sincronização

A aplicação precisa continuar útil em ambientes nos quais a conectividade móvel pode ser limitada. Isso me levou a trabalhar com recursos da aplicação em cache, operações enfileiradas localmente e sincronização posterior com o servidor.

Suporte offline não é apenas ligar um “modo offline”. Ele traz perguntas sobre operações pendentes, envios duplicados, ordem de execução, conflitos, retorno visual para o usuário e o que deve acontecer quando a conexão volta. Trabalhar nesses casos tem sido uma das lições técnicas mais valiosas do projeto.

## Infraestrutura, segurança e testes

Os testes em dispositivos móveis revelaram restrições de rede, limitações de firewall e diferenças de acesso entre a máquina de desenvolvimento e o ambiente real. Trabalhei com **Vercel, Turso e Cloudflare** no acesso hospedado enquanto também preparava a operação interna com SQLite, verificação de ambiente, migração e rotinas de backup.

A API usa cookies de sessão protegidos, RBAC no servidor, validação de origem, rate limiting, derivação de senhas com salt e segredos por variáveis de ambiente. Os testes automatizados cobrem políticas de entrega, transições do fluxo de retiradas e comportamento das listas de solicitações sem utilizar dados operacionais.

Esse trabalho reforçou que uma aplicação é mais do que seu código-fonte. A confiabilidade também depende da rede, dos limites de segurança, da integridade dos dados, da estratégia de implantação e da maneira como usuários reais interagem com o sistema.

## O que este projeto está me ensinando

- Traduzir um processo em papel em regras explícitas de software
- Modelar papéis, permissões e mudanças de estado auditáveis
- Projetar APIs em torno de um fluxo real
- Tratar conectividade como parte do projeto da aplicação
- Conectar QR Code, assinatura, regras de GPS e evidências imutáveis
- Projetar transições seguras para retirada e conferência no escritório
- Testar em ambientes desktop e mobile
- Sustentar infraestrutura hospedada e interna
- Melhorar um sistema por meio de feedback real, não apenas requisitos hipotéticos

> **Escrever código é apenas uma parte de construir software.**

---

[← Sobre](./sobre.md) · [ProtoVia](./protovia.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Repositório ↗](https://github.com/zztrevisan/ProtocolosHiperion)
