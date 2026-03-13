# Drehbuch: AI-First Software Development (3h)

## Übersicht
| Block | Zeit | Dauer |
|-------|------|-------|
| Intro | 08:30–09:00 | 30 min |
| Claude Code kennenlernen | 09:00–10:00 | 60 min |
| *Pause* | 10:00–10:30 | 30 min |
| AI-First Lifecycle — Hands-On | 10:30–11:30 | 60 min |
| Wrap-Up | 11:30–12:00 | 30 min |

---

## Block 1: Intro (30 min)
**08:30–09:00**

### Ziel
Mindset-Shift: Warum 95% scheitern, warum Neugier der Schlüssel ist

### Ablauf
- **08:30** (5 min) — Begrüssung, Vorstellung
- **08:35** (10 min) — Die 5% vs 95% Story
  - Statistik: 78% nutzen AI, 5% Nutzen
  - Was machen die 5% anders? → Integration statt Experiment
- **08:45** (10 min) — Neugier-Mindset
  - Wieder zu Kindern werden
  - Emergent Abilities: warum niemand "die Antwort" hat
- **08:55** (5 min) — Verification First + Wo lernen?
  - DAS wichtigste Prinzip
  - github.com/anthropics, @bcherny

---

## Block 2: Claude Code kennenlernen (60 min)
**09:00–10:00**

### Ziel
Hands-On: Das Tool kennenlernen — Konzepte und Grundlagen

### Ablauf
- **09:00** (10 min) — Copilot vs Agent
  - Unterschied erklären
  - Microsoft "Copilot Cowork" als Bestätigung der Agent-Richtung
- **09:10** (10 min) — Cheatsheet + ausprobieren
  - Wichtigste Befehle: /help, /clear, /compact, /plan, Shift+Tab, @-Mentions
  - Kurzreferenz verteilen (referenz-claude-code.md)
  - Teilnehmer probieren Befehle aus
- **09:20** (10 min) — Was ist Context?
  - CLAUDE.md, Conversation, Tool Results, @ Mentions
  - Context Window ≈ 200K Tokens, /compact wenn voll
- **09:30** (10 min) — Permissions & Trust
  - Lesen immer erlaubt, Schreiben/Bash fragt nach
  - "Yes to all" erst wenn sicher
- **09:40** (10 min) — Slash Commands & Tools
  - /plan Modus: nur planen, nicht coden
  - Teilnehmer: `/plan Erkläre mir die Ordnerstruktur`
- **09:50** (10 min) — MCP — USB für AI
  - Offener Standard, .mcp.json
  - Beispiele: DB, DevOps, Slack, Monitoring

### Pause (30 min)
**10:00–10:30**

Teilnehmer prüfen: Claude Code läuft? Repo geklont? Azure CLI eingeloggt?

---

## Block 3: AI-First Lifecycle — Hands-On (60 min)
**10:30–11:30**

### Ziel
Den kompletten Lifecycle durchgehen — pro Phase kurz erklären (Mensch vs Agent), dann sofort hands-on im Kalkulationstool-Repo.

**→ Detaillierte Prompts: siehe `exercises-kalkulationstool.md`**

### Ablauf
- **10:30** (5 min) — Setup & Init
  - `cd Kalkulationstool && claude`
  - `/init` → CLAUDE.md erstellen
  - "Was ist dieses Projekt?"
- **10:35** (10 min) — Phase 1: Requirements
  - Mensch: Business-Ziel, Priorisierung
  - Agent: Code analysieren, Fragen generieren
  - Hands-On: Bug #191 lesen, verstehen, Rückfragen generieren
- **10:45** (10 min) — Phase 2: Spec
  - Mensch: Approach entscheiden, Risiken bewerten
  - Agent: Spec schreiben, betroffene Dateien identifizieren
  - Hands-On: `/plan` Spec für Bug #191
- **10:55** (15 min) — Phase 3: Code + Test
  - Mensch: Diffs prüfen, jede Änderung verstehen
  - Agent: Tests zuerst, dann implementieren
  - Hands-On: Fix implementieren, Unit Test schreiben
  - Hinweis: agent-browser.dev für Frontend-Testing
- **11:10** (10 min) — Querschnitt: Security
  - `/security-review` ausführen
  - Security Audit für gesamte Codebase erstellen
  - Hands-On: Fehlende [Authorize] Attribute fixen
- **11:20** (10 min) — Phase 4: Deploy & Ops
  - Mensch: Release-Entscheid, Incident-Priorität
  - Agent: PRs erstellen, Logs analysieren, Hooks
  - Hands-On: Azure CLI Work Items abfragen, Bug-Report erstellen

---

## Block 4: Wrap-Up (30 min)
**11:30–12:00**

### Ablauf
- **11:30** (10 min) — Der geschlossene Loop
  - Zusammenfassung: was gerade durchlaufen wurde
  - Vision: Issue → Code → Test → Deploy aus einer Oberfläche
- **11:40** (10 min) — Feedback-Runde
  - Was hat funktioniert, was nicht?
  - Wo seht ihr den grössten Hebel?
  - Was war überraschend?
- **11:50** (5 min) — Was ihr heute gelernt habt
  - Verification First, Context Engineering, Explore → Plan → Code
  - Agent > Copilot, geschlossener Loop
- **11:55** (5 min) — Ressourcen + Danke
  - Links: Claude Code Docs, MCP Registry, Workshop-Repo
  - "Wir haben die ersten Samen gepflanzt — jetzt den Garten anlegen"

---

## Materialien
- [ ] Slides (slides/slides.md)
- [ ] Demo-Repo: Kalkulationstool
- [ ] Handout: Setup-Guide (handout-en.md)
- [ ] Kurzreferenz: Claude Code (referenz-claude-code.md)
- [ ] Handout: MCP Use Cases (handout-mcp-usecases.md)
- [ ] Todo/Bug-Beschreibung (todo.md)
