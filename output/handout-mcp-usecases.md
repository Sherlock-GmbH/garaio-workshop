# MCP — Killer Use Cases für Entwickler
*Stand: März 2026*

> **MCP (Model Context Protocol)** ist ein offener Standard, der AI-Assistenten mit externen Tools und Datenquellen verbindet — wie USB für AI. Einmal konfiguriert, kann Claude (oder jeder andere MCP-kompatible Assistant) direkt auf eure Systeme zugreifen.

## 🌍 MCP ist Industrie-Standard

MCP wurde November 2024 von Anthropic eingeführt und hat sich zum **universellen Standard** entwickelt:

- **Adoptiert von:** Anthropic, OpenAI, Google, Microsoft, Amazon, Salesforce
- **97 Millionen monatliche SDK-Downloads** (Python + TypeScript, Stand Feb 2026)
- Dezember 2025: Übergabe an die **Linux Foundation** (Agentic AI Foundation)
- Unterstützt in: Claude Code, ChatGPT, Gemini, Copilot, Cursor, VS Code, Windsurf

Ein MCP Server den ihr für Claude baut, funktioniert automatisch auch mit ChatGPT, Copilot & Co.

## Setup (30 Sekunden)

```json
// .mcp.json im Projekt-Root
{
  "mcpServers": {
    "mein-tool": {
      "command": "npx",
      "args": ["-y", "@beispiel/mcp-server"]
    }
  }
}
```

Claude Code erkennt die Datei automatisch. Fertig.

---

## 🗄️ Datenbank (Supabase, Postgres, SQL Server, SQLite)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **Live-Debugging** | *"Warum sieht User X seine Offerten nicht? Prüf seine Rollen und Berechtigungen in der DB."* |
| **Schema-Exploration** | *"Wie hängen Offers, Rooms und RoomGroups zusammen? Zeichne mir die Beziehungen."* |
| **Query-Entwicklung** | *"Schreib mir die Query für den Report und teste sie gegen echte Daten."* |
| **Migration-Check** | *"Stimmt das DB-Schema noch mit meinen EF Entities überein?"* |
| **Datenqualität** | *"Finde verwaiste Records — Offers ohne Customer, Rooms ohne RoomGroup."* |

**MCP Server:** `@modelcontextprotocol/server-postgres`, `supabase mcp`, `mcp-server-sqlite`

---

## 🔧 DevOps (Azure DevOps, GitHub, Jira)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **Sprint-Analyse** | *"Welche Items sind at risk? Was ist seit 2 Wochen unassigned?"* |
| **Issue → Code → PR** | *"Nimm Bug #191, finde den Code, schlag einen Fix vor, erstelle den PR."* |
| **Pipeline-Debugging** | *"Der letzte Build ist fehlgeschlagen — was ist die Ursache?"* |
| **Release Notes** | *"Generiere Release Notes aus allen geschlossenen PRs seit dem letzten Tag."* |

**MCP Server:** `@azure-devops/mcp`, `@modelcontextprotocol/server-github`

---

## 📁 Knowledge Base (Confluence, Notion, SharePoint)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **Onboarding** | *"Lies die gesamte Projektdoku und erstelle mir einen Überblick."* |
| **Doku aktualisieren** | *"Die Wiki-Seite sagt .NET 7, der Code ist auf .NET 8 — fix das."* |
| **Wissenssuche** | *"Wo ist dokumentiert, wie die Authentifizierung funktioniert?"* |

**MCP Server:** `mcp-confluence`, `mcp-notion`

---

## 🔍 Monitoring (Sentry, Datadog, Application Insights)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **Error-Triage** | *"Welche Errors sind seit dem letzten Deploy neu?"* |
| **Performance** | *"Zeig mir die langsamsten Endpoints der letzten 24h und schlag Optimierungen vor."* |
| **Korrelation** | *"Der Fehler tritt nur bei Users mit Rolle X auf — warum?"* |

**MCP Server:** `mcp-sentry`, `mcp-server-datadog`

---

## 💬 Kommunikation (Slack, Teams)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **Context-Gathering** | *"Was wurde im #backend-Channel letzte Woche über die Migration diskutiert?"* |
| **Standup-Prep** | *"Fasse zusammen, was seit gestern passiert ist."* |

