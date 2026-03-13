---
theme: default
title: AI-First Software Development
author: Sherlock GmbH
addons:
  - slidev-addon-excalidraw
drawings:
  persist: false
---

# AI-First Software Development

### Vom Experiment zum integrierten Workflow

<br>

**GARAIO Dev Camp** · 18. März 2026

<!--
Willkommen zum Dev Camp. Ich bin Lukas, Sherlock GmbH.

Heute reden wir nicht über "AI ist cool" — das wisst ihr schon.
Wir reden darüber, warum fast alle Firmen mit AI scheitern, und was die wenigen anders machen, die es nicht tun.

Und vor allem: ihr werdet heute selber coden. Mit Claude Code, eurem eigenen Repo.
-->

---

# Agenda

| Block | Zeit | Inhalt |
|-------|------|--------|
| 🧠 Intro | 09:00–09:30 | Warum 95% scheitern |
| 🔄 AI-First Lifecycle | 09:30–10:30 | Der komplette Workflow |
| ☕ Pause | 10:30–10:45 | |
| 🛠️ Hands-On | 10:45–11:45 | Bugs fixen im Kalkulationstool |
| 💬 Q&A | 11:45–12:15 | Diskussion |

<!--
Das ist unser Plan für die nächsten 3 Stunden.

Der wichtigste Teil ist das Hands-On — ihr arbeitet mit eurem eigenen Repo. Alles davor ist Kontext, damit ihr wisst WARUM ihr es so macht, nicht nur WIE.
-->

---
layout: center
---

# Teil 1: Warum 95% scheitern

<!--
Los geht's mit einer unbequemen Statistik.
-->

---

# Die Realität

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

## 78%
der Firmen nutzen AI

</div>
<div>

## 5%
erzielen messbaren Nutzen

</div>
</div>

<br>

> Quelle: Noser/Stanford/BCG

<!--
78% der Firmen nutzen AI in irgendeiner Form. Das klingt nach viel.

Aber nur 5% erzielen damit messbaren geschäftlichen Nutzen.

Woran liegt das? Nicht an der Technologie. Nicht am Budget.
-->

---

# Warum scheitern die 95%?

<v-clicks>

- 🏝️ **Fragmentierung** — AI-Tools werden isoliert eingesetzt, nicht in Workflows integriert
- 🎯 **Kein klares Ziel** — Technologie wird adoptiert ohne definierte Business-Outcomes
- 🧪 **Experiment-Falle** — Vielversprechende Piloten werden nie skaliert
- 🙈 **Fehlende Führung** — Kein Management-Alignment über Ziele und Grenzen

</v-clicks>

<!--
(Click durch die Punkte)

Fragmentierung: "Wir haben Copilot" — ja, als Autocomplete. Nicht als Teil des Workflows.

Kein klares Ziel: "Wir machen jetzt AI" ist kein Ziel. "Wir halbieren die Bug-Fix-Zeit" ist eins.

Experiment-Falle: Die Piloten funktionieren. Aber niemand skaliert sie. Warum? Weil es unbequem ist, echte Prozesse umzustellen.

Und der Klassiker: Das Management sagt "macht mal AI" ohne zu definieren was Erfolg heisst.
-->

---

# Wieder zu Kindern werden

<v-clicks>

- 🧒 Kinder sind **neugierig** — sie fragen "warum?" statt "wie rechtfertigen wir das?"
- 🔁 Sie **iterieren** — scheitern, starten neu, scheitern besser
- 🚫 Die 95% managen AI wie ein Wasserfall-Projekt
- ✅ Die 5% verhalten sich wie Kinder: neugierig, iterativ, fehlerfreundlich

</v-clicks>

<br>

> "Curiosity fuels innovation, but structure sustains it. Without one, you stall. Without the other, you spiral." — CIO Magazine

<!--
Was unterscheidet die 5% die es schaffen?

Sie sind neugierig. Sie probieren Dinge aus, BEVOR sie einen Business Case haben. Sie scheitern schnell und lernen daraus.

Die 95% versuchen AI in einen Wasserfallprozess zu pressen. Anforderungen, Ausschreibung, Evaluation, Pilotprojekt, Skalierung. Bis Schritt 4 fertig ist, hat sich die Technologie dreimal geändert.

Der Punkt ist nicht "seid chaotisch". Der Punkt ist: Neugier plus Struktur. Beides zusammen.
-->

---

# Warum niemand "die Antwort" hat

<v-clicks>

