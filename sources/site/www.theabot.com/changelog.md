# Source: https://www.theabot.com/changelog

Updates

# Changelog

Last updated: August 27, 2026

Faster, Safer, Clearer

### A Faster Dashboard and Safer Automation

This release makes Thea easier to operate and harder to overwhelm. The dashboard is clearer, expensive work spends less time holding database connections, and moderation and raid controls now preserve better evidence while remaining reliable under concurrency.

### Dashboard and settings

- Dashboard navigation now stays visible while you scroll, content and billing frames use the wider settings layout, and keyboard users get a direct skip-to-content link
- Settings open on General by default, invalid section links recover safely, and each section loads only the Discord and database data it needs
- AutoMod, raid protection, onboarding, logging, tickets, answering, and welcome settings now use clearer internal sections, descriptive multi-select controls, and inline plan or permission limits
- Ticket response and satisfaction statistics and AutoMod channel coverage now open in dedicated sheets instead of crowding their queues
- The Playground is now a full conversation tester with sample questions, multiline input, Enter-to-send, clearable history, per-answer run diagnostics, and specific errors for rate limits, spend caps, configuration, and validation
- Backup and cloning workflows now have clearer source and destination controls, optional pasted JSON, unresolved-reference handling, and a structured preview before any configuration is replaced
- The Content API now has an in-dashboard reference covering authentication, request fields, examples, responses, indexing behavior, related endpoints, quotas, and rate limits

### Moderation and raid protection

- AutoMod review flags retain the text that was actually scanned, including forwarded messages, embeds, polls, attachment filenames, and sticker names; media-only evidence is labelled and snapshots remain redacted and size-limited
- A later matching incident can fill previously blank evidence, while borderline messages receive at most one paid classifier judgment
- User, channel, and server rate limits now update in one atomic Redis operation, preventing concurrent bot instances from racing cooldowns, strikes, or shared budgets
- Raid verification lookups are briefly cached and simultaneous checks are coalesced, reducing database load during message floods without delaying verification changes

### Answers, retrieval, and operations

- Embedding, retrieval, reranking, generation, and duplicate checks no longer keep tenant database transactions open while waiting on model providers
- Knowledge availability now uses an early-exit existence check, and document and curated-answer lookups are scheduled together
- Large embedding jobs are processed in ordered batches of 96 with combined token accounting, avoiding oversized provider requests while preserving result order
- Server overview and alert data now share lightweight cached snapshots, reducing repeated account, billing, usage, spend, and alert queries without changing alert coverage
- Background Discord alert workloads have configurable per-sweep batch limits, reducing janitor head-of-line blocking while preserving workload order and cadence
- Serverless web processes no longer start the authentication keepalive timer
- Decorative marketing effects pause when hidden, backgrounded, or reduced motion is requested, and reduced-motion headings remain fully readable without animation

One Panel, Another Channel

### Reminders That Land Where People Are Looking

The onboarding panel wants a quiet channel it can sit in for months. The reminder wants the channel your server actually reads. Those were the same channel, and they should not have been.

- The panel stays where you put it; members are now tagged somewhere else — your general chat, or wherever your server talks
- Reminders repeat on a schedule you pick, up to twice a day, for members who arrived and never finished
- One message per reminder tagging everyone still outstanding, not one message each, so a busy week does not bury the channel
- Reminders stop seven days after a member arrives, whichever interval you chose. A daily ping with no end is how a bot gets muted, and they can still finish from the panel whenever they like
- Nobody is tagged once they have completed the form, and nothing is sent while raid mode is holding the door
- The arrival tag no longer deletes itself after five minutes: it now stays put, because a mention that vanishes leaves members with a notification pointing at nothing

Ask, Keep Nothing

### Onboarding, and the Answers Thea Doesn't Keep

New members arrive and you have questions of your own. Thea can now ask them — an email address, an order number, or nothing more involved than "I've read the rules" — and hand the answers straight to your staff. What it will not do is keep them.

- Onboarding forms: new members press one button and answer up to five questions you write, in a Discord dialog rather than a DM
- Answers are posted to a staff channel you choose and stored nowhere else, so there is no copy of your members' details on our side to leak or lose — and none for us to hand back, which is the trade
- A role granted on completion, so the form can gate the rest of the server; it is re-checked at the moment it is granted, so a role that quietly gained moderator powers last month stops being handed out
- Rules-acknowledgment mode: no questions at all, where pressing the button is the whole thing
- Questions asking for passwords, login codes, payment details or identity documents are refused outright — members read that form inside Thea's own dialog, and no server gets to phish from behind our name
- A form that asks for an email address or a phone number cannot send its answers to a channel `@everyone` can read
- Each arrival gets one nudge pointing at the panel, and staff get one message about the members who never finished — once each, never a repeat
- Fits around Discord's own membership screening, and stays quiet while raid mode is holding the door

