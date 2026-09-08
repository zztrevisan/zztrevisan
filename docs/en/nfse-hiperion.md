# NFSe Hiperion

[← Home](../../README.md) · [🇧🇷 Ler em português](../pt-br/nfse-hiperion.md) · [Next: Journey →](./journey.md)

**NFSe Hiperion** is a business process automation project focused on reducing repetitive work with municipal service invoice documents.

The original process requires a user to access a system, choose a company and period, download the available files, organize them and repeat the same sequence for other companies. The project's goal is to turn that repeated interaction into a predictable workflow.

```text
Manual process
Access → Select company → Select period → Download → Organize → Repeat

Target workflow
One action → Automation → Process companies → Organized file structure
```

## Main goals

- Reduce repetitive navigation and downloads
- Process more than one company in a consistent way
- Organize documents by company and period
- Make progress and failures visible to the user
- Produce a repeatable process that is easier to verify

## Engineering considerations

Automation has to handle more than the successful path. The project involves studying authentication flows, changing interfaces, download validation, naming and folder rules, retries, logs and clear error reporting.

Because the solution is still evolving, I describe it by its problem and direction instead of presenting unfinished decisions as production-ready features. It has also encouraged me to explore automation approaches outside my primary JavaScript stack when the problem calls for them.

## What this project is teaching me

- Breaking a manual routine into deterministic steps
- Separating configuration from execution logic
- Designing useful logs and failure messages
- Validating outputs rather than assuming a download succeeded
- Treating maintainability as part of automation
- Choosing tools based on the workflow instead of habit

> **Turn repetitive operational work into a predictable automated process.**

---

[← Hiperion Protocolos](./hiperion-protocolos.md) · [Journey](./journey.md) · [Learning](./learning.md)

