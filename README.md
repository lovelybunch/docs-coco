# Coconut documentation

The source for [docs.coconut.md](https://docs.coconut.md), the technical documentation for Coconut, the shared context layer for AI tools and agents.

Built on [Mintlify](https://mintlify.com). Pages are MDX with YAML frontmatter, and navigation lives in `docs.json`.

## Local preview

```bash
npm i -g mint
mint dev
```

Run it from the repository root, where `docs.json` lives. The preview is at `http://localhost:3000`.

## Before you open a pull request

```bash
npx mint@latest broken-links
```

Read [`AGENTS.md`](AGENTS.md) first. It carries the terminology, the voice rules, and the content boundaries this site is written to, and it applies to people and coding agents alike.

## Publishing

The Mintlify GitHub app deploys `main` automatically. Pull requests get a preview deployment.

## Related

| Repository | What it is |
| --- | --- |
| [`coconut-cli`](https://github.com/lovelybunch/coconut-cli) | The `coco` command-line client (npm `coconut`) |
| [`coconut-sdk`](https://github.com/lovelybunch/coconut-sdk) | The TypeScript client and the `openapi.yaml` REST contract |

## License

[Apache-2.0](LICENSE) © Coconut AI Inc.
