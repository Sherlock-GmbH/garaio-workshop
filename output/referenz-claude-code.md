# Claude Code — Kurzreferenz

> **Wenn du unsicher bist, frag einfach Claude Code.** Tippe deine Frage ins Terminal — Claude kennt seine eigenen Features besser als jedes Dokument. Probier's aus: `was kannst du alles?` oder `wie erstelle ich Skills?`

---

## Essential Commands

| Command | Was es tut |
|---------|-----------|
| `claude` | Interaktiven Modus starten |
| `claude "task"` | Einmal-Aufgabe ausführen |
| `claude -p "query"` | Query ausführen, dann beenden (für Scripts/CI) |
| `claude -c` | Letzte Konversation fortsetzen |
| `claude -r` | Frühere Konversation auswählen und fortsetzen |
| `claude commit` | Git Commit erstellen |

### Innerhalb einer Session

| Command | Was es tut |
|---------|-----------|
| `/help` | Verfügbare Befehle anzeigen |
| `/clear` | Konversation zurücksetzen (wichtig zwischen Tasks!) |
| `/compact` | Kontext zusammenfassen um Platz zu sparen |
| `/init` | CLAUDE.md automatisch generieren |
| `/login` | Account wechseln |
| `/permissions` | Berechtigungen konfigurieren |
| `/hooks` | Hooks interaktiv einrichten |
| `Shift+Tab` | Plan Mode umschalten (nur planen, nicht coden) |
| `Esc` | Claude stoppen (Kontext bleibt erhalten) |
| `Esc + Esc` | Rewind-Menü öffnen (Code + Konversation zurücksetzen) |
| `exit` / `Ctrl+C` | Claude Code beenden |

---

## Die `~/.claude` Struktur

```
~/.claude/
├── CLAUDE.md              # Globale Anweisungen (gilt für ALLE Projekte)
├── settings.json          # Globale Einstellungen (Permissions, etc.)
└── projects/              # Projekt-spezifische Daten
    └── <hash>/
        └── sessions/      # Gespeicherte Konversationen
```

### CLAUDE.md — Wo sie leben kann

| Ort | Scope | Tipp |
|-----|-------|------|
| `~/.claude/CLAUDE.md` | Global — alle Sessions | Persönliche Präferenzen, globale Regeln |
| `./CLAUDE.md` (Projekt-Root) | Projekt — ins Git einchecken! | Build-Commands, Architektur, Konventionen |
| `./subfolder/CLAUDE.md` | Verzeichnis — on demand geladen | Modul-spezifische Regeln (z.B. pro Microservice) |

**Wichtig:** CLAUDE.md wird bei **jeder** Interaktion geladen. Halte sie kurz (<100 Zeilen). Frage dich bei jeder Zeile: *"Würde Claude ohne diese Zeile Fehler machen?"* Wenn nein → löschen.

### Was gehört rein?

✅ **Ja:**
- Build/Test-Commands die Claude nicht raten kann
- Code-Style-Regeln die vom Standard abweichen
- Architektur-Entscheidungen spezifisch fürs Projekt
- Dev-Environment-Eigenheiten (Env-Vars, Ports)
- Häufige Gotchas und nicht-offensichtliches Verhalten

❌ **Nein:**
- Alles was Claude aus dem Code ablesen kann
- Standard-Konventionen die Claude bereits kennt
- Detaillierte API-Dokumentation (stattdessen verlinken)
- Datei-für-Datei-Beschreibungen der Codebase
- Selbstverständliches wie "schreib sauberen Code"

### Beispiel

```markdown
# CLAUDE.md

## Build & Run
- Backend: `dotnet build` / `dotnet run --project Api`
- Frontend: `npm ci && ng serve` (Proxy auf :5022)
- Tests: `dotnet test` (xUnit + SQLite in-memory)

## Architecture
- CQRS: Commands in Api.Core/Commands/, Queries in Api.Core/Queries/
- EF Core mit SQL Server, Migrations in Sql/Migrations/

## Conventions
- `var` bevorzugt, Expression Bodies wo sinnvoll
- Angular: Standalone Components, NgRx für State
- Immer einzelne Tests laufen lassen, nicht die ganze Suite
```

### `@`-Imports in CLAUDE.md

CLAUDE.md kann auf andere Dateien verweisen:

```markdown
Projektübersicht: @README.md
API-Dokumentation: @docs/api-reference.md
Persönliche Overrides: @~/.claude/my-preferences.md
```

---

## Permissions & Sicherheit

Claude Code fragt standardmässig bei jeder Dateiänderung und jedem Shell-Befehl um Erlaubnis.

**Optionen:**
- **Allowlists:** Bestimmte Tools erlauben (z.B. `npm run lint`, `git commit`)
- **Sandboxing:** OS-Level-Isolation — Claude arbeitet frei, aber eingegrenzt
- **`--dangerously-skip-permissions`:** Alles erlauben (nur für sichere, abgegrenzte Tasks)

Konfiguration via `/permissions` oder `.claude/settings.json`.