Every Ticket, Answered

### Support That Answers Back

The support half of Thea grew up. Tickets now have owners, notes, canned replies and a clock that chases the ones nobody answered — and everyone who opens one keeps a copy. AutoMod learned to read the things it used to miss, and anyone it gets wrong can finally ask a human to look again.

- Ticket transcripts sent to the member on close, and downloadable by staff — a deleted channel no longer takes the record with it
- Claim and assign tickets so two agents never work the same one; staff notes keep handover context on the ticket instead of a side channel
- A response-time target that re-pings your support role when an escalated ticket goes unanswered, plus a satisfaction rating on close so you can see whether support is good, not just busy
- Saved replies with autocomplete, and reopening a closed ticket when "actually, it's still broken"
- AutoMod reads image attachments, QR codes, forwarded messages, embeds and stickers — and rescans a message that was edited after posting
- Members punished by AutoMod can request a review, even after a kick or ban; staff rulings surface a false-positive rate you can tune against
- Server logs for deletes, edits, joins, leaves and bans, in channels you choose
- Suspicious usernames screened at join, moderator notes and a watchlist that survives a shift change, and moderation records exportable as CSV
- Welcome messages with a role granted once a newcomer clears raid verification
- Announcements with embeds and repeating schedules; server settings exportable and cloneable to another server
- Email where the bot used to go quiet: approaching your plan limit, a failed payment, a paused knowledge source

Raid Ready

### Raid Protection, and an AutoMod That Shows Its Work

This update hardens the front door and turns the lights on. Thea now catches join raids as they form, pools scam intelligence across servers, and accounts for every moderation decision — including the ones it could not carry out.

- Raid protection: join-surge and content-storm detectors with alert and auto modes, an emoji-captcha gate for unverified newcomers, and `/raid` commands for manual control
- Community scam list pooled across Thea servers, and scam links now match your blocklists even when pasted without `http://`
- `/automod test` shows which layers are on, whether you are exempt, and what a sample message would trigger
- Actions AutoMod intended but could not complete — a missing permission, no log channel — now appear in the review queue instead of disappearing
- Severity icons on alerts and warnings, in Discord and on the dashboard
- Custom ticket form fields, so tickets open with the details your staff need
- Account-wide billing: every billed server in one place, with invoice history and saved payment methods
- Live server stats page, and email-verified signups

Beyond Answers

### Moderation, Tickets, and a Help Center

Thea now handles the rest of the support job, not just the questions. The same install moderates the room in layers, runs your ticket queue with triage attached, and publishes your indexed docs as a searchable help center.

- Layered AutoMod: Discord-native rules, spam and scam-link heuristics, the moderation API, then an AI pass judged against rules you write
- Per-severity actions from log-only up to a timeout, with quarantine review buttons in your log channel
- Repeat-offender escalation ladder you configure; members audit their own record with `/standing`
- Moderator commands — warn, timeout, kick, ban, softban, purge, and channel lock — sharing one ledger with automatic actions
- Tickets in private channels, triaged by category, urgency, and sentiment, then routed to the role that owns them
- Help center with collections, search, and your own domain on paid plans
- Scheduled announcements, weekly staff digests, and knowledge-gap clustering

Thea 1.0

### Thea 1.0: Grounded Answers for Everyone

Thea is out of beta. Every server gets grounded answers with citations, confidence-gated handoffs, and a dashboard that shows exactly what your members are asking.

- Cited answers in threads, linked to the exact source passage
- Confidence threshold with automatic moderator escalation
- Knowledge dashboard for URL, sitemap, and FAQ sources
- Playground to rehearse real questions before launch
- Activity analytics: questions, helpfulness, time-to-answer

Verified Answers

### Verified Answers and Smarter Escalations

Moderators can now bless a reply as the canonical answer, and handoffs carry everything a human needs to pick up the thread without re-reading it.

- Pin a reviewed reply as the verified answer for a question
- Verified answers outrank raw doc passages at answer time
- Escalation pings include the full thread and cited sources
- Per-channel confidence thresholds
- Guardrail presets for tone and scope

Fresher Sources

### Source Sync, Without the Babysitting

Connected docs now stay fresh on their own. Thea re-crawls on a schedule, fetches only what changed, and tells you when a source breaks instead of answering from stale pages.

- Scheduled re-syncs for every connected source
- Sitemap crawls fetch only changed pages
- Broken-source alerts in the knowledge dashboard
- Passage counts and last-synced times per source
- Faster indexing for large wikis