# Documentation project instructions

## About this project

- This is the Coconut documentation site, built on [Mintlify](https://mintlify.com) and published at [docs.coconut.md](https://docs.coconut.md).
- Pages are MDX files with YAML frontmatter. Navigation lives in `docs.json`.
- The public marketing site is [coconut.dev](https://www.coconut.dev); the app is [app.coconut.md](https://app.coconut.md). These docs should complement [coconut.dev/developers](https://www.coconut.dev/developers), not duplicate it.
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP.
- Run `npx mint@latest broken-links` before finishing any change that adds or moves a page.

## Terminology

Use these terms exactly. They match the product surface and the company's messaging.

| Use | Not |
| --- | --- |
| Coconut (product), Coconut AI Inc. (company) | Coco, coconut.dev, the platform |
| context layer, shared context layer | knowledge base, wiki, document store |
| space | workspace, project, folder |
| page | document, article, note |
| shared space / personal space | public space / private space |
| page metadata | tags, properties, attributes |
| record type (a template declaring a `metadataSchema`) | model, schema object, content type |
| space agent | bot, assistant, copilot |
| connector | integration, plugin |
| organization, org | tenant, account, company (in product context) |
| agent key, agent token | API key (when referring to Coconut credentials) |

`Coco` appears only inside technical identifiers that really are spelled that way: `coco` (the CLI binary), `coconut-sdk`, `COCO_*` environment variables, and `X-Coco-*` headers. Never in prose.

## Voice

The company voice guide is the source of truth, at [`social/voices/coconut`](https://app.coconut.md/pages/social/voices/coconut). Read it before writing anything substantial. Its hard rules apply to docs:

- **No em dashes, ever.** Use a comma, a colon, or a full stop.
- **No hype.** Never "revolutionary", "game-changing", "unleash", "supercharge", "seamless", "cutting-edge", "powerful", "effortless". Also avoid "finally" and "at last".
- **American spelling.**
- **Titles are plain nouns or questions.** "Record types", not "Why You Need Record Types".
- **Measured, not breathless.** Authority comes from precision, not adjectives.
- **Ground abstractions in real failure.** Not "metadata can drift" but "a pipeline accumulates `diligence`, `Diligence`, and `in diligence` until no query is trustworthy".
- **Don't dunk on competitors.**

Docs are reference writing, not blog writing. The voice guide's blog skeleton (one-sentence definition opener, a single thesis blockquote, a "bottom line" close) is not required here. What carries over is the tone, the vocabulary, and the hard style rules above.

## Style preferences

- Active voice and second person ("you").
- One idea per sentence. Sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Code formatting for file names, commands, paths, environment variables, and API routes.
- Lead a page with what the thing is and when to reach for it, before how to configure it.
- Prefer a table to a long run of bullets when the items share a shape.
- Show runnable commands, not pseudo-code. A query example should be a real `coco query` invocation or a real filter JSON payload, never invented syntax like `stage = "x" AND score < 0.5`.

## Content boundaries

- **Never reference private repository paths.** No `specs/*.md`, `packages/...`, `infra/...`, `ROADMAP.md`, or `DECISIONS.md`. Readers cannot open them. Link to a public docs page instead, or explain the thing inline.
- Self-hosted operational commands (`./scripts/compose-local.sh`, `pnpm db:migrate`) are fine on Operations pages, where the reader has the distribution.
- Don't document unreleased features, internal admin tooling, or per-customer configuration.
- Examples use `https://api.coconut.md` and `$COCO_API_KEY`. Only the self-hosted quickstart uses `http://localhost:8787` and the seeded `dev-agent-key-change-me`.

## Keeping tool docs accurate

`/tools/cli` and `/tools/sdk` describe two published packages. When either ships a change to its command surface, filter syntax, error types, or exit codes, update these docs in the same cycle.

- CLI: [`lovelybunch/coconut-cli`](https://github.com/lovelybunch/coconut-cli) (npm `coconut`, binaries `coco` and `coconut`)
- SDK: [`lovelybunch/coconut-sdk`](https://github.com/lovelybunch/coconut-sdk) (npm `coconut-sdk`), whose `openapi.yaml` is the source of truth for the REST contract

Metadata filter operators are documented in five places and must agree: `/concepts/page-metadata`, `/concepts/records`, `/api-reference/search`, `/tools/cli`, and `/tools/sdk`.
