# Site Hiperion

[← Início](../../README.pt-BR.md) · [Read in English](../en/hiperion-website.md) · [Próximo: NFSe Hiperion →](./nfse-hiperion.md)

O **Site Hiperion** é o redesign completo do site público do escritório de contabilidade onde trabalho, fundado em 1969 em São Paulo.

O ponto de partida era um site que funcionava, mas dizia pouco: todas as seções usavam o mesmo molde, o enfeite ocupava o lugar do conteúdo, os serviços não explicavam o que o escritório entrega e dois artigos anunciados levavam a páginas que não existiam.

```text
Antes
Molde genérico → Enfeite → Serviços vagos → Links quebrados

Depois
Posicionamento claro → Entregas reais → Notícias com fonte → Uma conversa de distância
```

## O que o projeto faz

- **Guia o visitante pelo momento dele.** Logo depois do topo, três caminhos (abrir empresa, já ter uma, trocar de contador) começam a conversa no ponto certo.
- **Explica o trabalho.** Cada área abre e mostra o que o escritório entrega, em vez de mandar todo clique direto para o WhatsApp.
- **Conta a história pela rolagem.** Um contador corre de 1969 até hoje enquanto os marcos vão acendendo.
- **Mostra alcance.** Um globo de pontos destaca o Brasil e oferece atendimento em português e inglês.
- **Publica informação útil.** Os Insights são selecionados de fontes oficiais, sempre com o nome da fonte, a data e o link para o original.
- **Fala três idiomas.** Português, inglês e chinês, a partir de um único arquivo de conteúdo.

## Decisões de engenharia

- **Next.js, React e TypeScript** na aplicação, com páginas estáticas e revalidação incremental.
- **Three.js** no gráfico 3D de barras do topo: uma única malha instanciada, alturas geradas por uma função de onda somada a um efeito sob o cursor, e a animação pausa quando a seção sai da tela.
- **GSAP com ScrollTrigger e Lenis** para o movimento ligado à rolagem, tudo desligado quando a pessoa prefere menos animação.
- **Canvas 2D no globo**, a partir de uma máscara de terra pré-calculada: o mapa-múndi nunca vai para o navegador, apenas um arquivo de 19 KB.
- **Temas claro e escuro** com um único conjunto de variáveis CSS, guardando a escolha no navegador e aplicando antes do primeiro desenho da página.
- **Conteúdo fora do código.** Os textos ficam em um arquivo por idioma, os contatos em outro, e as notícias podem vir de uma Planilha do Google publicada, permitindo que a equipe atualize o site sem mexer em código nem publicar de novo.

## O que este projeto me ensinou

- Desenhar a interface a partir do que o visitante precisa decidir, não do que parece impressionante
- Manter a animação útil: pausar o que está fora da tela e respeitar preferências de acessibilidade
- Pré-calcular dados pesados na build em vez de enviá-los ao navegador
- Construir um sistema de temas com variáveis, em vez de estilos duplicados
- Tratar conteúdo como dado, para que pessoas fora do desenvolvimento mantenham o site
- Publicar notícias de terceiros com responsabilidade, sempre com a fonte e o link original

> **Um site precisa responder o que o visitante veio perguntar.**

---

[← Hiperion Protocolos](./hiperion-protocolos.md) · [ProtoVia](./protovia.md) · [Estudos](./estudos.md)