- 🤯 **Emergent Abilities** — LLMs entwickeln Fähigkeiten die plötzlich und unerwartet auftauchen
- 🔬 Kein wissenschaftlicher Konsens über die Erklärung
- 💬 Ilya Sutskever (OpenAI Mitgründer, 2022): *"It may be that today's large neural networks are slightly conscious"*
- 🤷 Wir können erklären WAS passiert, nicht vollständig WARUM

</v-clicks>

<br>

> Wenn nicht mal die Entwickler dieser Modelle erklären können warum sie so gut funktionieren — wer kann euch dann eine fertige Roadmap verkaufen?

<!--
Kurzer Exkurs: Warum kann euch niemand sagen "so macht man AI richtig"?

Weil nicht mal die Leute die diese Modelle bauen vollständig verstehen warum sie funktionieren. Das Stichwort heisst "Emergent Abilities" — Fähigkeiten die ab einer bestimmten Modellgrösse plötzlich auftauchen, ohne dass man darauf trainiert hat.

Ilya Sutskever — einer der OpenAI-Gründer — hat 2022 getweeted, die Modelle könnten "leicht bewusst" sein. Massive Kontroverse, aber es zeigt: selbst die Macher staunen über ihre eigenen Systeme.

Ergo: Jede Firma die euch eine "fertige Enterprise AI Transformation Roadmap" verkauft, lügt. Ihr müsst euren eigenen Weg finden. Ich kann heute einen Samen pflanzen — den Garten müsst ihr selbst anlegen.
-->

---

# DAS wichtigste Prinzip

<div class="text-center mt-16">
<h2 class="text-6xl font-bold">Verification First</h2>
<p class="text-2xl mt-4 text-gray-500">2–3× Qualitätssteigerung durch konsequentes Prüfen</p>
</div>

<!--
Bevor wir in den Lifecycle eintauchen — DAS eine Prinzip das ihr heute mitnehmt, wenn ihr sonst alles vergesst:

Verification First.

AI macht Fehler. Punkt. Kein "manchmal", kein "selten". Sie macht Fehler. Und sie ist verdammt überzeugend dabei.

Der Unterschied zwischen Leuten die mit AI produktiv sind und Leuten die's nicht sind: Die produktiven prüfen ALLES. Nicht weil sie der AI misstrauen, sondern weil sie wissen: Die AI braucht eine Feedback-Schleife. Tests, Screenshots, CLI-Output — alles was der AI zeigt ob sie richtig liegt.

Studien zeigen 2-3x Qualitätssteigerung allein durch konsequentes Verifizieren. Nicht mehr AI, nicht bessere Prompts. Einfach prüfen.
-->

---
layout: center
---

# Teil 2: AI-First Lifecycle

### Requirements → Spec → Code → Test → Deploy → Ops

<!--
Jetzt wird's konkret. Wir gehen den kompletten Lifecycle durch — von der Anforderung bis zum laufenden System. An jedem Schritt: wo arbeitet der Agent, wo der Mensch.
-->

---

# Copilot vs. Agent

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### 🤖 Copilot
- Autocomplete auf Steroiden
- Reagiert auf deinen Cursor
- Zeile für Zeile
- GitHub Copilot, Cursor Tab

</div>
<div>

### 🧠 Agent
- Autonome Tasks
- Liest, plant, implementiert
- Ganze Features
- Claude Code, Copilot Agent Mode

</div>
</div>

<br>

> Beides hat seinen Platz — aber der **Hebel** liegt bei Agents.

<!--
Kurz der Unterschied, weil das oft verwechselt wird.

Copilot: ihr tippt, es vervollständigt. Gut für Boilerplate, Autocomplete, schnelle Snippets. Das kennt ihr von GitHub Copilot.

Agent: ihr gebt eine Aufgabe, der Agent erledigt sie. Er liest den Code, versteht den Kontext, plant eine Lösung, implementiert sie, testet sie. Claude Code ist so ein Agent.

Beides hat seinen Platz. Aber der grosse Hebel — die 10x Produktivitätssteigerung — kommt von Agents. Nicht von schnellerem Autocomplete.
-->

---

# Context Engineering

<div class="text-center mt-8">
<h2 class="text-4xl">CLAUDE.md < 100 Zeilen</h2>
<p class="text-xl mt-4 text-gray-500">Concise & ruthless</p>
</div>

<br>

```markdown
# CLAUDE.md
## Project Overview
.NET 8 API + Angular 19 Frontend, CQRS, Azure SQL

## Build & Run
dotnet build / ng serve

## Architecture
Commands in Api.Core/Commands/, Queries in Api.Core/Queries/
```

<br>

> **Garbage in, garbage out** — der Agent ist nur so gut wie sein Kontext.

<!--
Context Engineering ist DER Skill für die Arbeit mit AI Agents.

