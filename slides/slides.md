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
| 🧠 Intro | 08:30–09:00 | Warum 95% scheitern |
| 🛠️ Claude Code | 09:00–10:00 | Hands-On: Das Tool kennenlernen |
| ☕ Pause | 10:00–10:30 | |
| 🔄 Lifecycle Hands-On | 10:30–11:30 | Req → Spec → Code → Test → Deploy → Ops |
| 💬 Wrap-Up | 11:30–12:00 | Feedback + Q&A |

<!--
Das ist unser Plan für die nächsten 3 Stunden.

Zuerst: Warum scheitern fast alle mit AI? Dann lernt ihr Claude Code kennen — hands-on. Nach der Pause gehen wir den kompletten Lifecycle durch — und ihr macht bei jeder Phase sofort mit. Kein Zuschauen und dann nochmal machen, sondern: erklären, dann direkt coden.

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

- 2024: **Scaling Laws** galten als der Weg — dann kam die "Scaling Wall"-Debatte
- 2024-25: **Reasoning-Modelle** (o1/o3, Extended Thinking) — vorher nicht auf der Roadmap
- 2025-26: **Agentic Workflows**, Computer Use, MCP — vor 2 Jahren kannte niemand diese Patterns
- Alle ~6 Monate ein neues Paradigma

</v-clicks>

<br>

> Wenn sich alle 6 Monate das Paradigma ändert — wer verkauft euch eine 3-Jahres-Roadmap?

<!--
Warum kann euch niemand sagen "so macht man AI richtig"?

Schaut euch die letzten 18 Monate an: Erst hiess es, grössere Modelle lösen alles — Scaling Laws. Dann kam die Debatte ob Skalierung an Grenzen stösst. Plötzlich kamen Reasoning-Modelle wie o1 — die hatte fast niemand auf dem Radar. Und jetzt reden wir über Agents, Computer Use, MCP — Patterns die vor zwei Jahren nicht existierten.

Alle paar Monate ändert sich das Spielfeld fundamental. Jede Firma die euch eine "fertige Enterprise AI Transformation Roadmap" verkauft, lügt. Ihr müsst euren eigenen Weg finden. Ich kann heute einen Samen pflanzen — den Garten müsst ihr selbst anlegen.
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

# Teil 3: AI-First Lifecycle — Hands-On

### Requirements → Spec → Code → Test → Deploy → Ops

### Echte Bugs. Echtes Repo. Echte Security Issues.

<!--
Jetzt wird's konkret UND praktisch. Wir gehen den kompletten Lifecycle durch — und ihr macht bei jeder Phase sofort mit. Kein Zuschauen, dann nochmal machen. Sondern: kurz erklären, dann direkt hands-on.

Öffnet euer Terminal, geht ins Kalkulationstool-Repo.
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

# Phase 1: Requirements (10 min)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### Mensch
- Business-Ziel definieren
- Priorisierung

### Agent
- Code analysieren
- Fragen generieren die ihr vergessen habt

</div>
<div>

### Hands-On: Bug #191 verstehen
```
Lies @todo.md und erkläre mir Bug #191.
```

```
Wo wird ein Vertrag aus einer Offerte
erstellt?
```

```
Welche Fragen müsste ich dem Product
Owner stellen, bevor ich das fixe?
```

</div>
</div>

<!--
Requirements: Der Mensch definiert WAS und WARUM. Der Agent hilft beim Analysieren.

Macht jetzt mit: Lest den Bug, lasst Claude den Code analysieren. Seht wie Claude Fragen generiert die ihr vielleicht nicht gestellt hättet. "Welche Zeitzonen sind relevant?" "Gibt es andere Stellen mit dem gleichen Pattern?"

Das ist der Mehrwert: die AI denkt an Edge Cases. Aber die Entscheidung welche Requirements wichtig sind — das bleibt beim Menschen.
-->

---

# Phase 2: Spec (10 min)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### Mensch
- Approach entscheiden
- Risiken bewerten
- Scope definieren

### Agent
- Spec schreiben (Explore → Plan)
- Betroffene Dateien identifizieren
- Alternativen vorschlagen

</div>
<div>

### Hands-On: Plan erstellen
```
/plan Schreib eine Spec für den Fix
von Bug #191. Max 5 Punkte.
Identifiziere betroffene Dateien.
```

<br>

**Prüft den Plan:**
- Stimmt die Ursache?
- Fehlen betroffene Dateien?
- Ist der Scope realistisch?

</div>
</div>

<!--
Spec: Der Agent schreibt einen Plan, der Mensch entscheidet ob er stimmt.

Wichtig: /plan Modus. Claude ändert nichts, es plant nur. Ihr seht den Plan, prüft ihn, und DANN gebt ihr grünes Licht.

Das ist Explore → Plan in der Praxis. Nie direkt loscodieren.
-->

---

# Phase 3: Code + Test (15 min)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### Mensch
- Diffs prüfen
- Jede Änderung verstehen

### Agent
- Tests zuerst schreiben
- Implementieren nach Spec
- Tests ausführen und Fehler fixen

</div>
<div>

### Hands-On: Fix implementieren
```
Implementiere den Fix nach dem Plan.
Schreib zuerst einen Unit Test der
das Problem reproduziert.
```

```
Führe die Tests aus. Wenn einer
fehlschlägt, analysiere warum.
```

