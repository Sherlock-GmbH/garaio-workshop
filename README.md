# GARAIO Workshop — AI-First Software Development

Workshop-Materialien für den 3-stündigen Claude Code Workshop.

## Inhalt

### 🎬 slides/
Slidev-Präsentation mit Speaker Notes:
- **slides.md** — Komplettes Slidedeck (Slidev Markdown)
- `pnpm run dev` zum Starten

### 📋 output/
Fertige Workshop-Dokumente:
- **drehbuch-3h.md** — Komplettes Drehbuch (Ablauf, Timing, Inhalte)
- **exercises-kalkulationstool.md** — Hands-On Exercises + Bonus
- **handout-en.md** — Setup-Guide für Teilnehmer (EN)
- **handout-mcp-usecases.md** — MCP Use Cases Handout zum Mitnehmen
- **handout-ressourcen.md** — Kuratierte Links & Ressourcen
- **referenz-claude-code.md** — Claude Code Kurzreferenz (Befehle, CLAUDE.md, Skills, MCP)
- **workflow-prompts-guide.md** — Prompt-Beispiele nach Rolle (Dev / Tester / PM)
- **security-considerations.md** — Security-Aspekte beim Einsatz von AI Agents
- **key-messages.md** — Key Messages des Workshops
- **todo.md** — Bug #191 + Azure DevOps CLI Commands für Demo

### 🔧 Demo-Repo (Kalkulationstool)
Das Kalkulationstool-Repo ist **nicht** in diesem Repository enthalten.
Teilnehmer clonen es direkt von Azure DevOps — siehe [Preparation Guide](output/handout-en.md).

## Slides starten

```bash
cd slides
pnpm install
pnpm run dev
# → http://localhost:3030
```

Speaker Notes: Drücke `s` in der Präsentation für den Presenter-Modus.

## Vorbereitung

Siehe [output/handout-en.md](output/handout-en.md) für die vollständige Setup-Anleitung.

**Kurzfassung:**
1. Claude Pro Subscription + Claude Code installieren
2. Azure CLI + DevOps Extension installieren und einloggen
3. Kalkulationstool-Repo von Azure DevOps clonen
4. Quick-Test: `claude` im Repo starten, `/init` ausführen
