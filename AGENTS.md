# Documentation project instructions

## About this project

- This is the public documentation site for **Thea**, an AI Discord support and moderation product.
- Pages are MDX files with YAML frontmatter.
- Configuration lives in `docs.json`.
- Source of truth for product behavior is the application at `D:\Code\discord-bot`, not marketing copy.

## Terminology

- Use **Thea** for the product. You can say "the bot" when describing Discord behavior.
- Use **server**, not "guild", in user-facing docs.
- Use **member** for people in a Discord server. Use **staff** or **moderators** for the server team.
- Use **dashboard** for the web app at theabot.com.
- Dashboard paths: **Knowledge**, **Playground**, **Conversations**, **Tickets**, **Help Center**, **Scam defense**, **Settings → Answering**, **Settings → Handoff**, and so on. Do not invent section names such as Guardrails.
- Confidence is a number from **0 to 1**, default **0.35**. Do not describe it as a 0–100 percentage slider.
- Saved replies are sent with `/macro send`, not `/reply`.
- Billing is **per Discord server**.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Do not invent features, dashboard paths, or commands that are not in the product
- Never stack callouts. One alert per section. Fold extra notes into body text or a step.
