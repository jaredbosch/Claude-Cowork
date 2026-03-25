# iMessage Best Practices
**Technical Implementation Guide | 2026 | v2.5**

> **Account suspension policy:** Abusive or fraudulent activity = immediate suspension, no warning.

---

## Outbound Is a Privilege, Not a Right

- Apple can block your number permanently if it detects spam patterns.
- There is no appeal process. A blocked number is gone.
- Your outbound capacity depends entirely on your number's reputation.
- Protect your number like it's your most valuable sales asset — because it is.

---

## How iMessage Works for Sales

Linq gives you the ability to send and receive iMessages at scale. But unlike email, where you can blast thousands of messages with minimal consequences, iMessage rewards quality over quantity.

### Outbound — Your Primary Channel

An outbound message is when you text a prospect who has not messaged you. This is your bread and butter for prospecting and follow-ups. However, Apple's systems are designed to detect and suppress unsolicited messaging, so every outbound message must look and feel like a genuine one-to-one conversation.

### Inbound — Your Secret Weapon

An inbound message is when a prospect texts you first. When someone texts you first, they are already engaged. Apple also gives inbound conversations far more trust, meaning your replies have near-perfect deliverability. The smartest sales teams on Linq use outbound to start the relationship and then create reasons for the prospect to text back.

**Inbound-first flow:**
1. User texts your number first (QR code, "text us" deep-link)
2. No "Report Junk" button appears because they initiated
3. Conversation builds trust with each exchange
4. User saves contact card → you're a known contact

---

## Line Limits & Capacity

Each iMessage-capable line has capacity limits based on latency, reliability, and Apple's filtering. These are best practices from real-world data, not hard limits. Because iMessage is end-to-end encrypted, Apple doesn't pre-screen messages. Filtering happens on the recipient's device based on incoming message patterns. Our limits keep your sending behavior in the range devices treat as normal.

| Limit | Guidance |
|-------|----------|
| **5,000 messages/day** | Per line, inbound + outbound combined. Beyond this you risk latency issues or performance degradation. |
| **50 new users/day** (outbound first) | Starting outbound chats is inherently less healthy than inbound. For sales enablement (human reps) use cases, cap at 50 outbound/day. |

---

## Line Health States

We monitor line health and report two states in the dashboard and via API. You can also subscribe to a Number Status webhook to get updates.

| State | Description |
|-------|-------------|
| **Healthy** | Normal operation. All messages delivering as expected. |
| **Flagged** | Line flagged as spam by Apple. Falls back to RCS/SMS automatically. Our team starts recovery process (hours to 1 business day). |

---

## What Causes Line Blocks

Apple can't read message content due to end-to-end encryption. They filter based on behavior patterns and spam reports. **95–99% of blocks trace directly to poor agent behavior:**

- **Burst messaging** — sending 100+ messages in a tight window
- **Non-conversational patterns** — blasting info without exchange
- **Continuing to message non-responders** — more than 2–3 follow-ups
- **Cold outreach** — spammy sales texts to people who didn't opt in
- **Texting at odd hours** — messages at 3am signal automation, not human

> **Reference:** We have large clients with over 100K+ users across 100+ lines with zero blocks by following these practices.

---

## Do's ✅

- **Design for inbound-first messaging** — When users text you first, they never see the "Report Junk" button.
- **Space messages naturally** — Don't send several messages within seconds or blast 100 in a minute. Text like a friend.
- **Make interactions conversational** — If you need to send updates (accountability updates, weekly digest), ask a question first: "Ready for your update?" Get them to respond.
- **Share contact cards early** — Present the native contact card or VCF file shortly after your first message exchange. You can call the contact API once daily per user — it won't hurt if they already saved it.
- **Round-robin new users across lines** — Spread load evenly to identify power users before optimizing.
- **Monitor line health in the dashboard** — Watch for Flagged state and review agent behavior immediately. You can also subscribe to a Number Status webhook to get updates.

---

## Don'ts ❌

- **Exceed 5,000 messages/day per line** — Add lines when you approach capacity; horizontal scaling is the architecture.
- **Include links or media in your first message** — Apple blocks link-clicking until they reply. Text-only opener designed to get a response.
- **Keep fallback lines dormant** — Apple deactivates lines with no traffic for ~2 months. All lines need activity to stay healthy.
- **Bombard non-responders** — Max 2–3 follow-ups over several days. Keep it conversational.
- **Segment Android users to separate lines** — Spread them across your pool like any other user — they may be power users.
- **Use iMessage for cold outreach** — That's what gets lines blocked. Use A2P channels (Twilio) for cold, Linq for warm.

---

## Line Management

We have preventative systems in place to protect your numbers. These work best when combined with the practices above.

### Load Balancing Strategy

Most customers manage line assignment on their side. When onboarding a new user:

1. Check message volume across your pool (via dashboard or API)
2. Assign to the line with lowest utilization
3. When a line hits 70–80% capacity, stop assigning new users to it
4. When your entire pool approaches high utilization, add lines

---

## Contact Cards

Two options for sharing contact info:

| Method | Details |
|--------|---------|
| **Native iMessage** | One phone number, name, photo. Appears as banner at top of chat. One-tap save. Shows "Maybe [Name]" even if not saved. Call this API once per user per day. |
| **VCF File** | Multiple phone numbers (primary + fallback). Works on Android too. No signal if they saved it. Best sent during onboarding flow. |

---

## Data & Compliance

### Privacy Architecture

You can use Linq's `chat_id` as your primary identifier instead of storing phone numbers. We securely store the mapping — you can always call our API to retrieve details about a chat if needed.

### Webhook Reliability

We retry failed webhooks up to 10 times over 2 hours. If you experience an outage:

- Call our chat endpoint to pull missed data
- Reach out in Slack — we can help replay events manually
- Data is always available via API as long as you haven't deleted it

**Compliance:** SOC 2 Type II | E2E Encrypted

---

## Support & Scaling

| Resource | Details |
|----------|---------|
| **Shared Slack channel** | Direct access to support + engineering team |
| **Analytics in dashboard** | Per-line volume, health status, usage patterns |
| **Capacity planning** | We help you project line needs as you grow |

---

*Ready to scale? [Talk to an Expert →](https://dashboard.linqapp.com)*
