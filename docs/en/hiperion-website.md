# Hiperion Website

[← Home](../../README.md) · [Ler em português](../pt-br/site-hiperion.md) · [Next: NFSe Hiperion →](./nfse-hiperion.md)

**Hiperion Website** is the complete redesign of the public website of the accounting firm where I work, an office founded in 1969 in São Paulo.

The starting point was a site that worked but said very little: every section used the same template, decoration replaced content, the services never explained what the firm actually delivers, and two announced articles pointed to pages that did not exist.

```text
Before
Generic template → Decoration → Vague services → Broken links

After
Clear positioning → Real deliverables → Curated news with sources → One conversation away
```

## What the project does

- **Guides the visitor by intent.** Right after the hero, three paths (opening a company, already running one, changing accountants) start the conversation at the right point.
- **Explains the work.** Each practice area opens to show what the firm delivers, instead of sending every click straight to WhatsApp.
- **Tells the story through scrolling.** A counter runs from 1969 to the present day while the milestones light up.
- **Shows reach.** A dotted globe highlights Brazil and offers service in Portuguese and English.
- **Publishes useful news.** Insights are curated from official sources, always with the source name, the date and a link to the original.
- **Speaks three languages.** Portuguese, English and Chinese, from a single content file.

## Engineering decisions

- **Next.js, React and TypeScript** for the application, with static pages and incremental revalidation.
- **Three.js** for the 3D bar chart in the hero: a single instanced mesh, heights driven by a wave function plus a pointer bump, and the animation pauses when the section leaves the screen.
- **GSAP with ScrollTrigger and Lenis** for scroll-driven motion, all of it disabled when the visitor prefers reduced motion.
- **Canvas 2D for the globe**, built from a precomputed land mask: the world map never ships to the browser, only a 19 KB file.
- **Light and dark themes** from a single set of CSS variables, with the choice stored in the browser and applied before the first paint.
- **Content out of the code.** Texts live in one file per language, contact details in another, and the news feed can be driven by a published Google Sheet so the team updates the site without touching code or redeploying.

## What this project taught me

- Designing an interface around what the visitor needs to decide, not around what looks impressive
- Keeping animation useful: pausing off-screen work and respecting accessibility preferences
- Precomputing heavy data at build time instead of shipping it to the browser
- Building a theme system with tokens rather than duplicated styles
- Treating content as data, so people who are not developers can maintain the site
- Publishing third-party news responsibly, always with the source and the original link

> **A website should answer what the visitor came to ask.**

---

[← Hiperion Protocolos](./hiperion-protocolos.md) · [ProtoVia](./protovia.md) · [Learning](./learning.md)
