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
| 🛠️ Claude Code | 09:30–10:15 | Hands-On: Das Tool kennenlernen |
| ☕ Pause | 10:15–10:30 | |
| 🔄 AI-First Lifecycle | 10:30–11:15 | Req → Spec → Code → Test → Deploy → Ops |
| 🏋️ Exercises | 11:15–11:55 | Bug Fix, Security, DevOps |
| 💬 Wrap-Up | 11:55–12:15 | Showcase + Q&A |

<!--
Das ist unser Plan für die nächsten 3 Stunden.

Zuerst: Warum scheitern fast alle mit AI? Dann lernt ihr Claude Code kennen — hands-on, im echten Repo. Nach der Pause gehen wir den kompletten Lifecycle durch, Phase für Phase mit Demo. Und dann fixxt ihr selber Bugs und Security Issues.

Wenn Teil 2 länger dauert, kürze ich bei Teil 3. Wichtiger ist, dass ihr das Tool versteht.
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

Ilya Sutskever — einer der OpenAI-Gründer — hat 2022 getweetet, die Modelle könnten "leicht bewusst" sein. Massive Kontroverse, aber es zeigt: selbst die Macher staunen über ihre eigenen Systeme.

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

# Wo lernen?

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### github.com/anthropics
- Beispiele für CLAUDE.md, Skills, Plugins
- Open-Source Repos mit Best Practices
- Claude Code selbst ist Open Source

</div>
<div>

### Boris Cherny (@bcherny)
- Creator von Claude Code
- Teilt öffentlich wie Anthropic Claude Code nutzt
- Praxis-Tipps direkt vom Macher

</div>
</div>

<br>

> **Tipp:** Schaut euch an wie Anthropic selbst ihre Repos strukturiert — das sind die besten Vorlagen.

<!--
Zwei Quellen die ich euch mitgeben will:

Erstens: github.com/anthropics — Anthropics eigene Repos. Da findet ihr echte Beispiele für CLAUDE.md Dateien, Skills, Plugins. Claude Code selbst ist Open Source. Schaut euch an wie die Macher ihre eigenen Tools strukturieren — das sind die besten Vorlagen.

Zweitens: Boris Cherny auf X — @bcherny. Er ist der Creator von Claude Code und teilt regelmässig wie sie intern damit arbeiten. Sehr praxisnah, keine Marketing-Slides. Folgt dem wenn ihr am Ball bleiben wollt.
-->

---
layout: center
---

# Teil 2: Claude Code kennenlernen

### Konzepte und Grundlagen

<!--
Jetzt lernt ihr das Tool kennen. Nicht zuschauen — selber machen. Öffnet euer Terminal, geht ins Kalkulationstool-Repo.

Wir gehen Schritt für Schritt durch: Was ist Claude Code, wie bedient man es, was sind die wichtigsten Konzepte.
-->

---

# Copilot vs. Agent

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### 🤖 Copilot
- Code-Vervollständigung im Editor
- Reagiert auf aktuelle Zeile/Datei
- Eingebettet in IDE, Office, Teams
- GitHub Copilot, M365 Copilot

</div>
<div>

### 🧠 Agent
- Autonome, mehrstufige Tasks
- Liest, plant, implementiert, testet
- Arbeitet über Dateigrenzen hinweg
- Claude Code, Copilot Agent Mode

</div>
</div>

<br>

> Selbst Microsoft geht von Copilot → Agents: **"Copilot Cowork"** (März 2026) bettet Agents direkt in M365 ein.

<!--
Kurz der Unterschied, weil das oft verwechselt wird.

Copilot: ihr tippt, es vervollständigt. Gut für Boilerplate, Autocomplete, schnelle Snippets. Das kennt ihr von GitHub Copilot. Oder M365 Copilot — der hilft euch in Word, Excel, Teams. Immer eingebettet, immer reaktiv.

Agent: ihr gebt eine Aufgabe, der Agent erledigt sie. Er liest den Code, versteht den Kontext, plant eine Lösung, implementiert sie, testet sie. Claude Code ist so ein Agent.

Fun Fact: Selbst Microsoft bewegt sich in Richtung Agents. Anfang März haben sie "Copilot Cowork" angekündigt — Wave 3 von M365 Copilot. Agents die autonom in euren Business-Workflows arbeiten, nicht nur assistieren. Die sagen selber: der nächste Schritt nach Copilot sind Agents.

