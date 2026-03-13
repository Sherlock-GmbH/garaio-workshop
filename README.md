# GARAIO Workshop — AI-First Software Development

Workshop-Materialien für den 3-stündigen Claude Code Workshop.

## Inhalt

### 🎬 slides/
Slidev-Präsentation mit Speaker Notes:
- **slides.md** — Komplettes Slidedeck (Slidev Markdown)
- `npm run dev` zum Starten, `npm run export-pdf` für PDF

### 📋 output/
Fertige Workshop-Dokumente:
- **drehbuch-3h.md** — Komplettes Drehbuch (Ablauf, Timing, Inhalte)
- **exercises-kalkulationstool.md** — 5 Hands-On Exercises + Bonus
- **handout-en.md** — Setup-Guide für Teilnehmer (EN)
- **handout-mcp-usecases.md** — MCP Use Cases Handout zum Mitnehmen
- **key-messages.md** — Key Messages des Workshops

### 🔧 Demo-Repo (Kalkulationstool)
Das Kalkulationstool-Repo ist **nicht** in diesem Repository enthalten.  
Teilnehmer clonen es direkt von Azure DevOps — siehe [Preparation Guide](output/handout-en.md).

## Slides starten

```bash
cd slides
npm install
npm run dev
# → http://localhost:3030
```

Speaker Notes: Drücke `s` in der Präsentation für den Presenter-Modus.

## Vorbereitung

Siehe [output/handout-en.md](output/handout-en.md) für die vollständige Setup-Anleitung.

**Kurzfassung:**
1. Claude Pro Subscription + Claude Code installieren
2. Azure CLI + DevOps Extension installieren und einloggen
3. Kalkulationstool-Repo von Azure DevOps clonen
4. Quick-Test: `claude` im Repo starten
