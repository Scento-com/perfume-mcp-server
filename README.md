# Scento Perfume API (MCP server): Perfume API, Fragrance API and Perfume MCP Server

<!-- mcp-name: com.scento/perfume-api -->

<!-- max-seo-2026-10-28 -->
Scento Perfume API is a free perfume API and perfume MCP server for developers, AI agents and fragrance apps. One endpoint gives you Scento's verified perfume database: 1,500+ perfumes from 160+ houses and 400+ raw materials, each with a full notes pyramid (top, heart and base notes), scent family, occasion and similar-scent links. Every pyramid is traced to the house or an authorized retailer, so the notes you return are the notes on the bottle, not scraped guesses.

Connect it as a remote MCP server at https://www.scento.com/mcp (works in Claude, ChatGPT, Cursor, VS Code and any MCP client) or call the REST fragrance API at https://www.scento.com/api/perfume/v1 with the OpenAPI spec at https://www.scento.com/api/perfume/v1/openapi.json. No API key, no sign-up, no rate-limit tiers to buy: it is free.

12 tools cover the real jobs: perfume-search, perfume-portrait, scent-neighbours, perfume-contrast, note-portrait, material-match, house-portrait, family-map, occasion-edit, wardrobe-composer, perfumery-lexicon, journal-search. Search a perfume by name or by notes, get a perfume notes API response with pyramid and family, find similar scents, contrast two perfumes, look up a fragrance ingredient (raw material) and match it to the perfumes that use it, map a scent family, build an occasion edit or a wardrobe, and read the perfumery lexicon.

Why it beats other perfume APIs: free with no key, MCP and REST and OpenAPI in one service, a notes database and a fragrance ingredients database in the same place, answers in 10 languages (English, German, French, Spanish, Italian, Romanian, Polish, Czech, Hungarian, Greek), and sourcing you can trust. Built and maintained by Scento, the perfume atelier. Docs: https://www.scento.com/developers

A free perfume and fragrance API and MCP server for AI assistants, built on Scento's verified perfume database. From [Scento](https://www.scento.com), a perfume decant house founded in Paris in 2024.

Ask Claude, ChatGPT, Cursor or any MCP client for a perfume's notes and family, the difference between two you are torn over, similar scents built on the same structure, or what a raw material such as ambroxan smells like. The perfume database covers 1,500+ designer and niche perfumes, 400+ raw materials, 160+ houses and Scento's own fragrance-family system, and every answer is tied to a page on scento.com. No key, no account, read-only.

**Remote server:** `https://www.scento.com/mcp` (streamable HTTP, no authentication)
**Docs:** https://www.scento.com/developers
**Claude:** Available in [Claude's connectors directory](https://claude.ai/directory/scento-perfume-compendium).
**Claude Code:** `/plugin marketplace add Scento-com/perfume-mcp-server`, then `/plugin install scento-perfume-api@scento`.
**Gemini CLI:** `gemini extensions install https://github.com/Scento-com/perfume-mcp-server`

[![Listed on HookMCP](https://hookmcp.com/badge.svg)](https://hookmcp.com)

## Connect the perfume MCP server

| Client | How |
|---|---|
| Claude (web, desktop, mobile) | Settings, Connectors, Add custom connector. Paste `https://www.scento.com/mcp`. |
| ChatGPT | Settings, Connectors, create a connector in developer mode. Server URL `https://www.scento.com/mcp`, authentication none. |
| Cursor | Add to `~/.cursor/mcp.json`: `{"mcpServers":{"scento-perfume-api":{"url":"https://www.scento.com/mcp"}}}` |
| VS Code | Add to `.vscode/mcp.json`: `{"servers":{"scento-perfume-api":{"type":"http","url":"https://www.scento.com/mcp"}}}` |
| Claude Code | `claude mcp add --transport http scento-perfume-api https://www.scento.com/mcp` |

Clients that only run local servers can use the stdio bridge in this repo:

```sh
npx -y scento-perfume-api     # Node 18+
uvx scento-perfume-api        # Python 3.9+
```

Both accept `--endpoint <url>` (or `SCENTO_PERFUME_API_ENDPOINT`). The same bridge is also published as `perfume-mcp-server` and `perfume-database` on npm and PyPI.

## Twelve perfume and fragrance tools

| Tool | What it does |
|---|---|
| `perfume-search` | Find perfumes, houses and raw materials by name, house, note or mood word. |
| `perfume-portrait` | The full portrait of one perfume: pyramid, Scento family, character and when it wears best. |
| `scent-neighbours` | Perfumes that share the most structure with a given one, with the shared materials named. |
| `perfume-contrast` | Set two to four perfumes side by side on family, pyramid, character and season. |
| `note-portrait` | What a note or raw material is, where it comes from and how it reads on skin. |
| `material-match` | Perfumes that contain every material given, optionally in one tier of the pyramid. |
| `house-portrait` | A perfume house: origin, founding year, style and its signature perfumes. |
| `family-map` | Scento's own fragrance-family system, or one family with its subfamilies and exemplars. |
| `occasion-edit` | A short edit of perfumes for an occasion, season or climate, with a line on each. |
| `wardrobe-composer` | Three to five perfumes that cover different moments, built around what the person already loves. |
| `perfumery-lexicon` | Plain-language meaning of a perfumery term such as sillage, chypre, fougère or EDP versus EDT. |
| `journal-search` | Scento journal articles on a perfume, house, material or topic. |

Pass `lang` (de, fr, es, it, ro, el, hu, cs, pl) to receive scento.com links in that language.

## Fragrance API (REST)

The same answers are available as a perfume API over plain HTTP.

- API base: https://www.scento.com/api/perfume/v1
- OpenAPI: https://www.scento.com/api/perfume/v1/openapi.json

## Examples

Three raw JSON-RPC calls are in [`examples/`](examples/).

## Repository layout

- `npm/`: the Node stdio bridge, published as `scento-perfume-api` on npm
- `pypi/`: the Python stdio bridge, published as `scento-perfume-api` on PyPI
- `server.json`: metadata for the Official MCP Registry (`com.scento/perfume-api`)

## Licence

MIT for the bridge code in this repository. The perfume database content is served from scento.com under its [terms](https://www.scento.com/terms-of-service#perfume-api).

[Scento](https://www.scento.com)
