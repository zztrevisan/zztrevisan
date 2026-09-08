# Hiperion Protocolos

[← Início](../../README.pt-BR.md) · [🇺🇸 Read in English](../en/hiperion-protocolos.md) · [Próximo: NFSe Hiperion →](./nfse-hiperion.md)

O **Hiperion Protocolos** é uma aplicação web interna criada para substituir um processo de entrega de documentos em papel por um fluxo digital e rastreável.

Ele nasceu como resposta direta a um problema operacional, não como demonstração de tecnologia. Conforme o fluxo real ficou mais claro, a aplicação foi além de operações básicas de CRUD e passou a exigir decisões no frontend, backend, banco de dados e infraestrutura.

## O que a aplicação abrange

- Autenticação e controle de sessões
- Usuários, papéis e acesso baseado em permissões
- Criação de protocolos e numeração automática ou manual
- Múltiplos documentos e datas de validade individuais
- Fluxos de entrega e cancelamento
- Assinaturas digitais
- Exclusão lógica, histórico e registros de auditoria
- API REST e persistência com SQLite
- Comportamento de PWA instalável e interface voltada a dispositivos móveis
- Operação offline, fila de sincronização e tratamento da reconexão

Algumas áreas continuam evoluindo, principalmente a experiência móvel, a arquitetura de infraestrutura e a implantação em produção. O projeto representa aprendizado ativo sobre um caso real, e não a afirmação de que todos os desafios de produção já foram resolvidos.

## Stack principal

`JavaScript` · `Node.js` · `Express` · `SQLite` · `HTML` · `CSS` · `API REST` · `PWA`

## Fluxo simplificado

```text
Usuário
  ↓
Autenticação → Papel e permissões
  ↓
Criar protocolo → Anexar documentos → Entregar e assinar
  ↓
API REST → SQLite → Histórico e auditoria
```

## Trabalho offline e sincronização

A aplicação precisa continuar útil em ambientes nos quais a conectividade móvel pode ser limitada. Isso me levou a trabalhar com recursos da aplicação em cache, operações enfileiradas localmente e sincronização posterior com o servidor.

Suporte offline não é apenas ligar um “modo offline”. Ele traz perguntas sobre operações pendentes, envios duplicados, ordem de execução, conflitos, retorno visual para o usuário e o que deve acontecer quando a conexão volta. Trabalhar nesses casos tem sido uma das lições técnicas mais valiosas do projeto.

## Infraestrutura e testes

Os testes em dispositivos móveis revelaram restrições de rede, limitações de firewall e diferenças de acesso entre a máquina de desenvolvimento e o ambiente real. Experimentei serviços como **Vercel, Turso e Cloudflare** para desenvolvimento e testes de acesso externo enquanto avalio um modelo de implantação local ou interno no longo prazo.

Esse trabalho reforçou que uma aplicação é mais do que seu código-fonte. A confiabilidade também depende da rede, dos limites de segurança, da integridade dos dados, da estratégia de implantação e da maneira como usuários reais interagem com o sistema.

## O que este projeto está me ensinando

- Traduzir um processo em papel em regras explícitas de software
- Modelar papéis, permissões e mudanças de estado auditáveis
- Projetar APIs em torno de um fluxo real
- Tratar conectividade como parte do projeto da aplicação
- Testar em ambientes desktop e mobile
- Avaliar infraestrutura local e serviços temporários em nuvem
- Melhorar um sistema por meio de feedback real, não apenas requisitos hipotéticos

> **Escrever código é apenas uma parte de construir software.**

---

[← Sobre](./sobre.md) · [NFSe Hiperion](./nfse-hiperion.md) · [Estudos](./estudos.md)

