# Hands-On Exercises: Kalkulationstool

Diese Exercises sind in den AI-First Lifecycle integriert. Pro Phase: kurz erklären, dann sofort hands-on.

---

## Setup & Init (5 min)
**10:30–10:35**

### Checkliste
- [ ] Claude Code läuft (`claude --version`)
- [ ] Repo geklont und im Terminal geöffnet
- [ ] Im Repo-Root: `claude` starten

### Aufgabe
```bash
cd Kalkulationstool
claude
```

Im Claude-Prompt:
```
/init
```

✅ Claude erstellt eine CLAUDE.md für das Projekt.

Dann:
```
Was ist dieses Projekt? Gib mir einen kurzen Überblick.
```

✅ Claude sollte die neue CLAUDE.md nutzen und die Architektur erklären (.NET 8 + Angular 19, CQRS, Azure).

---

## Phase 1: Requirements (10 min)
**10:35–10:45**

### Ziel
Bug #191 verstehen. Agent generiert Rückfragen die ihr vielleicht vergessen hättet.

### Aufgabe

1. **Bug lesen** (3 min)
   ```
   Lies @todo.md und erkläre mir Bug #191.
   ```

2. **Code finden** (4 min)
   ```
   Wo im Code wird ein Vertrag aus einer Offerte erstellt?
   Such nach "Vertrag erstellen" oder "Contract" Logik.
   ```

3. **Rückfragen generieren** (3 min)
   ```
   Welche Fragen müsste ich dem Product Owner stellen,
   bevor ich das fixe?
   ```

### Takeaway
> Agent denkt an Edge Cases. Aber die Entscheidung welche Requirements wichtig sind — das bleibt beim Menschen.

---

## Phase 2: Spec (10 min)
**10:45–10:55**

### Ziel
Plan erstellen lassen, prüfen, freigeben.

### Aufgabe

1. **Spec schreiben** (5 min)
   ```
   /plan Schreib eine Spec für den Fix von Bug #191.
   Max 5 Punkte. Identifiziere betroffene Dateien.
   ```

2. **Plan prüfen** (5 min)
   - Stimmt die Ursache?
   - Fehlen betroffene Dateien?
   - Ist der Scope realistisch?

Erwartete Erkenntnisse:
- Frontend sendet lokale Zeit
- Backend speichert als UTC
- Bei der Rückgabe wird nicht korrekt konvertiert
- Oder: JavaScript Date Objekt vs .NET DateTime Serialisierung

### Takeaway
> **Explore → Plan → Code** — nie direkt loscodieren. /plan Modus ändert nichts.

---

## Phase 3: Code + Test (15 min)
**10:55–11:10**

### Ziel
Fix implementieren. Test zuerst.

### Aufgabe

1. **Unit Test schreiben** (5 min)
   ```
   Schreib zuerst einen Unit Test der das Problem reproduziert.
   ```

2. **Fix implementieren** (5 min)
   ```
   Implementiere den Fix basierend auf dem Plan.
   Erkläre jeden Schritt.
   ```

3. **Tests ausführen** (5 min)
   ```
   Führe die Tests aus. Wenn einer fehlschlägt,
   analysiere warum und fixe es.
   ```

### Takeaway
> **Verification First** — Tests VOR dem Merge. Jeden Diff prüfen.

---

## Querschnitt: Security (10 min)
**11:10–11:20**

### Ziel
Agent als Security-Auditor. Fehlende `[Authorize]` Attribute finden und fixen.

### Aufgabe

1. **Security Review** (3 min)
   ```
   /security-review
   ```

2. **Codebase-weiter Audit** (3 min)
   ```
   Mach dasselbe für die gesamte Code-Base
   und speichere in security-audit-report.md
   ```

3. **Fix** (4 min)
   ```
   Welche Endpoints haben kein [Authorize]?
   Füge die fehlenden Attribute hinzu.
   ```

### Takeaway
> AI findet Issues schnell — aber **du verifizierst**.

---

## Phase 4: Deploy & Ops (10 min)
**11:20–11:30**

### Ziel
Claude als DevOps-Brücke: Azure DevOps Work Items abfragen und mit Code verknüpfen.

### Vorbereitung
```bash
# Azure CLI muss installiert und eingeloggt sein
az login
az extension add --name azure-devops
```

### Aufgabe

1. **Work Items auflisten** (3 min)
   ```
   Nutze die Azure CLI, um alle offenen Bugs aufzulisten.
   Commands findest du in @todo.md.
   ```

2. **Bug-Report erstellen** (4 min)
   ```
   Erstelle einen Bug-Report:
   Titel, Severity, wie lange offen, Priorisierung.
   ```

3. **Cross-Reference** (3 min)
   ```
   Nimm Bug #191 — löst unser Fix das Problem?
   ```

### Takeaway
> **Code ↔ Issues verknüpfen.** Keine Context-Switches zwischen Browser, Terminal und IDE.

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

### Timing
Die Phasen sind in den Lifecycle integriert (60 min total):
- Setup (5) + Req (10) + Spec (10) + Code+Test (15) + Security (10) + Deploy (10) = 60 min

Falls Zeit knapp: Security oder Deploy&Ops kürzen/weglassen.

### Voraussetzungen
- **Azure CLI:** Teilnehmer brauchen `az login` + DevOps-Extension. Falls nicht möglich → als Live-Demo durch Moderator
- **Fallback:** Befehle aus `todo.md` zeigen und erklären, wie Claude sie nutzt

### Häufige Probleme
- **Claude findet CLAUDE.md nicht**: `/init` ausführen, Working Directory prüfen, muss in `Kalkulationstool/` sein
- **API läuft nicht**: Für Exercises nicht nötig, ist reines Code-Reading
- **Teilnehmer stuck**: Beispiel-Prompts vorzeigen, Pair Programming
- **`az boards` schlägt fehl**: Org/Projekt als Default setzen: `az devops configure --defaults organization=https://dev.azure.com/garaio-allpura project=Kalkulationstool`