</div>
</div>

<br>

> **Frontend-Testing:** [agent-browser.dev](https://agent-browser.dev/) — Agent steuert den Browser, testet UI visuell

<!--
Code und Test zusammen: erst der Test der fehlschlägt, dann der Fix der ihn grün macht. TDD — und die AI macht es automatisch wenn ihr es so promptet.

Achtet darauf: Ihr seht jeden Diff. Akzeptiert nicht blind. Lest den Code. Verification First.

Für Frontend gibt's agent-browser.dev — ein Tool das dem Agent einen echten Browser gibt. Screenshots, Buttons klicken, echtes E2E-Testing.
-->

---

# Querschnitt: Security (15 min)

### Fehlende `[Authorize]` Attribute 🔒

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### Mensch
- Fix korrekt? Ausreichend?
- Andere Stellen betroffen?

### Agent
- Audit lesen, Code finden
- Pattern-Matching über alle Files
- Fix implementieren

</div>
<div>

### Hands-On
```
/security-review
```

```
Mach dasselbe für die gesamte
Code-Base und speichere in
security-audit-report.md
```

</div>
</div>

<br>

> AI findet Issues schnell — aber **du verifizierst**.

<!--
Security ist ein Querschnitt der in jeder Lifecycle-Phase relevant ist. Hier seht ihr den Agent als Code-Auditor.

Lasst Claude den Report lesen, den Code finden, und den Fix implementieren. Aber — und das ist der Punkt — IHR prüft ob der Fix korrekt ist. Nicht blind akzeptieren.

Security Reviews sind ein perfekter AI Use Case. Die AI findet Muster schneller als ihr. Aber die Entscheidung ob ein Fix korrekt und ausreichend ist, bleibt bei euch.
-->

---

# Phase 4: Deploy & Ops (10 min)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

### Mensch
- Release-Entscheid treffen
- Incident-Priorität bestimmen
- Monitoring-Alerts bewerten

### Agent
- PRs erstellen, Pipelines analysieren
- Logs durchsuchen, Incidents debuggen
- Hooks für Automatisierung

</div>
<div>

### Hands-On: Azure CLI
```
Nutze die Azure CLI, um alle offenen
Bugs aufzulisten. Commands in @todo.md.
```

```
Erstelle einen Bug-Report: Titel,
Severity, wie lange offen.
```

```
Nimm Bug #191 — löst unser Fix
das Problem?
```

</div>
</div>

<br>

> **Tools:** CLI-Tools (az cli, gh, kubectl) + DevOps MCP Server + Hooks

<!--
Deploy und Ops: Hier kommt alles zusammen. Claude kann CLI-Tools wie az cli oder gh direkt aufrufen. Oder einen DevOps MCP Server der das nativ integriert.

Lasst Claude die Befehle nutzen, einen Bug-Report erstellen, und den Fix mit dem Work Item verknüpfen. Das zeigt den Mehrwert: Claude versteht sowohl den Code als auch die Issues — ohne Context-Switches.

Hooks automatisieren deterministische Schritte: nach jedem Commit Linting, nach jedem PR einen Security-Check. Hooks sind der Klebstoff zwischen Agent und Pipeline.
-->

---

# Der geschlossene Loop

```
📋 Issue lesen        (az CLI / DevOps MCP)
   ↓
🔍 Code verstehen     (Filesystem)
   ↓
🗄️ Daten prüfen       (DB MCP)
   ↓
💻 Fix implementieren  (Claude Code)
   ↓
✅ Tests schreiben     (Claude Code)
   ↓
🚀 PR erstellen        (az CLI / DevOps MCP)
   ↓
📊 Monitoring prüfen   (devTools MCP)
```

> **Das habt ihr gerade gemacht.** Issue → Explore → Plan → Code → Test → DevOps. Alles aus einer Oberfläche.

<!--
Das ist der geschlossene Loop — und ihr habt ihn gerade selbst durchlaufen. Vom Bug lesen über Code verstehen, Plan schreiben, Fix implementieren, Tests, bis zum Work Item in Azure DevOps.

Noch nicht komplett automatisiert — aber die Bausteine sind da. Mit MCP-Servern kommen die äusseren Schichten dazu.
-->

---
layout: center
---

# Feedback-Runde

- Was hat funktioniert, was nicht?
- Wo musstet ihr Claude korrigieren?
- Wo seht ihr den grössten Hebel für euren Alltag?
- Was war überraschend?

<!--
Offene Runde. Mich interessiert euer ehrliches Feedback — nicht nur was gut lief, sondern vor allem wo es gehakt hat. Wo musstet ihr Claude korrigieren? Was hat überraschend gut oder schlecht funktioniert?

Und die wichtigste Frage: Wo seht ihr den grössten Hebel für euren Alltag? Was nehmt ihr morgen mit?
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
- 📋 **Workshop-Repo:** github.com/Sherlock-GmbH/garaio-workshop

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

Wir haben heute die ersten Samen gepflanzt.
Jetzt gilt es, den Garten anzulegen und zu pflegen.

<br>

**Lukas Haas** · Sherlock GmbH

<!--
Danke fürs Mitmachen. Wir wissen jetzt mehr als 95% der Firmen die "AI machen".

Der Rest liegt bei uns allen. Klein anfangen, iterieren, neugierig bleiben. Und alles prüfen was die AI uns gibt.

-->
