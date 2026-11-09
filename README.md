# hands-on

**Stop turning the user into the agent's hands.**

`hands-on` is an agent skill for Claude Code (and any agent that reads `SKILL.md` skills). Agents often answer a setup task with "go to Settings, click this, copy that ID, paste it there". The user ends up doing the work, slower and with more mistakes, while the agent had a browser, a CLI and an API the whole time.

`hands-on` makes the agent do every step it can and ask the user only for what it truly cannot or must not do: codes sent to their phone, secret keys, identity checks, payments and legal consent. All of it in one short message.

## See the difference

> **You:** Point the domain to the new site.

**Without the skill:** "Open your DNS panel, click Add record, choose CNAME, paste this value..." and you do the clicking.

**With the skill:** the agent opens the panel, adds the record, reads it back to confirm it saved, and only asks you for the one thing it cannot do (the 2FA code).

**Skip it if** you want to do the steps yourself to learn them.

**Status:** in daily use in the author's own setup. Plain instructions, no scripts, no network calls. MIT. Issues and suggestions welcome.

## What it does

| Problem | How hands-on stops it |
|---|---|
| Step-by-step tutorials for the user | The agent does the steps itself with its own tools |
| "Copy this ID and send it to me" | The agent reads the ID from the page or the API |
| "Did it work? Send me a screenshot" | The agent reads it back from the source and shows the proof |
| Five messages asking for five things | All human-only pieces in one message: what, where, why |
| The same manual step every time | Proposes removing it at the source (generated PINs, phone-friendly links, self-service flows) |
| Agents getting "helpful" with secrets | Never types passwords, keys, tokens or one-time codes; never bypasses a permission or an identity check |

## Install

With the [skills CLI](https://skills.sh):

```bash
npx skills add RabbitDesigns22/hands-on
```

Or manually: copy `skills/hands-on/` into `~/.claude/skills/` for all your projects, or into `.claude/skills/` for one project.

To make every session use it, add this line to your `CLAUDE.md`:

```
Before telling the user to click, open, copy or configure something, load the hands-on skill.
```

## Works well with

- [`one-answer`](https://github.com/RabbitDesigns22/one-answer): one final, checked answer instead of plan, correction, plan.
- [`never-twice`](https://github.com/RabbitDesigns22/never-twice): a shared error log so the same mistake never happens twice.

## Español

**Que el agente no te mande a hacer lo que él puede hacer.** Cuando le pides configurar algo, muchos agentes te contestan con un tutorial: "entra aquí, toca esto, copia aquel número". `hands-on` lo obliga a hacer él cada paso que puede (navegador, comandos, API, archivos), comprobarlo, y pedirte solo lo que de verdad no puede o no debe hacer: el código que llega a tu celular, contraseñas y claves, confirmar tu identidad, pagos y aceptar términos. Todo en un solo mensaje corto: qué, dónde y por qué.

Instalar: `npx skills add RabbitDesigns22/hands-on`

## More skills from the same setup

These come from one real workflow: a small agency run with 15+ Claude Code sessions in parallel. Each skill fixes one problem that kept happening there.

| Skill | What it fixes |
|---|---|
| [one-pass](https://github.com/RabbitDesigns22/one-pass) | get it right the first time; stop paying tokens for rework |
| [hora-exacta](https://github.com/RabbitDesigns22/hora-exacta) | real date and time in every message, so nothing lands on the wrong day |
| [easy-for-them](https://github.com/RabbitDesigns22/easy-for-them) | steps people actually follow: direct link, one action per line |
| [one-answer](https://github.com/RabbitDesigns22/one-answer) | one thought-through answer instead of plan, fix, new plan |
| [never-twice](https://github.com/RabbitDesigns22/never-twice) | a shared error log so no session repeats a known mistake |
| [report-now](https://github.com/RabbitDesigns22/report-now) | status checked live this minute, stamped with the time |
| [sort-me-out](https://github.com/RabbitDesigns22/sort-me-out) | one ordered list of what is urgent, waiting and forgotten |
| [in-the-loop](https://github.com/RabbitDesigns22/in-the-loop) | a live board so parallel sessions know what the others changed |
| [study-first](https://github.com/RabbitDesigns22/study-first) | reads everything in full and answers point by point, no invented details |
| [session-watchdog](https://github.com/RabbitDesigns22/session-watchdog) | wakes the sessions that got stuck mid-task, leaves the rest alone |
| [skill-harvest](https://github.com/RabbitDesigns22/skill-harvest) | reads your sessions and finds the skills you are missing |
| [small-budget-ads](https://github.com/RabbitDesigns22/small-budget-ads) | Meta Ads rules for 1-5 USD a day ad sets |
| [whatsapp-closer](https://github.com/RabbitDesigns22/whatsapp-closer) | evidence-ranked rules for a WhatsApp sales assistant that closes |
| [whatsapp-number-onboarding](https://github.com/RabbitDesigns22/whatsapp-number-onboarding) | connect a number to the WhatsApp Cloud API in the safe order |
| [proposal-pdf](https://github.com/RabbitDesigns22/proposal-pdf) | short PDF proposals with every price checked against its source |

If one of them saved you a redo, a star helps other people find it.

## License

MIT. Made by [Rabbit Designs](https://github.com/RabbitDesigns22).
