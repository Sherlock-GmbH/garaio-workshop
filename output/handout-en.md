# Workshop Preparation Guide

Complete these steps **before** the workshop to avoid setup delays.

---

## 1. Claude Account

1. Go to [claude.ai](https://claude.ai) and sign up
2. Subscribe to **Claude Pro** ($20/month) — required for Claude Code
3. Verify your subscription is active

---

## 2. Install Claude Code

### Mac / Linux
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

### Windows
```powershell
irm https://claude.ai/install.ps1 | iex
```

### Verify Installation
```bash
claude --version
```
You should see a version number (e.g., `claude 1.x.x`).

---

## 3. Azure CLI + DevOps Extension

We use the Azure CLI to interact with Azure DevOps work items during the workshop.

### Mac
```bash
brew install azure-cli
az extension add --name azure-devops
```

### Windows
```powershell
winget install Microsoft.AzureCLI
az extension add --name azure-devops
```

### Login
```bash
# Login to GARAIO AG Tenant
az login --tenant <TENANT_ID> --allow-no-subscriptions

# Login to Azure DevOps
az devops login --organization https://dev.azure.com/garaio-allpura
```

> **Finding the Tenant ID:**
> - Azure Portal → Microsoft Entra ID → Overview → "Tenant ID"
> - Or via CLI: `az account list --output table` (shows TenantId per account)

---

## 4. Clone Demo Repository (Kalkulationstool)

### Prerequisites

**Mac:**
```bash
brew install git-credential-manager
```

**Windows:**
Git for Windows includes Git Credential Manager:
```powershell
winget install Git.Git
```

### Clone
```bash
git clone https://garaio-allpura@dev.azure.com/garaio-allpura/Kalkulationstool/_git/Kalkulationstool
```

You'll be prompted for credentials — use the PAT token created during `az devops login`, or GCM will handle it automatically after `az login`.

---

## 5. Pre-Check

Run this quick test to ensure everything works:

```bash
# Open terminal in the cloned repo
cd Kalkulationstool

# Start Claude Code
claude

# Inside Claude, type:
Was ist dieses Projekt? Gib mir einen kurzen Überblick.

# Claude should read CLAUDE.md and explain the architecture
# Exit with Ctrl+C or /exit
```

---

## 6. Checklist

- [ ] Claude Pro subscription active
- [ ] Claude Code installed (`claude --version` works)
- [ ] Azure CLI installed (`az --version` works)
- [ ] Azure DevOps Extension added (`az boards --help` works)
- [ ] Logged in to GARAIO Azure tenant
- [ ] Kalkulationstool repo cloned
- [ ] Test run successful (Claude reads CLAUDE.md)

---

## Troubleshooting

**"Command not found: claude"**
→ Restart your terminal, or add to PATH manually

**"Authentication failed" (Claude)**
→ Run `claude login` and follow the prompts

**"Subscription required"**
→ Ensure Claude Pro is active at [claude.ai/settings](https://claude.ai/settings)

**"az: command not found"**
→ Restart terminal after installation. Mac: `brew install azure-cli`. Windows: `winget install Microsoft.AzureCLI`

**Git clone fails with 401/403**
→ Ensure `az login` was successful, then try: `az devops login --organization https://dev.azure.com/garaio-allpura`

---

## Questions?

Contact: [github.com/haaslukas](https://github.com/haaslukas)

See you at the workshop! 🚀
