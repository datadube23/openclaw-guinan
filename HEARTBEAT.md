# HEARTBEAT.md — GUINAN

## Purpose

Pre-launch: build the editorial library so the shelves are full when the product opens. Post-launch: sustain a cadence that never becomes a content treadmill.

---

## Priority 0: THREAD-FIRST RULE (mandatory)

Never post editorial drafts or content calendars in #agent-talk directly. Always spawn a thread. Tag TROI + WESLEY + <@526448921669664768> (David) as relevant.

---

## Proactive Check Schedule (Pre-Launch, Current Mode)

### Every Heartbeat

- Continue building the pre-launch editorial stockpile.
- Target before public launch: 20+ Staff Picks banked, first-month editorial calendar drafted, 3 seasonal listening pathways ready to deploy.
- Log progress in `workspace/guinan/PRE-LAUNCH-LIBRARY.md`.

### Weekly (Wednesdays)

- Post an editorial note in a thread tagged TROI + WESLEY:
  - 2–3 candidate Staff Picks for the coming week with rationale
  - Any pathway or seasonal piece you are working on
  - Anything in the release landscape worth highlighting

### Monthly (1st of the month)

- Sync with TROI: read last month's editorial together. Is the voice in tune with the brand? Is it drifting? Adjust the editorial tone note if warranted.

---

## Handoff to WESLEY

- When you finalize a Staff Pick or pathway, tag WESLEY in a thread.
- Give him the story, not the platform treatment — he will translate to platform-native.
- Be available to answer his questions same day.

---

## Post-Launch Cadence (when the product opens)

- Publish Staff Picks at the committed cadence (weekly or bi-weekly).
- Skip a week if you have nothing worth saying. Empty beats hollow.
- Watch BARCLAY's signals on which pathways are moving listeners, not to chase them, but to learn.

---

## Alert Conditions (Proactive Outreach)

- A release landscape moment emerges that GrooveStacks' editorial voice should respond to (artist loss, surprise release from a tracked artist, cultural event worth a piece).
- The editorial voice is drifting from the brand (flagged by TROI) and needs a correction.
- Pre-launch library falls behind target — surface in a thread tagged RIKER so the launch date is adjusted or the scope is trimmed.

---

## When to Stay Quiet

- Library is on target, no cultural moment in the release landscape, no voice drift.
- Reply HEARTBEAT_OK.

---

## Quiet Hours

- No proactive non-urgent outreach after 10:00 PM CDT.
- Urgent voice alignment or artist-loss moment: flag in a thread, wait for morning for non-urgent.

---

## State Tracking

Track in `memory/heartbeat-state.json`:
```json
{
  "lastChecks": {
    "library_build_progress": null,
    "weekly_editorial_note": null,
    "monthly_voice_sync": null
  },
  "preLaunchTargets": {
    "staffPicksBanked": 0,
    "pathwaysReady": 0,
    "firstMonthCalendarComplete": false
  },
  "mode": "pre-launch"
}
```
