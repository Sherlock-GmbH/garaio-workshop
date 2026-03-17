# Claude Code CLI — Ressourcen & Links
*Handout zum Garaio Workshop, 18. März 2026*

---

## 🏁 Einstieg & Erste Schritte

### Für Entwickler

| Ressource | Beschreibung |
|-----------|-------------|
| [How to Use Claude Code (Beginner Guide)](https://www.builder.io/blog/how-to-use-claude-code) | Von Installation bis zum ersten Code Change — inkl. CLAUDE.md Setup und Workflow |
| [Claude Code Tutorial: Complete Getting Started Guide](https://www.nxcode.io/resources/news/claude-code-tutorial-beginners-guide-2026) | Step-by-step mit Plan Mode, Commands und Real-World Workflows |
| [5-Minute Quickstart](https://blakecrosley.com/blog/claude-code-quickstart) | CLAUDE.md, Permissions und Hooks in unter 5 Minuten |
| [Complete Developer's Guide to Commands](https://timdietrich.me/blog/claude-code-commands-guide/) | Alle Slash Commands, CLI Flags und Keyboard Shortcuts |
| [Practical Guide to Automating Your Dev Workflow](https://henriquesd.medium.com/claude-code-a-practical-guide-to-automating-your-development-workflow-675714db08ed) | `/init`, CLAUDE.md und praktische Automation |

### Für Product Manager & Nicht-Devs

| Ressource | Beschreibung |
|-----------|-------------|
| [Claude Code for Product Managers](https://www.sachinrekhi.com/p/claude-code-for-product-managers) | Der Referenz-Artikel für PMs — PRDs, Prototyping, Analytics |
| [Claude Cowork: The Ultimate Guide for PMs](https://www.productcompass.pm/p/claude-cowork-guide) | Cowork als visueller Einstieg — Emails, Contracts, Invoices |
| [13 Claude Code Projects That Changed My PM Role](https://medium.com/@ondrej.machart/13-claude-code-projects-that-changed-my-product-manager-role-over-the-last-6-months-7057b9045d51) | PM baut eigene Tools mit Claude Code, 0 Code-Wissen nötig |
| [Stop re-explaining your product to AI — Build a Skill instead](https://designproject.io/blog/how-to-build-custom-claude-code-skills-and-why-your-team-needs-them/) | Skills für Teams — auch ohne Dev-Hintergrund erstellbar |

---

## 🧠 Best Practices

| Ressource | Beschreibung |
|-----------|-------------|
| ⭐ [claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) | 15'000+ Stars auf GitHub — Community-kuratierte Tips, Workflows und Patterns von Claude Code Creator Boris Cherny |
| [CLAUDE.md Best Practices: 10 Sections to Include](https://uxplanet.org/claude-md-best-practices-1ef4f861ce7c) | Konkrete Struktur für gute CLAUDE.md Dateien |
| [A Mental Model: Skills, Subagents, and Plugins](https://levelup.gitconnected.com/a-mental-model-for-claude-code-skills-subagents-and-plugins-3dea9924bf05) | Wie die Bausteine zusammenspielen — das grosse Bild |

### Community-Tipps (Reddit r/ClaudeCode)

- **CLAUDE.md aufteilen**: Stabile Regeln in `.claude/rules/`, CLAUDE.md als Scratch-Surface für Session-Kontext
- **Stop-Hook für Learnings**: Am Ende jeder Session ein kurzes Learning in `coder-patterns.md` schreiben → nach 100+ Sessions ein echtes Asset
- **Worktree Isolation**: Agents arbeiten in isolierten Git-Branches, können sich nicht gegenseitig überschreiben
- **Task-Prompt > CLAUDE.md > Context Files**: Die Hierarchie, wie Claude Anweisungen priorisiert

---

## 🔧 Advanced: Hooks, Agent Teams, Skills

| Ressource | Beschreibung |
|-----------|-------------|
| [From Tasks to Swarms: Agent Teams in Claude Code](https://alexop.dev/posts/from-tasks-to-swarms-agent-teams-in-claude-code/) | Agent Teams — koordinierte Sessions mit Shared Tasks und Direct Messaging |
| [5 Production Hooks From Scratch](https://blakecrosley.com/blog/claude-code-hooks-tutorial) | Auto-Format, Lint, Block-Rules — hands-on |

---

## 📖 Offizielle Anthropic Dokumentation

- **Claude Code Docs**: https://docs.anthropic.com/en/docs/claude-code
- **Hooks Guide**: https://docs.anthropic.com/en/docs/claude-code/hooks-guide
- **Release Notes**: https://docs.anthropic.com/en/release-notes/claude-code
- **Official Plugins**: https://github.com/anthropics/claude-plugins-official
- **Plugin Dev Kit**: https://github.com/anthropics/claude-code/tree/main/plugins

---

## 📊 Claude Code vs. Copilot — Kurzvergleich

| Dimension | Claude Code | GitHub Copilot |
|-----------|-------------|----------------|
| **Paradigma** | Autonomer Agent — Tasks delegieren | IDE-Autocomplete — schneller tippen |
| **Context Window** | 1M Tokens (Opus 4.6) | 32k–128k |
| **SWE-bench** | 80.8% (höchster Score) | Variiert je nach Modell |
| **Multi-File Changes** | ✅ Plant und führt aus | Manuell orchestriert |
| **Inline Autocomplete** | ❌ | ✅ |
| **GitHub-Integration** | Git Commands | Native (PRs, Issues, Actions) |
| **Preis** | CHF 20–200/Monat | CHF 10–39/Monat |
| **Stärke** | Komplexe Tasks eliminieren | Daily Coding beschleunigen |

> *"Copilot macht dich 55% schneller beim Tippen. Claude Code eliminiert ganze Tasks. Das ist ein fundamentaler Unterschied."*

**Empfehlung**: Beide komplementär nutzen — Copilot für Daily Coding, Claude Code für die 20% komplexen Tasks die 80% der Zeit fressen.

---

## 🔗 Weiterführend

- **Vergleichs-Artikel**: [Claude Code vs. GitHub Copilot: A Real Developer Comparison](https://codegen.com/blog/claude-code-vs-github-copilot/) (Codegen, März 2026)
- **Benchmark-Übersicht**: [Claude Code vs Copilot: Terminal Agent vs Multi-Model Platform](https://www.morphllm.com/comparisons/claude-code-vs-copilot) (Morph, März 2026)
- **Community**: [r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/) — aktive Community mit täglichen Workflow-Posts

---

*Zusammengestellt von Lukas Haas · März 2026*
