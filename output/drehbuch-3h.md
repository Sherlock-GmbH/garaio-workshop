# Drehbuch: AI-First Software Development (3h)

## Übersicht
| Block | Zeit | Dauer |
|-------|------|-------|
| Intro | 09:00–09:30 | 30 min |
| AI-First Lifecycle | 09:30–10:30 | 60 min |
| *Pause* | 10:30–10:45 | 15 min |
| Hands-On | 10:45–11:45 | 60 min |
| Q&A + Diskussion | 11:45–12:15 | 30 min |

---

## Block 1: Intro (30 min)
**09:00–09:30**

### Ziel
Mindset-Shift: Warum 95% scheitern, warum Neugier der Schlüssel ist

### Ablauf
- **09:00** (5 min) — Begrüssung, Vorstellung
- **09:05** (10 min) — Die 5% vs 95% Story
  - Statistik: 78% nutzen AI, 5% Nutzen
  - Was machen die 5% anders? → Integration statt Experiment
- **09:15** (10 min) — Neugier-Mindset
  - Wieder zu Kindern werden
  - Fragen > Antworten
  - Demo: "Dumme Fragen" an Claude stellen
- **09:25** (5 min) — Verification First
  - DAS wichtigste Prinzip
  - 2-3x Qualität durch konsequentes Prüfen

---

## Block 2: AI-First Lifecycle (60 min)
**09:30–10:30**

### Ziel
Den kompletten Workflow verstehen: Requirements → Spec → Code → Test → Deploy → Ops

### Ablauf
- **09:30** (10 min) — Explore Phase
  - Problem verstehen mit AI
  - Context Engineering: CLAUDE.md < 100 Zeilen
  - Demo: Projekt-Setup
- **09:40** (10 min) — Plan Phase
  - Spec schreiben lassen
  - Explore → Plan → Code Workflow
  - Demo: Feature-Spec generieren
- **09:50** (15 min) — Code Phase
  - Copilot vs Agent (Autocomplete vs autonome Tasks)
  - Live-Demo: Feature implementieren mit Claude Code
- **10:05** (10 min) — Test & Verify
  - Verification First in der Praxis
  - Tests generieren lassen
  - Review-Workflow
- **10:15** (10 min) — Agent Teams + MCP
  - Mehrere Agents orchestrieren
  - MCP als Tool-Connector
  - Ausblick: Claude Cowork für Non-Coders
- **10:25** (5 min) — Zusammenfassung Block 2

### Pause (15 min)
**10:30–10:45**

---

## Block 3: Hands-On (60 min)
**10:45–11:45**

### Ziel
Teilnehmer arbeiten selbst im Kalkulationstool-Repo (echte Bugs, echte Security Issues)

**→ Detaillierte Exercises: siehe `exercises-kalkulationstool.md`**

### Ablauf
- **10:45** (5 min) — Setup-Check
  - Claude Code läuft? Repo geklont?
  - Quick Test: "Was ist dieses Projekt?"
- **10:50** (10 min) — Exercise 1: Context Engineering
  - CLAUDE.md lesen und verstehen
  - Architektur-Fragen stellen (CQRS, Auth)
  - Reflexion: Was fehlt in CLAUDE.md?
- **11:00** (20 min) — Exercise 2: Bug #191 fixen
  - **Echter Bug:** Auftragsbeginn-Datum fällt um 1 Tag zurück (UTC-Problem)
  - Explore → Plan → Code durchspielen
  - Unit Test schreiben (Verification First!)
- **11:20** (15 min) — Exercise 3: Security Issue fixen
  - Security Audit lesen (4 Findings)
  - Fehlende [Authorize] Attribute fixen
  - Debug-Endpoints absichern
- **11:35** (10 min) — Showcase
  - 2-3 Teilnehmer zeigen ihre Lösung
  - Diskussion: Was funktionierte? Was nicht?

---

## Block 4: Q&A + Diskussion (30 min)
**11:45–12:15**

### Ablauf
- **11:45** (15 min) — Offene Fragen
  - Was ist unklar geblieben?
  - Wo seht ihr Hürden in eurem Alltag?
- **12:00** (10 min) — Diskussion
  - Wie sieht euer AI-First Workflow morgen aus?
  - Was nehmt ihr mit?
- **12:10** (5 min) — Wrap-Up
  - Ressourcen teilen
  - Kontakt für Follow-up
  - Danke!

---

## Materialien
- [ ] Slides (optional, minimal)
- [ ] Demo-Repo: Kalkulationstool
- [ ] Handout: Setup-Guide (Englisch)
- [ ] CLAUDE.md Template