**MCP Server:** `@anthropic/mcp-server-slack`

---

## 🏗️ Infrastruktur (Terraform, Azure, AWS)

| Use Case | Beispiel-Prompt |
|----------|----------------|
| **IaC Review** | *"Vergleiche mein Bicep-Template mit dem tatsächlich deployten Zustand."* |
| **Cost Analysis** | *"Welche Resources kosten am meisten?"* |
| **Security Scan** | *"Prüfe meine App Settings — welche Secrets liegen nicht im Key Vault?"* |

**MCP Server:** `azure-mcp-server`, `mcp-server-aws`

---

## Der geschlossene Loop

```
Issue (DevOps MCP)
  → Code verstehen (Filesystem)
  → Daten prüfen (DB MCP)
  → Fix implementieren (Claude Code)
  → Tests schreiben & laufen lassen
  → PR erstellen (DevOps MCP)
  → Monitoring prüfen (Observability MCP)
```

**Alles aus einer Oberfläche. Keine Context-Switches.**

---

---

## 🔝 Die beliebtesten MCP Server 2026

| Server | Beschreibung |
|--------|-------------|
| **Context7** | Injiziert versionsspezifische Docs & Code-Beispiele direkt in Prompts |
| **Playwright** | Deterministische Browser-Automation via Accessibility Snapshots |
| **Sentry** | Production Error Tracking (gehostet, kein Install nötig) |
| **Firecrawl** | Web Scraping als MCP Tool |
| **Atlassian** | Jira/Confluence Integration (Docker + Streamable HTTP) |
| **Postgres/Supabase** | Direkter DB-Zugriff aus dem Agent |

Kuratierte Liste mit 50+ Servern: https://claudefa.st/blog/tools/mcp-extensions/best-addons

---

## 📰 Was gerade passiert (März 2026)

### 2026 Roadmap (veröffentlicht 12. März)
Vier Prioritäten der MCP-Maintainer:

1. **Transport Evolution** — SSE wird deprecated, Migration zu **Streamable HTTP** (Deadline: 1. April 2026). Stateless Sessions für horizontales Scaling. `.well-known` Discovery.
2. **Agent Communication** — Tasks Primitive (SEP-1686) experimentell live. Retry-Semantik und Expiry Policies.
3. **Governance** — Working Groups können SEPs selbst akzeptieren. Contributor Ladder.
4. **Enterprise Readiness** — Audit Trails, SSO-Auth, Gateway Behavior.

### Neue SDKs
- **Microsoft MCP C# SDK v1.0** — Full Spec Support inkl. OAuth 2.1, Elicitation, Tool Icons
- **Elicitation**: MCP Server können jetzt strukturierten User-Input anfordern während der Tool-Ausführung

### ⚠️ Security — Das muss man wissen
- **30 CVEs in 60 Tagen** — MCP Security ist ein aktives Problemfeld
- **8'000+ MCP Server exposed** (öffentlich erreichbar ohne Auth)
- Hauptrisiken:
  - **Tool Poisoning**: Malicious Instructions in Tool-Descriptions → Agent exfiltriert Daten
  - **Confused Deputy**: Zu breite Token-Scopes erlauben Zugriff über legitime Tools
  - **Prompt Injection** über manipulierte Tool-Responses
- **Best Practice**: MCP Server immer lokal oder hinter Auth betreiben, Tokens minimal scopen
- Guide: [Securing MCP: Defense-First Architecture](https://christian-schneider.net/blog/securing-mcp-defense-first-architecture/)

---

## Ressourcen

- **MCP Spec & Roadmap:** https://modelcontextprotocol.io
- **MCP Server Registry:** https://github.com/modelcontextprotocol/servers
- **MCP Roadmap Blog Post:** https://blog.modelcontextprotocol.io/posts/2026-mcp-roadmap/
- **Azure DevOps MCP:** https://learn.microsoft.com/azure/devops/mcp-server
- **Claude Code Docs:** https://docs.anthropic.com/en/docs/claude-code
- **MCP Security Risks (Veeam):** https://www.veeam.com/blog/model-context-protocol-security-risks.html
- **MCP vs A2A Vergleich:** https://dev.to/pockit_tools/mcp-vs-a2a-the-complete-guide-to-ai-agent-protocols-in-2026-30li
