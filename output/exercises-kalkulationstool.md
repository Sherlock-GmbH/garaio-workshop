# Hands-On Exercises: Kalkulationstool

Diese Exercises nutzen das echte GARAIO Demo-Repo mit realen Bugs und Issues.

---

## Setup Check (5 min)
**10:45–10:50**

### Checkliste
- [ ] Claude Code läuft (`claude --version`)
- [ ] Repo geklont und im Terminal geöffnet
- [ ] Im Repo-Root: `claude` starten

### Quick Test
```bash
cd Kalkulationstool
claude
```

Im Claude prompt:
```
Was ist dieses Projekt? Gib mir einen kurzen Überblick.
```

Claude sollte CLAUDE.md lesen und die Architektur erklären (.NET 8 + Angular 19, CQRS, Azure).

---

## Exercise 1: Context Engineering verstehen (10 min)
**10:50–11:00**

### Ziel
Verstehen, wie CLAUDE.md funktioniert und warum Context Engineering wichtig ist.

### Aufgabe

1. **CLAUDE.md öffnen und lesen** (2 min)
   ```
   Zeig mir den Inhalt von CLAUDE.md
   ```

2. **Architektur-Fragen stellen** (5 min)
   ```
   Erkläre mir das CQRS Pattern in diesem Projekt. 
   Wo liegen Commands, wo Queries?
   ```

   ```
   Wie funktioniert die Authentifizierung? 
   Was ist x-ms-client-principal?
   ```

3. **Reflexion** (3 min)
   - Was hat Claude aus CLAUDE.md gelernt?
   - Welche Infos fehlen, die hilfreich wären?

### Takeaway
> **CLAUDE.md < 100 Zeilen** — concise & ruthless. 
> Garbage in, garbage out.

---

## Exercise 2: Bug #191 fixen — Explore → Plan → Code (20 min)
**11:00–11:20**

### Der Bug
Bei Umwandlung Offerte → Vertrag fällt das **Auftragsbeginn-Datum um 1 Tag zurück**. 
Vermutlich UTC/Timezone Off-by-One.

### Phase 1: Explore (5 min)

```
Lies todo.md und erkläre mir Bug #191.
```

```
Wo im Code wird ein Vertrag aus einer Offerte erstellt? 
Such nach "Vertrag erstellen" oder "Contract" Logik.
```

```
Zeig mir alle Stellen, wo Datums-Konvertierungen stattfinden. 
Besonders interessant: UTC, ToLocalTime, DateTime vs DateTimeOffset.
```

### Phase 2: Plan (5 min)

```
Basierend auf deiner Analyse: 
Was ist die wahrscheinliche Ursache für Bug #191?
Schreib eine kurze Spec (3-5 Punkte) wie wir das fixen.
```

Erwartete Erkenntnisse:
- Frontend sendet lokale Zeit
- Backend speichert als UTC
- Bei der Rückgabe wird nicht korrekt konvertiert
- Oder: JavaScript Date Objekt vs .NET DateTime Serialisierung

### Phase 3: Code (10 min)

```
Implementiere den Fix für Bug #191 basierend auf deinem Plan.
Erkläre jeden Schritt.
```

**Verification First!**
```
Schreib einen Unit Test, der das korrekte Datum-Verhalten verifiziert.
```

### Takeaway
> **Explore → Plan → Code** — nicht direkt loscodieren.
> **Verification First** — Tests VOR dem Merge.

---

## Exercise 3: Security Issue fixen (15 min)
**11:20–11:35**

### Das Problem
Im Security Audit wurden fehlende `[Authorize]` Attribute gefunden.

### Aufgabe

1. **Security Audit lesen** (3 min)
   ```
   Lies security-audit-report.md und fasse die Findings zusammen.
   Fokus auf Vulnerability #2 (Missing Authorize).
   ```

2. **Code finden** (3 min)
   ```
   Zeig mir UserController.cs. 
   Welche Endpoints haben kein [Authorize] Attribut?
   ```

3. **Fix implementieren** (5 min)
   ```
   Füge die fehlenden [Authorize] Attribute hinzu.
   Die Debug-Endpoints (echo/*) sollen nur im Development verfügbar sein.
   ```

4. **Review** (4 min)
   ```
   Erkläre mir, warum diese Änderungen die Sicherheit verbessern.
   Gibt es noch andere Stellen im Code, die ähnliche Probleme haben könnten?
   ```

### Takeaway
> AI findet Issues schnell — aber **du verifizierst**.
> Security Reviews sind ein perfekter AI Use Case.

