# hands-on

**Stop turning the user into the agent's hands.**

`hands-on` is an agent skill for Claude Code (and any agent that reads `SKILL.md` skills). Agents often answer a setup task with "go to Settings, click this, copy that ID, paste it there". The user ends up doing the work, slower and with more mistakes, while the agent had a browser, a CLI and an API the whole time.

`hands-on` makes the agent do every step it can and ask the user only for what it truly cannot or must not do: codes sent to their phone, secret keys, identity checks, payments and legal consent. All of it in one short message.

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

## License

MIT. Made by [Rabbit Designs](https://github.com/RabbitDesigns22).
