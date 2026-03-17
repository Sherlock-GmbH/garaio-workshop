# Claude Code Workflow — Prompts für Devs, Tester & PMs

> Jeder Workflow-Schritt mit konkreten Prompt-Beispielen für alle Rollen.
> Grundprinzip: **Explore → Plan → Code → Verify**

---

## 1. 🔍 EXPLORE — Verstehen

**Ziel:** Problem/Codebase verstehen, bevor man etwas ändert.

### Für Devs
```
give me an overview of this codebase
```
```
explain the main architecture patterns used here
```
```
how is authentication handled in this project?
```
```
trace the login process from front-end to database
```
```
find the files that handle user authentication
```
```
what external dependencies does this project use and why?
```

### Für Tester / QA
```
what are the critical paths in this application that need testing?
```
```
which parts of the codebase have no test coverage?
```
```
find functions in NotificationsService that are not covered by tests
```
```
list all API endpoints and their expected input/output
```
```
where are the most complex functions that are likely to have bugs?
```

### Für PMs / Non-Devs
```
explain this project like I'm a product manager — what does it do, who uses it, what are the main features?
```
```
what's the current state of this feature? is it complete?
```
```
summarize all open TODOs and FIXMEs in the codebase
```
```
how long would it roughly take to add [feature X] based on the current architecture?
```

### 💡 Pro-Tipps
- **Plan Mode** aktivieren (`Shift+Tab` 2x) — Claude liest nur, ändert nichts
- Alternativ: `claude --permission-mode plan`
- Breite Fragen zuerst, dann gezielt tiefer gehen

---

## 2. 📋 PLAN — Spezifizieren

**Ziel:** Klaren Plan erstellen, bevor Code geschrieben wird.

### Für Devs
```
I need to add OAuth2 authentication. Create a detailed implementation plan — which files to change, in what order, and why.
```
```
plan the refactoring of utils.js to use ES2024 features. List each change and its impact.
```
```
what's the best approach to fix this bug? give me 2-3 options with trade-offs.
```
```
create a migration plan from REST to GraphQL for the user endpoints
```

### Für Tester / QA
```
create a test plan for the checkout flow — cover happy path, edge cases, and error scenarios
```
```
what test cases would you write for this function? include boundary values and error conditions
```
```
plan a regression test suite for the authentication module
```
```
analyze this PR diff and tell me what test scenarios I should verify manually
```

### Für PMs / Non-Devs
```
I want to add a notification system. Write a feature spec with requirements, acceptance criteria, and technical considerations.
```
```
create a PRD (Product Requirements Document) for [feature] based on what you see in the codebase
```
```
compare two implementation approaches for [feature] and recommend one with pros/cons
```
```
what are the risks and dependencies if we build [feature X]?
```

### 💡 Pro-Tipps
- `Ctrl+G` öffnet den Plan im Editor — direkt editierbar!
- Plan Mode = iterativ: "What about backward compatibility?" nachfragen
- Bei komplexen Changes: Plan als Markdown-File speichern lassen

---

## 3. 🛠️ CODE — Implementieren

**Ziel:** Änderungen umsetzen (nur Devs schreiben Code, aber alle können steuern).

### Für Devs
```
implement the OAuth2 authentication based on the plan we discussed
```
```
refactor utils.js to use ES2024 features while maintaining the same behavior
```
```
fix the UTC date bug in OrderService — the start date is off by one day
```
```
add proper error handling to all API endpoints in the auth module
```
```
add JSDoc comments to all public functions in auth.js
```
```
create a pr for my changes
```

### Für Tester / QA
```
add tests for the notification service — cover edge cases
```
```
write integration tests for the checkout API endpoints
```
```
generate test data fixtures for the user module
```
```
add test cases for the edge conditions: empty input, max length, special characters, null values
```

### Für PMs / Non-Devs
```
create a working prototype of the notification feature — keep it simple, just the core flow
```
```
build a simple dashboard that shows [data X] from the database
```
```
generate a demo page that shows the current API capabilities
```

### 💡 Pro-Tipps
- Auto-Accept Mode (`Shift+Tab` 1x) für schnelles Durcharbeiten
- `/clear` zwischen unabhängigen Tasks — frischer Kontext!
- Bei Fehler 2x korrigiert → `/clear` + besserer initialer Prompt
- `Esc` zum Stoppen, `Esc+Esc` zum Rewind (Code + Konversation zurücksetzen)

---

## 4. ✅ VERIFY — Prüfen

> **Das wichtigste Prinzip: Verification First!** 2-3x bessere Qualität durch konsequentes Prüfen.

### Für Devs
```
run the tests and fix any failures
```
```
run npm test and show me the results
```
```
review my recent changes for potential issues — security, performance, edge cases
```
```
check if my changes break any existing functionality
```
```
use a subagent to review this code for security issues
```
```
find deprecated API usage in our codebase
```

### Für Tester / QA
```
run all tests and summarize: how many pass, fail, skip?
```
```
analyze the test results — which failures are real bugs vs flaky tests?
```
```
check this PR for security vulnerabilities: SQL injection, XSS, missing auth
```
```
verify that the implemented code matches the requirements in [spec document]
```
```
compare the actual API response with the documented schema — any mismatches?
```

### Für PMs / Non-Devs
```
does this implementation match the requirements I described?
```
```
summarize what changed in this PR in non-technical terms
```
```
are there any user-facing changes I should know about?
```
```
what could go wrong with this feature from a user perspective?
```

### 💡 Pro-Tipps
- Immer Verification einbauen: Tests, Screenshots, Bash-Commands
- Claude kann seinen eigenen Output prüfen — "now verify your changes work"
- Subagents für Security Review: eigener Kontext, spezialisiert

---

## 5. 🚀 SHIP — Ausliefern

### Für Devs
```
summarize the changes I've made to the authentication module
```
```
create a pr with a detailed description
```
```
enhance the PR description with more context about the security improvements
```
```
create a changelog entry for this release
```
```
claude commit
```

### Für Tester / QA
```
create a test report summarizing all test results for this sprint
```
```
list all bugs found during testing with severity and reproduction steps
```
```
what's the test coverage percentage after our new tests?
```

### Für PMs / Non-Devs
```
write release notes for this feature — targeted at end users, not developers
```
```
create a summary of all changes in this sprint for the stakeholder update
```
```
what's the status of [feature X]? what's done, what's still open?
```

---

## 6. 🔧 MAINTAIN — Betreiben & Verbessern

### Für Devs
```
find all deprecated API calls and suggest modern replacements
```
```
analyze the performance bottlenecks in this module
```
```
what technical debt should we address first?
```
```
upgrade dependencies and check for breaking changes
```

### Für Tester / QA
```
which tests are flaky? find tests that sometimes pass and sometimes fail
```
```
find dead test code — tests that are skipped or never run
```
```
suggest tests we're missing based on recent bug reports
```

### Für PMs / Non-Devs
```
analyze our codebase health — any areas of concern?
```
```
how maintainable is this code? where should we invest in improvements?
```
```
create a technical health dashboard summary for the team
```

---

## Quick Reference

Slash Commands, Shortcuts, Anti-Patterns und Subagents: siehe [Kurzreferenz Claude Code](referenz-claude-code.md).

---

> Wenn du nicht weiterkommst, frag Claude einfach direkt:
> `"wie mache ich X?"` — Claude kennt seine eigenen Features besser als jedes Dokument.
