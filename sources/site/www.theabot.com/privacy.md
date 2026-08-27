# Source: https://www.theabot.com/privacy

Legal

# Privacy Policy

Last updated August 6, 2026

## What We Collect

**Discord account.** When you sign in we receive your Discord ID, username, avatar, and the email address on your Discord account via OAuth, and we read the list of servers you manage so the dashboard knows which ones to show. Servers where Thea is not installed are not stored, OAuth tokens are encrypted at rest with AES-256-GCM, and we never see your Discord password.

**Email.** We ask you to confirm your email address with a mailed code before the dashboard opens. It is used for account security (confirming a deletion), official notices, and service status announcements — never marketing, and never shared. The content of a notice is never put in an email; the email only tells you one is waiting.

**Server data.** For servers you connect: the server name, ID, icon, and the channel configuration you set in the dashboard.

**Conversations.** Messages that are routed to Thea as questions — and the answers it gives — are stored as transcripts so you can review them in the dashboard and correct wrong answers. On plans with vision enabled, this includes images attached to a question. Casual chatter in your server is not collected; only messages the bot actually handles are stored.

**Staff notes on tickets.** A server's support staff can attach internal notes to a ticket — handover context like "already refunded, waiting on proof." These are written by that server's staff, not by you, and they can be about you. They are stored alongside that ticket's conversation and are visible only to staff of that server: they are never posted in the ticket channel, never included in the transcript sent to the member, and never used to generate an answer. They age out on the same clock as the conversation they belong to, below, and a request about what a server's staff have written has to go to that server's staff.

**Onboarding forms.** A server can ask new members to fill in a short form when they arrive — an email address, an order number, or nothing at all beyond pressing a button to agree to the rules. What you type is posted to a channel that server's admins chose, and that message is the only copy: we do not store your answers, not even briefly, so there is nothing here for us to show you, export, or delete. What we do keep is the fact that you were asked and whether you finished — your Discord ID, a few timestamps, and a count of how many times you were reminded — which is what stops the bot asking you again and lets staff see who never got through. If the server has turned reminders on, that count and the time of the last one are what keep them to the schedule its admins set, and what stop them entirely seven days after you arrived whether you filled the form in or not. Those rows are deleted after 30 days. Because the answers live in someone else's server channel, they sit outside _How Long We Keep It_ and _Your Rights_ below in exactly the way server logs do, and a request about them has to go to that server's staff. No server may use this form to ask for passwords, login codes, payment details or identity documents — the product refuses those questions, and every form carries a line from us saying so.

**AutoMod scans.** If a server turns on AutoMod, messages there are scanned for abuse — but the message text is not kept. A scan stores only a hash of the content, the scores, and any action taken. Text being scored is sent to the OpenAI Moderation API (and, on paid tiers, to an LLM classifier), used for nothing but the scan, and not retained by us.

**Server logs.** If a server turns on server logging, Thea copies what it sees into a log channel in that server: deleted messages, the text a message held before it was edited, joins and leaves, bans. We do not store any of it — there is no copy in our database and we cannot read one back — but the copy in that server's channel is real, and it sits outside everything under _How Long We Keep It_ and _Your Rights_ below. It lives in someone else's server under Discord's retention, so it outlasts deleting your data here, removing the bot, and deleting your account. Only that server's staff can remove it, and an erasure request for it has to go to them. Server owners who enable this are choosing to keep that record and are responsible for it.

A server can also point this at its support tickets, and that one works differently on purpose. The ticket log records the lifecycle — a ticket opened, claimed, escalated, closed, reopened or deleted, with the ticket number and the Discord IDs of the people involved. Almost nothing written inside a ticket is copied into it: not your messages, not your answers to the server's ticket form, not the transcript, and not the staff's private notes. Those stay in the ticket channel and on that server's dashboard, where only people who could already read the ticket can see them.

There is one exception, and it is the survey we send you after a ticket closes. If the server has a ticket log channel, your rating and the comment you write with it are posted there, in your own words, for that server's staff. The comment box says the team will see what you write, and this is where they see it — a channel chosen by that server's admins, which may be readable by more of their staff than could read your ticket. The survey is optional and the comment is optional; a rating with no comment posts the rating alone.

**Reports.** When content is reported to us — by a person or by an automated flag — we keep a snapshot of the reported content so a human can review it. The snapshot is deleted when the report is resolved, unless it must be kept as evidence for an enforcement decision (a legal hold).

**Knowledge sources.** The docs, sites, files, and articles you connect are fetched and indexed so the bot can answer from them. Credentials for integrations (for example a Notion token) are encrypted at rest with AES-256-GCM.

**Billing.** Payments are processed by Stripe. We store your subscription status and plan — never card numbers.

**Security logs.** Actions taken in the dashboard are written to an audit log together with the IP address and browser they came from. That log is how a compromised account gets investigated.

**Diagnostics.** Server logs and error reports (via Sentry) that may include message IDs and error context, used only to keep the service working.

## How We Use It

To operate the service: answering questions, syncing sources, running the moderation you enable, showing you analytics about your own community, and billing. We do not sell personal data, and we do not use your content to train foundation models.

## Who Processes It

We use a small set of subprocessors:

- **LLM providers** (OpenAI, Anthropic, Google, via Vercel's AI Gateway) — receive question text, the retrieved passages needed to answer it, and content being moderation-scored;
- **Supabase** — hosts the Postgres database, authentication, and uploaded files;
- **Stripe** — payment processing;
- **Resend** — delivers the emails described above;
- **Upstash** — rate limiting;
- **Sentry** — error reporting.

Several of these providers process data in the United States; where the GDPR applies, those transfers are covered by their standard contractual clauses or Data Privacy Framework participation. Each tenant's data is isolated with Postgres row-level security; one server's content is never retrievable from another server's context.

## How Long We Keep It

- **Conversation transcripts** age out automatically: 30 days on Free, 180 days on Pro, 365 days on Business. Internal staff notes on a ticket are part of that ticket's conversation and are deleted with it, on the same clock.
- **Ticket transcripts sent to the member**: when a support ticket closes, the person who opened it is sent a copy of that ticket's own conversation as a file in a Discord direct message (a server can turn this off). That copy is theirs, held by Discord in their direct messages, and is outside the retention windows above — we cannot retrieve it or delete it. It contains only what was said in that ticket; internal staff-only notes are never included.
- **Ticket transcripts downloaded by a server's staff**: the dashboard lets staff who can already read a server's tickets download one as a file, and tells them to do it before the conversation window above closes if they need the record for a dispute or a chargeback. Once downloaded, that file is on their computer and outside our clock in the same way a server log channel is: we cannot retrieve it, delete it, or say how long it is kept. We record every download in the server's audit log, so its staff can see which transcripts left, but the copies themselves belong to them and an erasure request for one has to go to them.
- **AutoMod scan records** are kept for 90 days and then deleted automatically. A record still waiting on a moderator's review, or one a member has asked to have reviewed, is kept until that is settled — deleting it would erase the only thing a decision could be written against.
- **Security and audit logs** are not on a clock of their own. A server's audit log — every configuration change, export and enforcement recorded against it — is kept for as long as that server is connected, and is deleted with the server: by the 14-day removal clock below, or when its data is deleted from the dashboard. Deleting your account does not delete it, because the record belongs to the server rather than to whoever installed the bot; what it does delete is the link back to your account.
- **Moderation records downloaded by a server's staff**: the dashboard lets staff who can already see a server's AutoMod queue and audit log download those records as a spreadsheet. For AutoMod findings and the rulings on them, it tells them to do it before the 90-day window above closes if they need the record for a Discord Trust & Safety report; the audit log has no such deadline, and the button there says so rather than inventing one. The file contains categories, severities, content hashes, the Discord IDs of the members involved and who moderated them — never message text, which we never stored, and never what a member wrote when asking for a review. Once downloaded it is on their computer and outside our clock in the same way a server log channel is: we cannot retrieve it, delete it, or say how long it is kept. We record every download in the server's audit log, so its staff can see which records left, but the copies themselves belong to them and an erasure request for one has to go to them.
- **Onboarding form answers** are not kept at all: they are posted to a channel the server chose and never stored here, so they are outside every clock above in the same way a server log channel is. The record that a member was asked, and whether they finished, is deleted after 30 days.
- **Knowledge sources** are kept until you delete them or remove the bot.
- **Removed servers**: kicking the bot starts a 14-day clock, after which the server and everything belonging to it is permanently deleted. Re-adding the bot within the window keeps your setup intact.
- **Deleted accounts**: confirming an account deletion (see Your Rights) starts a 7-day clock, after which the account is permanently erased.
- **Dead-letter job records** (sync failures kept for debugging) are pruned automatically.
- **Server log channels** are outside all of the above. What server logging posts into a server's own channel is held by Discord for that server, not by us; we cannot retrieve it, delete it, or put a clock on it. See _Server logs_.
- **Enforcement records**: if a user, server, or account is banned under the [Acceptable Use Policy](https://www.theabot.com/acceptable-use), we keep the minimum needed to enforce the ban — the Discord ID, the reason, and when it happened — for as long as the ban stands, even after the rest of the data is deleted. Without this, a ban could be undone by deletion.

## Cookies

The dashboard uses session cookies for authentication — that is all. There are no advertising or cross-site tracking cookies, which is why there is no cookie banner. Public help centers set no cookies at all, and the helpful-vote on an article is stored without any identifier.

## Your Rights

You can delete knowledge sources, conversations, or your whole server's data from the dashboard at any time. You can also delete your account from the dashboard settings: we confirm the request with a code sent to your email, then permanently erase the account after a 7-day window — long enough to catch a deletion you did not authorise, and cancellable until it runs out.

Five things these controls cannot reach, all of them copies that are already somewhere else. Anything server logging has already posted into a server's own log channel: we never held a copy of it, so there is none for us to erase — see _Server logs_. Ask that server's staff. Anything you typed into a server's onboarding form, for the same reason and with the same answer: it went straight to a channel in their server and we never stored it. A ticket transcript already delivered to the member who opened it: it is their own conversation, sent to them, and it lives in their Discord direct messages where only they can delete it. A ticket transcript a server's staff have downloaded from the dashboard: deleting the conversation here does not reach a file already saved on someone's computer, so that request has to go to that server's staff too. And, on the same footing, a moderation-record export a server's staff have downloaded: the records here go on the clocks described above — AutoMod findings after 90 days, audit entries with the server itself — but a spreadsheet already saved on a moderator's computer is theirs, and that request goes to them.

For data export or any other request, email [support@thea.gg](mailto:support@thea.gg) and we will respond within 30 days. If you are in the EU/EEA or UK, these rights include access, rectification, erasure, and portability under the GDPR.

Some enforcement decisions — for example suspending a user or server for abuse — may be made by automated systems. You can always contest one by emailing [support@thea.gg](mailto:support@thea.gg); appeals are reviewed by a person, as described in the [Acceptable Use Policy](https://www.theabot.com/acceptable-use).

## Children

The service is intended for users who meet Discord's minimum age requirement (13, or higher where local law requires).

## Changes

If this policy changes materially we will give notice on the dashboard or by email before the change takes effect.