---

## Showcase (10 min)
**11:45–11:55** *(oder früher, je nach Fortschritt)*

### Format
2-3 Teilnehmer zeigen ihre Lösung (3 min pro Person):

1. **Was war der Approach?**
   - Welche Fragen hast du Claude gestellt?
   - Wie war der Explore → Plan → Code Flow?

2. **Was hat funktioniert?**
   - Wo war Claude besonders hilfreich?

3. **Was nicht?**
   - Wo musstest du korrigieren?
   - Was hat Claude falsch verstanden?

### Diskussionsfragen
- Wie unterscheidet sich das von "klassischem" Debugging?
- Wo seht ihr den grössten Produktivitätsgewinn?
- Was braucht noch Übung?

---

## Exercise 4: Azure CLI — Work Items abfragen (10 min)
**11:35–11:45** *(alternativ zu Showcase, je nach Zeitbudget)*

### Ziel
Claude Code als DevOps-Assistent nutzen: Azure DevOps Work Items direkt aus dem Terminal abfragen und analysieren.

### Vorbereitung
```bash
# Azure CLI muss installiert und eingeloggt sein
az login
az extension add --name azure-devops
```

### Aufgabe

1. **Offene Work Items auflisten** (3 min)
   ```
   Nutze die Azure CLI, um alle offenen Work Items im Kalkulationstool-Projekt aufzulisten.
   Die Commands findest du in todo.md. Organisation: garaio-allpura, Projekt: Kalkulationstool.
   ```

   Claude sollte die `az boards query` Befehle aus `todo.md` nutzen.

2. **Bug-Report erstellen** (4 min)
   ```
   Erstelle mir einen Report aller offenen Bugs:
   - Titel, Severity, wem zugewiesen
   - Wie lange offen (seit Erstelldatum)
   - Empfehlung zur Priorisierung
   ```

   ```
   Welche Work Items sind unassigned? 
   Erstelle eine Übersicht mit Vorschlägen zur Zuweisung.
   ```

3. **Cross-Reference: Code ↔ Issues** (3 min)
   ```
   Nimm Bug #191 aus den Work Items.
   Finde den zugehörigen Code und erkläre, 
   ob unser Fix aus Exercise 2 das Problem löst.
   ```

### Takeaway
> **AI als DevOps-Brücke**: Claude kann Work Items abfragen, mit Code verknüpfen, und Reports generieren — alles aus einer Oberfläche.
> Keine Context-Switches zwischen Browser, Terminal und IDE mehr.

---

## Exercise 5: MCP — Azure DevOps als Tool anbinden (15 min)
**Demo oder Hands-On, je nach Setup**

### Ziel
Verstehen, was MCP (Model Context Protocol) ist und wie es Claude Code zu einem vollwertigen DevOps-Agenten macht.

### Was ist MCP?
MCP ist ein offener Standard, der AI-Assistenten mit externen Datenquellen und Tools verbindet — wie USB für AI. Statt Claude manuell Befehle einzutippen, bekommt Claude **direkte Tool-Zugriffe**.

### Setup: Azure DevOps MCP Server

Der offizielle **Microsoft Azure DevOps MCP Server** verbindet Claude Code direkt mit Azure DevOps:

```json
// .mcp.json im Projekt-Root
{
  "mcpServers": {
    "azure-devops": {
      "command": "npx",
      "args": ["-y", "@azure-devops/mcp", "garaio-allpura"]
    }
  }
}
```

```bash
# Voraussetzung: Node.js 20+, az login
npm install -g @azure-devops/mcp  # oder via npx (siehe oben)
```

### Was kann der Azure DevOps MCP?

| Tool | Beschreibung |
|------|-------------|
| Work Items | Abfragen, erstellen, aktualisieren |
| Pull Requests | Auflisten, Reviews, Kommentare |
| Pipelines | Build-Status, Runs triggern |
| Repos | Code durchsuchen, Branches |
| Test Plans | Test Cases, Test Runs |
| Wiki | Dokumentation lesen und bearbeiten |

### Demo-Aufgaben

1. **Natürliche Sprache statt CLI** (3 min)
   ```
   Zeig mir alle offenen Bugs im aktuellen Sprint.
   ```
   
   → Claude nutzt automatisch das MCP Work Items Tool (kein `az boards query` nötig!)

2. **Sprint-Analyse** (5 min)
   ```
   Analysiere den aktuellen Sprint:
   - Wie viele Items sind offen vs. abgeschlossen?
   - Welche Items sind at risk?
   - Wann wurde zuletzt deployed?
   ```

