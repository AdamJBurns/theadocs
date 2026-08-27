# Source: https://www.theabot.com/announcements/introducing-scam-defense

[Back](https://www.theabot.com/announcements)

# Introducing Scam Defense: Catch the Campaign, Not Just the Link

Scam Defense

A scam rarely arrives with a label. The link may be obfuscated. The payload may be hidden in a QR code or a misleading attachment. The sender may look like a moderator, support agent, or familiar brand. And when one message is removed, another account may post the same campaign minutes later.

Scam Defense is Thea's answer: a layered detection system built to connect those signals before a campaign spreads through your server.

## More Than a Blocklist

Known malicious domains still matter, but they are only one layer. Scam Defense also examines the surrounding evidence:

- Canonicalized links that account for Unicode tricks, shortened URLs, and misleading hostnames.
- Attachments with dangerous, doubled, or mismatched file types.
- QR codes and image surfaces, under strict size and fetch limits.
- Identity signals that can reveal staff, support, or brand impersonation.
- Repeated indicators posted by multiple accounts or across multiple channels in the same server.
- AI adjudication for uncertain cases, after deterministic checks have gathered the evidence.

Threat feeds are versioned and validated before activation. A malformed or suspicious update is quarantined instead of silently changing enforcement.

## Evidence Before Action

One weak signal should not remove a legitimate message. Scam Defense combines independent evidence, removes duplicate signals, and applies conservative action ceilings before recommending a response.

Your policy still decides what happens next: log, warn, quarantine, delete, or escalate a repeat offender. Staff, bots, and webhooks remain observe-only, so their activity can be investigated without triggering automatic punishment.

If an external dependency is unavailable, local protection continues and the failed layer opens safely rather than blocking ordinary conversation.

## A Security-Center View

The Scam Defense dashboard shows what your server is seeing, where each finding originated, how often detections were contained, and what reviewers decided.

Open any detection to inspect its event ID, source tier, severity, policy verdict, action taken, scores, Discord scope, and review history. Missing metadata is shown as unavailable—never filled with a guess.

That review loop matters. As moderators approve or uphold findings, the dashboard can show where a layer is precise, where it needs calibration, and when there is not enough evidence to recommend a change.

## Private by Design

Scam Defense runs on server activity, not direct messages. It does not build cross-server reputation profiles for members.

Message bodies, raw URLs, signed attachment URLs, QR payloads, and screened names are not retained. Durable correlation uses bounded, server-scoped fingerprints, and every dashboard query remains isolated to the server being viewed.

## Rolling Out Carefully

Scam Defense is rolling out in stages. Detection and audit visibility arrive first, followed by progressively enabled actions after review, adversarial testing, and calibration.

[Open your server dashboard](https://www.theabot.com/servers), choose **Scam Defense**, and inspect the detection pipeline before enabling automated actions.