CLAUDE.md ist eine Datei im Repo-Root, die Claude Code automatisch liest. Darin steht: Was ist das Projekt, wie baut man es, wie ist die Architektur, was sind die Konventionen.

Wichtig: Unter 100 Zeilen. Concise and ruthless. Alles was drinsteht wird bei JEDER Interaktion geladen. Zu viel Kontext = Agent wird langsam und verwirrt.

Garbage in, garbage out. Wenn CLAUDE.md Müll ist, ist der Output Müll. Wenn sie gut ist, ist der Agent sofort produktiv.
-->

---

# Explore → Plan → Code

<div class="grid grid-cols-3 gap-6 mt-12">
<div class="text-center">

### 🔍 Explore
Problem verstehen.
Code lesen. Fragen stellen.

*"Wo wird ein Vertrag aus einer Offerte erstellt?"*

</div>
<div class="text-center">

### 📋 Plan
Lösung planen.
Spec schreiben. Approach definieren.

*"Schreib eine Spec mit 3-5 Punkten für den Fix."*

</div>
<div class="text-center">

### 💻 Code
Implementieren.
Tests zuerst. Dann Code.

*"Implementiere den Fix und schreib einen Unit Test."*

</div>
</div>

<br>

> **Nie direkt loscodieren.** Erst verstehen, dann planen, dann umsetzen.

<!--
Der wichtigste Workflow wenn ihr mit einem AI Agent arbeitet: Explore, Plan, Code.

Explore: Der Agent liest den Code, versteht das Problem, stellt euch Fragen. IHR stellt dem Agent Fragen. "Wo im Code passiert X?" "Welche Dateien sind betroffen?"

Plan: BEVOR eine einzige Zeile Code geschrieben wird, lasst den Agent einen Plan schreiben. Was wird geändert, warum, welche Risiken gibt es.

Code: Erst jetzt wird implementiert. Und zwar idealerweise: Test zuerst, dann Code.

Der häufigste Fehler: direkt loscodieren ohne Explore und Plan. Dann fixen wir das Falsche oder machen mehr kaputt als wir reparieren.
-->

---

# Agent Teams + MCP

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Agent Teams
- Mehrere Agents parallel
- Einer plant, einer coded, einer testet
- Git Worktrees für Isolation
- `claude --worktree`

</div>
<div>

### MCP (Model Context Protocol)
- **USB für AI** — Plug & Play
- Agent greift auf externe Tools zu
- DB, DevOps, Monitoring, Slack
- Offener Standard

</div>
</div>

<!--
Zwei Ausblicke die ihr im Hinterkopf behalten solltet:

Agent Teams: Statt einem Agent der alles macht, mehrere Agents die parallel arbeiten. Einer analysiert, einer implementiert, einer schreibt Tests. Claude Code unterstützt das über Git Worktrees.

MCP — Model Context Protocol: Ein offener Standard der AI Agents mit externen Tools verbindet. Wie USB — einmal eingesteckt, funktioniert's. Claude kann damit direkt auf eure Datenbank zugreifen, Azure DevOps Work Items lesen, Slack-Channels durchsuchen. Alles aus einer Oberfläche.

Dazu gibt's nachher noch ein Handout mit konkreten Use Cases.
-->

---

# MCP in Aktion

```json
// .mcp.json im Projekt-Root
{
  "mcpServers": {
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp"]
    }
  }
}
```

<br>

**Demo:** Claude spricht direkt mit der Datenbank

<!--
So sieht das konkret aus. Eine JSON-Datei im Repo-Root, und Claude Code hat plötzlich Zugriff auf eure Datenbank.

(LIVE DEMO: Supabase MCP zeigen — Claude fragt die DB ab, zeigt Schema, findet Daten)

Stellt euch vor: Bug Report kommt rein, Claude liest das Ticket aus Azure DevOps, schaut in die DB ob die Daten stimmen, findet den Bug im Code, und schlägt einen Fix vor. Alles ohne dass ihr zwischen Browser, Terminal und IDE wechselt.
-->

---

# Der geschlossene Loop

```
📋 Issue lesen        (DevOps MCP)
   ↓
🔍 Code verstehen     (Filesystem)
   ↓
🗄️ Daten prüfen       (DB MCP)
   ↓
💻 Fix implementieren  (Claude Code)
   ↓
✅ Tests schreiben     (Claude Code)
   ↓
🚀 PR erstellen        (DevOps MCP)
   ↓
📊 Monitoring prüfen   (Observability MCP)
```

> **Alles aus einer Oberfläche. Keine Context-Switches.**

