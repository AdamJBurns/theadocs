# Thea documentation

Public docs for [Thea](https://www.theabot.com) — an AI Discord support and moderation product.

Built with [Mintlify](https://mintlify.com). Product source of truth is the application repo (`discord-bot`), not marketing copy.

## Preview locally

```bash
npm i -g mint
mint dev
```

Open `http://localhost:3000`.

## Writing

- Pages are MDX with YAML frontmatter (`title`, `description`, `sidebarTitle`).
- Add every new page to `docs.json` or it will not appear in the sidebar.
- Internal links are root-relative without a file extension: `/answering/how-it-works`.
- Voice: second person, sentence-case headings, bold UI labels.
- Do not invent dashboard paths or commands. See `AGENTS.md`.
