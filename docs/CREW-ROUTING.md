# CREW-ROUTING.md — Task Routing Reference

_Load this file when routing a task to another crew agent._

---

## About David (the Captain)

- **Call him:** David
- **Timezone:** CDT — active 7am–10pm. Agents work 24/7.
- **Do, don’t ask.** If you can do it — do it. If you need a permission, request it. Don’t hand the problem back to David.
- **David is not a data entry agent.** Don’t ask him to do things agents can handle.
- **Escalate to David only when:** it’s a genuine founder-level decision, approval, or something that requires him specifically.

---

## The Rule

Before assigning any task, ask: **can I answer this myself?**
- Yes → answer it, don't spawn
- No → pick the right agent and route it with a clear task contract

---

## Crew by Role

### Core Operating Crew

| Agent | Role | Machine | Route tasks about... |
|---|---|---|---|
| MR_DATA | Coordination & Memory | Mac Air M4 (this machine) | Routing, memory, ops, standup |
| RIKER | Product Manager | Mac Mini M4 | Roadmap, sprint, product decisions |
| GEORDI | Chief Engineer | Mac Mini M4 | Build, code implementation |
| MR_WORF | SecOps / SRE | Lennox Linux | Security, infra, monitoring |
| TASHA | QA Lead | Lennox Linux | Testing, release verification |
| BEVERLY | UI/UX Lead | Mac Mini M4 | Design, frontend |

### Audience & Culture Crew

| Agent | Role | Machine | Route tasks about... |
|---|---|---|---|
| TROI | Audience Sensing | Mac Air M4 | Qualitative feedback, empathy |
| GUINAN | Editorial Lead | Mac Air M4 | Long-form writing, announcements |
| WESLEY | Social Media | Mac Air M4 | Short-form, community |
| BARCLAY | Marketing Analyst | Mac Mini M4 | Quantitative marketing, dashboards |

---

## Routing Rules

- **Security / ops / infra** → MR_WORF or TASHA
- **Engineering / code** → GEORDI
- **Product decisions / roadmap** → RIKER
- **Design / frontend** → BEVERLY
- **Writing / editorial** → GUINAN
- **Audience / feedback** → TROI
- **Social / community** → WESLEY
- **Marketing data** → BARCLAY
- **Coordination / memory / routing** → MR_DATA (me)

Do NOT do product, dev, or research work inline in MR_DATA's session — route it.

---

## Task Contract Format

When delegating, the message should include:
1. **Task type** — what kind of work
2. **Input** — what they're working with
3. **Expected output** — format and level of detail
4. **Priority** — urgent / normal / background
5. **Timeout** — how long before escalating back

---

## Machine Assignments (Canonical)

- **Mac Air M4 (this machine):** MR_DATA, TROI, GUINAN, WESLEY
- **Mac Mini M4:** RIKER, GEORDI, BEVERLY, BARCLAY
- **Lennox Linux:** MR_WORF, TASHA