<!--
Das ist die Vision: Ein geschlossener Loop. Vom Issue über Code und Tests bis zum PR und Monitoring. Alles in einem Tool.

Heute zeigen wir euch die ersten Schritte dieses Loops im Hands-On.
-->

---
layout: center
---

# ☕ Pause

### 15 Minuten — danach wird's praktisch

<!--
15 Minuten Pause. Danach arbeitet ihr selber.

Bitte prüft in der Pause:
- Claude Code läuft? (claude --version)
- Repo geklont?
- Azure CLI eingeloggt?
-->

---
layout: center
---

# Teil 3: Hands-On

### Echte Bugs. Echtes Repo. Echte Security Issues.

<!--
Jetzt wird's ernst. Ihr arbeitet mit dem echten Kalkulationstool-Repo. Echte Bugs, echte Security Issues — keine Spielzeug-Beispiele.

Die Exercises sind so aufgebaut, dass ihr den Explore-Plan-Code Workflow selber durchspielt.
-->

---

# Setup-Check (5 min)

```bash
cd Kalkulationstool
claude
```

Im Claude-Prompt:
```
Was ist dieses Projekt? Gib mir einen kurzen Überblick.
```

<br>

✅ Claude sollte CLAUDE.md lesen und die Architektur erklären

<!--
Erster Schritt: Stellt sicher dass alles läuft. 

Öffnet das Terminal im Kalkulationstool-Ordner. Startet Claude. Fragt "Was ist dieses Projekt?"

Claude sollte CLAUDE.md automatisch lesen und euch die Architektur erklären: .NET 8, Angular 19, CQRS, Azure. Wenn das funktioniert, seid ihr ready.

Wer Probleme hat: Hand hoch, wir helfen.
-->

---

# Exercise 1: Context Engineering (10 min)

### CLAUDE.md verstehen

1. **CLAUDE.md lesen** — `Zeig mir den Inhalt von CLAUDE.md`
2. **Architektur-Fragen stellen:**
   - *"Erkläre mir das CQRS Pattern in diesem Projekt."*
   - *"Wie funktioniert die Authentifizierung?"*
3. **Reflexion:** Was hat Claude aus CLAUDE.md gelernt? Was fehlt?

<br>

> **Takeaway:** CLAUDE.md < 100 Zeilen — concise & ruthless.

<!--
Exercise 1 ist Aufwärmen. Ihr schaut euch CLAUDE.md an und stellt Architektur-Fragen.

Das Ziel: Versteht, WIE Claude den Kontext nutzt. Fragt nach CQRS, nach der Auth — seht wie Claude die Infos aus CLAUDE.md kombiniert mit dem Code.

Und dann überlegt: Was fehlt in CLAUDE.md? Welche Infos wären nützlich gewesen?
-->

---

# Exercise 2: Bug #191 fixen (20 min)

### Auftragsbeginn-Datum fällt um 1 Tag zurück 🐛

**Explore** (5 min)
```
Lies todo.md und erkläre mir Bug #191.
Wo wird ein Vertrag aus einer Offerte erstellt?
```

**Plan** (5 min)
```
Was ist die wahrscheinliche Ursache?
Schreib eine Spec (3-5 Punkte) für den Fix.
```

**Code** (10 min)
```
Implementiere den Fix. Schreib zuerst einen Unit Test.
```

<!--
Das ist die Haupt-Übung. Ein echter Bug: Wenn eine Offerte zum Vertrag umgewandelt wird, fällt das Auftragsbeginn-Datum um einen Tag zurück. Klassisches UTC/Timezone-Problem.

Wichtig: Nicht direkt loscodieren! Erst Explore — Claude soll den Bug erklären und den relevanten Code finden. Dann Plan — was ist die Ursache, wie fixen wir's. DANN erst Code — und zwar Test zuerst.

Ihr habt 20 Minuten. Das ist knapp — das ist Absicht. In der Praxis müsst ihr auch unter Zeitdruck entscheiden, wann "gut genug" ist.
-->

---

# Exercise 3: Security Issue (15 min)

### Fehlende `[Authorize]` Attribute 🔒

1. **Audit lesen:** `Lies security-audit-report.md, Fokus auf Vulnerability #2`
2. **Code finden:** `Welche Endpoints haben kein [Authorize]?`
3. **Fix:** `Füge die fehlenden Attribute hinzu`
4. **Review:** `Gibt es noch andere Stellen mit ähnlichen Problemen?`

<br>

> **Takeaway:** AI findet Issues schnell — aber **du verifizierst**.

<!--
Exercise 3: Security. Im Repo liegt ein Security Audit Report mit 4 Findings. Ihr fokussiert auf Vulnerability 2: fehlende Authorize-Attribute.

