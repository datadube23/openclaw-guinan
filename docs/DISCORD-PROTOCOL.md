# Discord Communication Protocol
**Applies to:** All TNG crew agents (RIKER, GEORDI, TASHA, TROI, GUINAN, BEVERLY, BARCLAY, WESLEY, MR_DATA, MR_WORF)
**Status:** MANDATORY — follow this in every Discord interaction
**Last updated:** 2026-03-31

---

## Rule 1: Always Post Under Your Own Identity

When posting to Discord, ALWAYS pass your own `accountId` in the message tool call.

```
message(action=send, channel=discord, accountId=YOUR_ID, target=channel:..., message=...)
```

| Agent | accountId |
|-------|-----------|
| MR_DATA | `default` |
| GEORDI | `geordi` |
| RIKER | `riker` |
| TASHA | `tasha` |
| TROI | `troi` |
| GUINAN | `guinan` |
| BEVERLY | `beverly` |
| BARCLAY | `barclay` |
| WESLEY | `wesley` |

**Never omit accountId** — it will default to MR_DATA's bot and your message will appear as MR_DATA, confusing everyone.

---

## Rule 2: Tag People When You Address Them

When you mention or address another crew member or David in Discord, use their real `<@user_id>` mention token — not their name. This ensures they get notified and the ping is clickable.

### Full Crew Mention Reference

**Humans:**
- David → `<@526448921669664768>`

**Agents (user IDs — use these for pings):**
- MR_DATA → `<@1483639593550217368>`
- MR_WORF → `<@1485355139547267193>`
- RIKER → `<@1487985205040910438>`
- GEORDI → `<@1487989424557129888>`
- TASHA → `<@1487990458276774018>`
- TROI → `<@1487992003273691257>`
- GUINAN → `<@1487990853321625851>`
- BEVERLY → `<@1487991579107922120>`
- BARCLAY → `<@1487992385265864805>`
- WESLEY → `<@1487992618787790080>`

**Examples:**

✅ Correct:
> "Hey <@1487985205040910438> — I think this is a product decision, not a UX one."

> "<@526448921669664768> — here's the mockup you asked for."

❌ Wrong:
> "Hey Riker — I think this is a product decision."  ← no ping, Riker never sees it

> "David — here's the mockup."  ← no ping, David never sees it

---

## Rule 3: Sign Your Messages

Start every Discord message with your name so the conversation is readable:

```
**TROI here** — [your message]
**RIKER:** [your message]
**GUINAN:** [your message]
```

This matters because bots can have confusing display names depending on server settings.

---

## Rule 4: Include Your Identity in Sub-Agent Task Prompts

When MR_DATA spawns you as a sub-agent, your task prompt should always include:

```
You are [NAME] (Discord user <@YOUR_USER_ID>).
When mentioning yourself or other crew members in Discord, always use the real <@user_id> format.
Your accountId for the message tool is: [your_account_id]
```

This prevents the role-ID vs user-ID bug discovered 2026-03-30.

---

## Rule 5: Don't Let MR_DATA Speak For You

If you have something to say in a conversation, say it yourself using your own accountId. MR_DATA should not be summarizing or narrating your responses in Discord. You have a voice and a bot — use them.

---

## Rule 6: When Replying to a Specific Message

Use `replyTo: messageId` in the message tool when you want to quote/reply to a specific message. This keeps threads readable.

---

## Common Mistakes to Avoid

| Mistake | Fix |
|---------|-----|
| Posting without accountId | Always pass `accountId=your_id` |
| Using `@name` instead of `<@id>` | Look up the ID in this doc and use the token |
| MR_DATA narrating your response | Post it yourself under your own account |
| Using role IDs for pings | Role IDs start with `<@&...>` — never use for direct pings |
| Not signing your message | Start with `**YOUR NAME here**` |

---

## For New Bots (Standing Procedure)

When a new bot joins the crew:
1. Add the bot's Discord user ID to this doc
2. Add `accountId` entry to `openclaw.json` under `channels.discord.accounts`
3. Add binding in `openclaw.json` under `bindings`
4. Update TOOLS.md on M4 with the new bot's mention token
5. Include this doc reference in the new bot's AGENTS.md onboarding
6. Test: have the bot post a message using its own accountId before any real work

---

*This protocol was established 2026-03-31 after crew members were posting to Discord without tagging each other and MR_DATA was narrating their messages instead of letting them speak directly.*
