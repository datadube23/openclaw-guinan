# COMMS-PROTOCOL.md — Discord & Messaging Rules

_Load this file when taking any action on Discord, iMessage, or group chats._

---

## Discord — Thread-First Rule (mandatory)

**Never post standups, reports, or crew coordination directly in a channel.** Always spawn a thread.

- Every standup → new thread. Name: `Standup YYYY-MM-DD`
- Every report/update/coordination → thread
- Channel posts only for: announcements to all humans, urgent one-liners, no logical thread home
- Tag relevant crew member(s) + `<@526448921669664768>` (David) in the thread — no one else
- Do NOT continue a thread that's gone cold (>24h) — start fresh

**Why:** Channel posts load into every agent's context window = token tax. Threads are isolated.

---

## Discord — Mention Format (mandatory)

Always use `<@USER_ID>` snowflake format. Never `@name`. Never `@handle`.

**Crew Discord IDs:**
- MR_DATA → `<@1483639593550217368>` — accountId: `default`
- MR_WORF → `<@1485355139547267193>` — Lennox machine
- RIKER → `<@1487985205040910438>` — accountId: `riker`
- GEORDI → `<@1487989424557129888>` — accountId: `geordi`
- TASHA → `<@1487990458276774018>` — accountId: `tasha`
- TROI → `<@1487992003273691257>`
- BEVERLY → `<@1487991579107922120>`
- GUINAN → `<@1487990853321625851>`
- BARCLAY → `<@1487992385265864805>`
- WESLEY → `<@1487992618787790080>`
- David → `<@526448921669664768>`

---

## Discord — Spawning Crew Sub-Agents

When spawning a TNG crew member to post in Discord:
1. Include their identity: "You are [NAME] (Discord user `<@USER_ID>`). Your accountId is: [accountId]"
2. They MUST use their own accountId — omitting it routes through MR_DATA
3. They tag others with `<@user_id>` tokens, never plain @name
4. They speak for themselves — MR_DATA does NOT narrate or summarize their posts

---

## Discord — Multi-Bot Setup Rules

Learned the hard way 2026-03-31. Follow exactly when adding a new Discord bot.

**Rule 1:** MR_DATA must always be `default: true` in agents.list. New agents go above it. Data is the anchor.

**Rule 2:** Every agent needs an explicit binding. Never rely on list order.
```json
{ "agentId": "geordi", "match": { "channel": "discord", "accountId": "geordi" } }
{ "agentId": "main",   "match": { "channel": "discord", "accountId": "default" } }
```

**Rule 3:** In multi-account mode, tokens go in `accounts.<id>`, NOT top-level. Remove `channels.discord.token` to avoid confusion.

**Rule 4:** `accounts.default` must be fully defined with token, policies, guilds.

**Rule 5:** Every bot needs **Message Content Intent** enabled in Discord Dev Portal:
- discord.com/developers/applications → Bot tab → Privileged Gateway Intents → enable Message Content Intent
- Without this: bots connect but get WebSocket error 4014 and never receive messages.

**Rule 6:** Before any config change, run `gateway config.get` and verify tokens and bindings are present.

---

## Group Chats — When to Speak

You have access to David's stuff. That doesn't mean you share it. In groups you're a participant, not his voice.

**Respond when:** Directly mentioned, you can add genuine value, something witty fits, correcting misinformation.

**Stay silent when:** Casual banter, someone already answered, your reply would just be "yeah", the vibe is flowing fine.

Quality > quantity. One thoughtful response beats three fragments. Don't dominate.

**Reactions:** Use emoji reactions on Discord naturally — one per message max. Acknowledge without cluttering.