---

## Skills

Skills erweitern Claudes Wissen mit projekt- oder domänenspezifischen Informationen. Claude lädt sie **on demand** — sie belasten nicht jede Session wie CLAUDE.md.

### Skill erstellen

```
.claude/skills/
└── api-conventions/
    └── SKILL.md
```

```markdown
---
name: api-conventions
description: REST API Konventionen für unsere Services
---
# API Conventions
- Kebab-case für URL-Pfade
- CamelCase für JSON-Properties
- Immer Pagination für List-Endpoints
```

### Skill als Workflow (aufrufbar via `/skill-name`)

```markdown
---
name: fix-issue
description: GitHub Issue fixen
disable-model-invocation: true
---
Analysiere und fixe das GitHub Issue: $ARGUMENTS.

1. `gh issue view` für Issue-Details
2. Problem verstehen
3. Relevante Files finden
4. Fix implementieren
5. Tests schreiben und laufen lassen
6. Commit erstellen und PR öffnen
```

Aufruf: `/fix-issue 1234`

---

## Subagents

Subagents laufen in **eigenem Kontext** mit eigenen Tools — ideal für Aufgaben die viele Files lesen, ohne den Hauptkontext zu verschmutzen.

```markdown
<!-- .claude/agents/security-reviewer.md -->
---
name: security-reviewer
description: Reviews code for security vulnerabilities
tools: Read, Grep, Glob, Bash
model: opus
---
Du bist ein Senior Security Engineer. Review Code auf:
- Injection Vulnerabilities (SQL, XSS, Command Injection)
- Auth/Authorization Flaws
- Secrets oder Credentials im Code
- Unsichere Datenverarbeitung
```

Aufruf: *"Use a subagent to review this code for security issues."*

---

## Hooks

Hooks sind **deterministische** Scripts die an bestimmten Punkten in Claudes Workflow laufen — im Gegensatz zu CLAUDE.md-Anweisungen (die nur "empfohlen" sind).

Claude kann Hooks für dich schreiben:
```
"Schreib einen Hook der eslint nach jedem File-Edit laufen lässt"
"Schreib einen Hook der Writes in den migrations/ Ordner blockt"
```

Konfiguration: `/hooks` oder `.claude/settings.json`

---

## MCP (Model Context Protocol)

MCP verbindet Claude mit externen Datenquellen. Konfiguration via `.mcp.json` im Projekt-Root:

```json
{
  "mcpServers": {
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp"]
    }
  }
}
```

Claude erkennt die Datei automatisch und hat sofort Zugriff auf die konfigurierten Tools.

→ Siehe **Handout: MCP Use Cases** für konkrete Beispiele.

---

## Kontext-Management — Der wichtigste Skill

> **Claudes Context Window ist die wichtigste Ressource.** Performance sinkt wenn es voll wird.

**Best Practices:**
- `/clear` zwischen **unabhängigen Tasks** — nicht alles in eine Session packen
- `/compact` wenn die Session lang wird
- **Subagents** für Recherche nutzen (liest Files in eigenem Kontext)
- Wenn Claude 2× den gleichen Fehler macht → `/clear` + besserer Prompt statt weiter korrigieren
- `Esc + Esc` → Rewind statt "mach das rückgängig"

---

## Anti-Patterns

| ❌ Anti-Pattern | ✅ Besser |
|----------------|----------|
| Eine endlose Session für alles | `/clear` zwischen Tasks |
| Claude 3× korrigieren | `/clear` + besserer initialer Prompt |
| CLAUDE.md mit 500 Zeilen | Unter 100 Zeilen, Rest in Skills |
| "Sieht richtig aus" → Ship it | Tests/Verification **immer** |
| "Untersuche mal die Codebase" (unscoped) | Subagent oder scope eingrenzen |
| Direkt loscodieren | Explore → Plan → Code |

---

## Weiterführende Referenz

- **Quickstart:** https://code.claude.com/docs/en/quickstart
- **Best Practices:** https://code.claude.com/docs/en/best-practices
- **Common Workflows:** https://code.claude.com/docs/en/common-workflows
- **CLAUDE.md Deep Dive:** https://code.claude.com/docs/en/memory
- **Skills:** https://code.claude.com/docs/en/skills
- **Subagents:** https://code.claude.com/docs/en/sub-agents
- **MCP:** https://code.claude.com/docs/en/mcp
- **Hooks:** https://code.claude.com/docs/en/hooks-guide
- **Plugins:** https://code.claude.com/docs/en/plugins
- **Permissions:** https://code.claude.com/docs/en/permissions
- **CLI Reference:** https://code.claude.com/docs/en/cli-reference
- **Extend Claude Code:** https://code.claude.com/docs/en/features-overview

---

> 💡 **Tipp:** Wenn du nicht weiterkommst, frag einfach Claude Code selbst. `wie mache ich X?` funktioniert fast immer. Claude kennt seine eigenen Docs und kann dir Schritt für Schritt helfen.