Beides hat seinen Platz. Aber der grosse Hebel — die 10x Produktivitätssteigerung — kommt von Agents. Nicht von schnellerem Autocomplete.
-->

---

# Claude Code Cheatsheet

<div class="grid grid-cols-2 gap-6 mt-4">
<div>

### Navigation
| Befehl | Funktion |
|--------|----------|
| `claude` | Starten |
| `Ctrl+C` | Abbrechen |
| `Ctrl+D` | Beenden |
| `/help` | Hilfe |
| `/clear` | Context leeren |
| `/compact` | Context komprimieren |

</div>
<div>

### Arbeiten
| Befehl | Funktion |
|--------|----------|
| `/plan` | Plan-Modus |
| `Shift+Tab` | Multi-line Input |
| `@file.ts` | Datei referenzieren |
| `#pattern` | Dateien suchen |
| Bild einfügen | Screenshot/Mockup |

</div>
</div>

<br>

> **Kurzreferenz:** [output/referenz-claude-code.md](https://github.com/Sherlock-GmbH/garaio-workshop/blob/main/output/referenz-claude-code.md) — **Jetzt ausprobieren:** `/help` eingeben

<!--
Das sind die wichtigsten Befehle. Geht die jetzt durch — tippt /help ein, schaut euch die Ausgabe an. Dann /compact um den Context zu komprimieren.

Shift+Tab ist wichtig für mehrzeilige Eingaben. @-Mention um Dateien direkt in den Prompt zu ziehen. Und ihr könnt Screenshots einfügen — Claude versteht Bilder.

Probiert 2-3 Befehle aus. Ihr habt 3 Minuten.
-->

---

# Was ist Context?

<div class="mt-8">

### Claude sieht bei jeder Nachricht:

<v-clicks>

1. **CLAUDE.md** — Projekt-Kontext, Architektur, Konventionen (immer geladen)
2. **Conversation** — Alles was ihr bisher geschrieben habt
3. **Tool Results** — Dateien die Claude gelesen hat, Befehle die es ausgeführt hat
4. **@ Mentions** — Dateien die ihr explizit referenziert

</v-clicks>

</div>

<br>

> Context Window ≈ 200K Tokens. Wenn voll → `/compact`

<!--
Wichtiges Konzept: Context. Was "sieht" Claude eigentlich?

CLAUDE.md wird immer geladen — darum muss sie kurz und präzise sein. Dann die Conversation — alles was ihr bisher gesagt habt. Dann Tool Results — wenn Claude eine Datei liest oder einen Befehl ausführt, landet das im Context. Und @-Mentions — Dateien die ihr direkt reingezogen habt.

Das Context Window ist begrenzt — ca. 200K Tokens. Wenn es voll wird, merkt ihr das daran dass Claude vergesslich wird. Dann /compact um zusammenzufassen und Platz zu schaffen.

Darum: CLAUDE.md kurz halten. Nicht jede Datei referenzieren. Gezielt arbeiten.
-->

---

# Permissions & Trust

<div class="mt-8">

### Claude fragt bevor es handelt:

<v-clicks>

- 📖 **Lesen** — immer erlaubt
- ✏️ **Schreiben** — fragt nach Bestätigung
- ⚡ **Bash Commands** — fragt nach Bestätigung
- ✅ **"Yes to all"** — Trust-Modus (Vorsicht!)

</v-clicks>

</div>

<br>

> **Tipp:** Akzeptiert einzeln, bis ihr euch sicher fühlt. Dann ggf. "Yes to all" für den Rest der Session.

<!--
Wichtig zu verstehen: Claude fragt euch bevor es Dateien ändert oder Befehle ausführt. Ihr seht genau was es tun will und könnt ablehnen.

Lesen ist immer erlaubt — Claude kann jede Datei im Repo lesen. Aber Schreiben und Bash Commands brauchen eure Bestätigung.

Es gibt einen "Yes to all" Modus — da akzeptiert Claude alles automatisch. Nutzt das erst wenn ihr euch sicher fühlt. Am Anfang lieber einzeln bestätigen, damit ihr seht was passiert.

Das ist Verification First in der Praxis: Ihr seid der Gatekeeper.
-->

---

# Slash Commands & Tools

<div class="grid grid-cols-2 gap-6 mt-8">
<div>

### Slash Commands
- `/plan` — Plan-Modus (kein Code)
- `/compact` — Context komprimieren
- `/clear` — Neuer Start
- `/help` — Übersicht
- `/review` — Code Review

</div>
<div>

### Was Claude kann
- Dateien lesen & schreiben
- Bash Commands ausführen
- Tests laufen lassen
- Git Operationen
- Bilder verstehen
- Web suchen (mit MCP)

</div>
</div>

<br>

> **Jetzt:** `/plan Erkläre mir die Ordnerstruktur dieses Projekts` — Plan-Modus = keine Änderungen

<!--
Slash Commands sind Shortcuts für häufige Aktionen. Der wichtigste: /plan. Im Plan-Modus analysiert Claude nur — es ändert keine Dateien. Perfekt zum Erkunden.

Probiert jetzt: "/plan Erkläre mir die Ordnerstruktur dieses Projekts". Claude wird die Struktur analysieren ohne etwas zu ändern.

Das ist der sichere Weg um ein Projekt kennenzulernen. Erst /plan, dann wenn ihr den Plan gut findet, lasst ihr Claude implementieren.
-->

---

# MCP — USB für AI

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Was ist MCP?
- **Model Context Protocol**
- Offener Standard
- Verbindet AI mit externen Tools
- Wie USB — Plug & Play

</div>
<div>

### Beispiele
- 🗄️ Datenbank abfragen
- 📋 DevOps Work Items lesen
- 💬 Slack durchsuchen
- 📊 Monitoring-Daten abrufen

</div>
</div>

<br>

```json
// .mcp.json im Projekt-Root
{ "mcpServers": { "supabase": { "command": "npx", "args": ["-y", "@supabase/mcp"] } } }
```

<!--
MCP — Model Context Protocol: Ein offener Standard der AI Agents mit externen Tools verbindet. Wie USB — einmal eingesteckt, funktioniert's.

Eine JSON-Datei im Repo-Root, und Claude hat plötzlich Zugriff auf eure Datenbank, eure Work Items, euer Monitoring.

Stellt euch vor: Bug Report kommt rein, Claude liest das Ticket aus Azure DevOps, schaut in die DB, findet den Bug im Code, schlägt einen Fix vor. Alles ohne Context-Switches.

Dazu gibt's ein Handout mit konkreten Use Cases. Heute nutzen wir Azure CLI als Brücke zu DevOps.
-->

---
layout: center
---

# ☕ Pause

### 15 Minuten

<!--
15 Minuten Pause.

Bitte prüft in der Pause:
- Claude Code läuft? (claude --version)
- Repo geklont?
- Azure CLI eingeloggt?

Falls ihr Fragen habt zu dem was wir bisher gemacht haben — jetzt ist ein guter Zeitpunkt.
-->

---
layout: center
---

# Teil 3: AI-First Lifecycle

### Requirements → Spec → Code → Test → Deploy → Ops

<!--
Jetzt wird's konkret. Wir gehen den kompletten Lifecycle durch — von der Anforderung bis zum laufenden System. An jedem Schritt: wo arbeitet der Agent, wo der Mensch. Pro Phase eine kurze Demo.
-->

---

# Requirements

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Mensch
- Stakeholder-Gespräche
- Business-Ziel definieren
- Priorisierung

</div>
<div>

### Agent
- Bestehenden Code analysieren
- Impact Assessment
- Fragen generieren die ihr vergessen habt

</div>
</div>

<br>

**Demo:**
```
Lies Bug #191 in todo.md. Welche Fragen müsste ich dem
Product Owner stellen, bevor ich das fixe?
```

<!--
Requirements: Der Mensch definiert WAS und WARUM. Der Agent hilft beim Analysieren.

(DEMO: Claude liest den Bug, analysiert den Code, generiert Rückfragen)

Seht ihr — Claude stellt Fragen die ihr vielleicht nicht gestellt hättet. "Welche Zeitzonen sind relevant?" "Gibt es andere Stellen mit dem gleichen Pattern?" Das ist der Mehrwert: die AI denkt an Edge Cases.

Aber die Entscheidung welche Requirements wichtig sind — das bleibt beim Menschen.
-->

---

# Spec

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Mensch
- Approach entscheiden
- Risiken bewerten
- Scope definieren

</div>
<div>

### Agent
- Spec schreiben (Explore → Plan)
- Betroffene Dateien identifizieren
- Alternativen vorschlagen

</div>
</div>

<br>

**Demo:**
```
/plan Schreib eine Spec für den Fix von Bug #191.
Max 5 Punkte. Identifiziere betroffene Dateien.
```

<!--
Spec: Der Agent schreibt einen Plan, der Mensch entscheidet ob er stimmt.

(DEMO: /plan Modus — Claude analysiert und schreibt eine Spec)

Wichtig: /plan Modus. Claude ändert nichts, es plant nur. Ihr seht den Plan, prüft ihn, und DANN gebt ihr grünes Licht.

Das ist Explore → Plan in der Praxis. Nie direkt loscodieren.
-->

---

# Code

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Mensch
- Plan reviewen und freigeben
- Diffs prüfen
- Jede Änderung verstehen

</div>
<div>

### Agent
- Implementieren nach Spec
- Tests zuerst schreiben
- Refactoring vorschlagen

</div>
</div>

<br>

**Demo:**
```
Implementiere den Fix nach der Spec.
Schreib zuerst einen Unit Test der das Problem reproduziert.
```

<!--
Code: Jetzt wird implementiert. Aber — Test zuerst.

(DEMO: Claude schreibt erst den Test, dann den Fix)

Achtet darauf was Claude macht: Es schreibt erst einen Test der fehlschlägt, dann den Fix der den Test grün macht. Das ist TDD — und die AI macht es automatisch wenn ihr es so promptet.

Und ihr seht jeden Diff. Akzeptiert nicht blind. Lest den Code. Verification First.
-->

---

# Test

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Mensch
- Test-Strategie definieren
- Edge Cases identifizieren
- Akzeptanzkriterien prüfen

</div>
<div>

### Agent
- Unit Tests schreiben
- Integration Tests
- Edge Cases abdecken
- Tests ausführen und Fehler fixen

</div>
</div>

<br>

**Demo:**
```
Führe die Tests aus. Wenn einer fehlschlägt, analysiere warum
und fixe es.
```

<br>

> **Frontend-Testing:** [agent-browser.dev](https://agent-browser.dev/) — Agent steuert den Browser, testet UI visuell

<!--
Test: Die AI ist extrem gut darin Tests zu schreiben und auszuführen. Aber IHR definiert was getestet werden soll.

(DEMO: Tests laufen lassen, ggf. Fehler fixen)

Der Agent kann den Red-Green-Refactor Cycle komplett alleine durchlaufen. Aber die Frage "testen wir das Richtige?" — das ist euer Job.

Für Frontend gibt's spannende Entwicklungen: agent-browser.dev — ein Tool das dem Agent einen echten Browser gibt. Der Agent kann die UI visuell testen, Screenshots machen, Buttons klicken. Nicht nur Unit Tests, sondern echtes E2E-Testing gesteuert vom Agent.
-->

---

# Deploy & Ops

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### Deploy
- PR erstellen mit Summary
- CI/CD Pipeline analysieren
- Deployment-Risiken bewerten

</div>
<div>

### Ops
- Logs analysieren
- Incidents debuggen
- Monitoring-Queries schreiben
- Post-Mortems unterstützen

</div>
</div>

<br>

> **Tools:** CLI-Tools (az cli, gh, kubectl) + DevOps MCP Server + Hooks für Automatisierung

<!--
Deploy und Ops: Hier kommt alles zusammen.

Deploy: Claude kann PRs erstellen, CI/CD Pipelines analysieren, Deployment-Risiken bewerten. Dafür nutzt ihr CLI-Tools wie az cli oder gh — Claude kann die direkt aufrufen. Oder einen DevOps MCP Server der das nativ integriert.

Ops: Logs analysieren, Incidents debuggen, Monitoring-Queries schreiben. Mit dem richtigen MCP-Server kann Claude direkt in Grafana oder Datadog schauen.

Und dann Hooks: Ihr könnt deterministische Schritte automatisieren. Z.B. nach jedem Commit automatisch Linting laufen lassen. Oder nach jedem PR automatisch einen Security-Check triggern. Hooks sind der Klebstoff zwischen Agent und eurer Pipeline.
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

Ihr habt heute die Mitte kennengelernt — Code verstehen, Fix implementieren, Tests schreiben. Die äusseren Schichten kommen mit MCP-Servern dazu.

Jetzt wendet ihr das Gelernte an.
-->

---
layout: center
---

# Teil 4: Exercises

### Echte Bugs. Echtes Repo. Echte Security Issues.

<!--
Jetzt wird's ernst. Ihr arbeitet mit dem echten Kalkulationstool-Repo. Echte Bugs, echte Security Issues — keine Spielzeug-Beispiele.

Nutzt den Explore-Plan-Code Workflow den ihr gerade gesehen habt.
-->

---

# Setup & Init (5 min)

```bash
cd Kalkulationstool
claude
```

Im Claude-Prompt:
```
/init
```

✅ Claude erstellt eine CLAUDE.md für das Projekt

<br>

Dann:
```
Was ist dieses Projekt? Gib mir einen kurzen Überblick.
```

✅ Claude sollte die neue CLAUDE.md lesen und die Architektur erklären

<!--
Erster Schritt: Stellt sicher dass alles läuft.

Öffnet das Terminal im Kalkulationstool-Ordner. Startet Claude Code.

Dann: /init — das ist der Befehl der eine CLAUDE.md erstellt. Claude analysiert euer Repo und generiert automatisch den Projekt-Kontext. Schaut euch an was rauskommt.

Danach fragt: "Was ist dieses Projekt?" Claude sollte die neue CLAUDE.md nutzen und euch die Architektur erklären: .NET 8, Angular 19, CQRS, Azure.

Wer Probleme hat: Hand hoch, wir helfen.
-->

---

# Exercise 1: Bug #191 fixen (20 min)

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

# Exercise 2: Security Issue (15 min)

### Fehlende `[Authorize]` Attribute 🔒

1. **Audit lesen:** `Lies security-audit-report.md, Fokus auf Vulnerability #2`
2. **Code finden:** `Welche Endpoints haben kein [Authorize]?`
3. **Fix:** `Füge die fehlenden Attribute hinzu`
4. **Review:** `Gibt es noch andere Stellen mit ähnlichen Problemen?`

<br>

> **Takeaway:** AI findet Issues schnell — aber **du verifizierst**.

<!--
Exercise 2: Security. Im Repo liegt ein Security Audit Report mit 4 Findings. Ihr fokussiert auf Vulnerability 2: fehlende Authorize-Attribute.

Lasst Claude den Report lesen, den Code finden, und den Fix implementieren. Aber — und das ist der Punkt — IHR prüft ob der Fix korrekt ist. Nicht blind akzeptieren.

Security Reviews sind ein perfekter AI Use Case. Die AI findet Muster schneller als ihr. Aber die Entscheidung ob ein Fix korrekt und ausreichend ist, bleibt bei euch.
-->

---

# Exercise 3: Azure CLI — Work Items (10 min)

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
Exercise 3: Wir nutzen Claude als DevOps-Brücke. In todo.md stehen Azure CLI Befehle für Azure DevOps Work Items.

Lasst Claude die Befehle nutzen, einen Bug-Report erstellen, und den Fix aus Exercise 1 mit dem Work Item verknüpfen.

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

1. **Verification First** — AI macht Fehler. Prüfen, prüfen, prüfen
2. **Context Engineering** — CLAUDE.md ist euer Freund
3. **Explore → Plan → Code** — Nicht direkt loscodieren
4. **Agent > Copilot** — Der Hebel liegt bei autonomen Tasks
5. **Geschlossener Loop** — Issue → Code → Test → Deploy aus einer Oberfläche

</v-clicks>

<!--
(Click durch die Punkte)

Fünf Dinge zum Mitnehmen.

Verification First — das Wichtigste. Context Engineering — CLAUDE.md gut pflegen. Explore Plan Code — nie direkt loscodieren. Agents statt Autocomplete. Und die Vision: ein geschlossener Loop.

1-3 könnt ihr morgen sofort einsetzen. Der Rest kommt mit der Zeit.
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