3. **Pipeline + Code verknüpfen** (5 min)
   ```
   Check den Status der CI Pipeline.
   Wenn der letzte Build fehlgeschlagen ist — 
   finde die Ursache im Code.
   ```

4. **Work Item erstellen** (2 min)
   ```
   Erstelle ein neues Bug Work Item:
   Titel: "Security: Fehlende [Authorize] Attribute auf Debug-Endpoints"
   Basierend auf unserem Fix aus Exercise 3.
   ```

### Vergleich: CLI vs MCP

| | Azure CLI | MCP |
|---|-----------|-----|
| **Setup** | `az login` + Extension | `.mcp.json` + npx |
| **Nutzung** | Claude generiert CLI-Befehle | Claude ruft Tools direkt auf |
| **Flexibilität** | Alles möglich (WIQL, etc.) | Vordefinierte Tools |
| **Vorteil** | Kein Setup nötig, überall verfügbar | Natürlicher, weniger Fehler, kein Copy-Paste |
| **Ideal für** | Ad-hoc Abfragen, Scripting | Tägliche Arbeit, Integration |

### Takeaway
> **MCP = USB für AI** — einmal eingesteckt, funktioniert es einfach.
> Azure DevOps MCP macht Claude zum vollwertigen Projektmanagement-Assistenten.
> In Kombination mit Code-Zugriff entsteht ein **geschlossener Loop**: Issue → Code → Test → Deploy.

---

## Bonus: Für Schnelle

### Option A: Privilege Escalation fixen (Vuln #1)
```
Analysiere Vulnerability #1 aus dem Security Audit (Privilege Escalation).
Wie würdest du das fixen? Implementiere eine Lösung.
```

### Option B: Projekt-Dokumentation verbessern
```
Die Wiki-Doku ist veraltet (nennt .NET 7 statt 8).
Generiere eine aktualisierte Technical Specifications Seite 
basierend auf dem aktuellen Code.
```

### Option C: Fehlende Tests schreiben
```
Schau dir die Test-Coverage an.
Welche kritischen Pfade haben keine Tests?
Schreib Tests für einen davon.
```

---

## Notizen für Moderator

### Timing-Optionen (60 min Hands-On)
Die 5 Exercises + Showcase passen nicht alle in 60 min. Empfohlene Kombinationen:

**Option A — Coding-Fokus (Standard):**
- Ex 1 (10) + Ex 2 (20) + Ex 3 (15) + Showcase (10) = 55 min ✅

**Option B — DevOps-Fokus:**
- Ex 1 (10) + Ex 2 (20) + Ex 4 (10) + Ex 5 Demo (10) + Showcase (10) = 60 min ✅

**Option C — Alles anteasen (straff):**
- Ex 1 (5) + Ex 2 (15) + Ex 3 (10) + Ex 4 (10) + Ex 5 Demo (5) + Showcase (10) = 55 min

### Exercise 4 & 5 — Voraussetzungen
- **Ex 4 (Azure CLI):** Teilnehmer brauchen `az login` + DevOps-Extension. Falls nicht möglich → als Live-Demo durch Moderator
- **Ex 5 (MCP):** Am besten als **Moderator-Demo** — MCP Setup braucht Vorbereitung. Teilnehmer sehen den Effekt, ohne selbst konfigurieren zu müssen
- **Fallback:** Wenn weder Azure CLI noch MCP verfügbar: die Befehle aus `todo.md` zeigen und erklären, wie Claude sie nutzt

### Häufige Probleme
- **Claude findet CLAUDE.md nicht**: Working Directory prüfen, muss in `Kalkulationstool/` sein
- **API läuft nicht**: Für Exercises nicht nötig, ist reines Code-Reading
- **Teilnehmer stuck**: Beispiel-Prompts vorzeigen, Pair Programming
- **`az boards` schlägt fehl**: Org/Projekt als Default setzen: `az devops configure --defaults organization=https://dev.azure.com/garaio-allpura project=Kalkulationstool`
- **MCP startet nicht**: Node.js 20+ prüfen, `npx` muss verfügbar sein

### Key Messages wiederholen
1. **Explore → Plan → Code** (nicht direkt implementieren)
2. **Verification First** (AI macht Fehler)
3. **Context Engineering** (CLAUDE.md ist dein Freund)
4. **MCP = USB für AI** (einmal eingesteckt, einfach nutzen)
5. **Geschlossener Loop**: Issue → Code → Test → Deploy — alles aus einer Oberfläche