Lasst Claude den Report lesen, den Code finden, und den Fix implementieren. Aber — und das ist der Punkt — IHR prüft ob der Fix korrekt ist. Nicht blind akzeptieren.

Security Reviews sind ein perfekter AI Use Case. Die AI findet Muster schneller als ihr. Aber die Entscheidung ob ein Fix korrekt und ausreichend ist, bleibt bei euch.
-->

---

# Exercise 4: Azure CLI — Work Items (10 min)

### Claude als DevOps-Assistent 🔧

```
Nutze die Azure CLI, um alle offenen Bugs aufzulisten.
Die Commands findest du in todo.md.
```

```
Erstelle einen Bug-Report:
Titel, Severity, wie lange offen, Priorisierung.
```

```
Nimm Bug #191 — löst unser Fix das Problem?
```

<br>

> **Takeaway:** Code ↔ Issues verknüpfen. Keine Context-Switches.

<!--
Exercise 4: Wir nutzen Claude als DevOps-Brücke. In todo.md stehen Azure CLI Befehle für Azure DevOps Work Items.

Lasst Claude die Befehle nutzen, einen Bug-Report erstellen, und den Fix aus Exercise 2 mit dem Work Item verknüpfen.

Das zeigt den Mehrwert: Claude versteht sowohl den Code als auch die Issues. Es kann beides verbinden — ohne dass ihr zwischen Browser und IDE wechselt.
-->

---
layout: center
---

# Showcase

### 2-3 Freiwillige zeigen ihren Approach

- Welche Fragen habt ihr gestellt?
- Wo war Claude hilfreich, wo nicht?
- Was hat euch überrascht?

<!--
Wer möchte zeigen was er gemacht hat? 3 Minuten pro Person.

Mich interessiert nicht nur die Lösung — mich interessiert der WEG. Welche Fragen habt ihr gestellt? Wo musstet ihr Claude korrigieren? Was war überraschend gut, was überraschend schlecht?
-->

---

# Was ihr heute gelernt habt

<v-clicks>

1. **Explore → Plan → Code** — Nicht direkt loscodieren
2. **Verification First** — AI macht Fehler. Prüfen, prüfen, prüfen
3. **Context Engineering** — CLAUDE.md ist euer Freund
4. **MCP = USB für AI** — Einmal eingesteckt, einfach nutzen
5. **Geschlossener Loop** — Issue → Code → Test → Deploy aus einer Oberfläche

</v-clicks>

<!--
(Click durch die Punkte)

Fünf Dinge zum Mitnehmen.

Explore Plan Code. Verification First. Context Engineering. MCP. Und das Ziel: ein geschlossener Loop ohne Context-Switches.

Davon ist heute Nummer 1-3 am wichtigsten. Das könnt ihr morgen sofort einsetzen. MCP und der geschlossene Loop kommen danach.
-->

---

# Ressourcen

- 📄 **Claude Code Docs:** docs.anthropic.com/en/docs/claude-code
- 🔌 **MCP Registry:** github.com/modelcontextprotocol/servers
- 🏗️ **Azure DevOps MCP:** learn.microsoft.com/azure/devops/mcp-server
- 📋 **MCP Use Cases Handout:** Habt ihr bekommen!

<br>

### Setup für morgen
```bash
curl -fsSL https://claude.ai/install.sh | bash   # Mac/Linux
irm https://claude.ai/install.ps1 | iex            # Windows
```

<!--
Hier sind die Links zum Weiterlesen. Das MCP Use Cases Handout habt ihr schon.

Claude Code Installation ist ein Einzeiler. Morgen könnt ihr loslegen.
-->

---
layout: center
---

# Q&A + Diskussion

### Offene Fragen?

- Wo seht ihr Hürden in eurem Alltag?
- Wie sieht euer AI-First Workflow morgen aus?
- Was nehmt ihr mit?

<!--
Jetzt seid ihr dran. Offene Fragen, Bedenken, Ideen.

Mich interessiert besonders: Wo seht ihr Hürden? Was hindert euch daran, das morgen einzusetzen? Und was nehmt ihr als Erstes mit?
-->

---
layout: center
---

# Danke! 🚀

<br>

Ich pflanze den Samen — den Garten legt ihr an.

<br>

**Lukas Haas** · Sherlock GmbH

<!--
Danke fürs Mitmachen. Ihr wisst jetzt mehr als 95% der Firmen die "AI machen".

Der Rest liegt bei euch. Fangen klein an, iteriert, seid neugierig. Und prüft alles was die AI euch gibt.

Wenn ihr Fragen habt — ihr wisst wo ihr mich findet.
-->
