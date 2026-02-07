<p align="center">
  <img src="assets/logo.svg" alt="Catedral" width="200">
</p>

<p align="center">
  <strong>Complete isolation for every app. Not containers. Real security.</strong>
</p>

<p align="center">
  <em>Catedral is to Coolify what Cloudflare is to Nginx</em>
</p>

<p align="center">
  <a href="https://github.com/catedral-dev/catedral/releases/latest">
    <img src="https://img.shields.io/github/v/release/catedral-dev/catedral?style=flat-square" alt="Release">
  </a>
  <a href="https://catedral.dev">
    <img src="https://img.shields.io/badge/docs-catedral.dev-blue?style=flat-square" alt="Docs">
  </a>
</p>

---

## What's New

| Feature | Description |
|---------|-------------|
| **Complete isolation per app** | Each app runs in total isolation—CVE in one can't touch others |
| **Runtime protection** | Detects and blocks threats in real-time |
| **Local or remote** | Deploy on this machine or any server via SSH |
| **Container-friendly** | Run Komodo/Dokploy/Coolify with enterprise security |
| **Ephemeral secrets** | Injected at runtime, never touch disk |

**Setup wizard handles everything.** Answer a few questions, we do the rest.

```bash
curl -fsSL https://catedral.dev/install | sh
catedral init  # The wizard guides you through everything
```

---

## Already Using Coolify, Dokploy, or Komodo?

**Perfect. Install them INSIDE Catedral.**

Catedral isn't here to replace your container platform—it's here to protect it.

| Without Catedral | With Catedral |
|------------------|---------------|
| All apps share resources | **Complete isolation per app** |
| CVE in one app = all apps at risk | CVE in one app = that app only |
| A compromised container can escalate | A compromised container hits isolation boundary |
| Secrets stored on disk | Ephemeral secrets in RAM only |

### The Analogy

**Catedral is to Coolify what Cloudflare is to Nginx.**

- Cloudflare doesn't replace your web server—it protects it
- Catedral doesn't replace your container orchestrator—it hardens it

```bash
catedral app install coolify   # Coolify now runs with enterprise security
catedral app install dokploy   # Same for Dokploy
catedral app install komodo    # Or Komodo
```

**Your workflow stays the same. Your security level goes up.**

---

## The Problem

Cloud infrastructure became an unnecessary tax. Vercel charges $0.15/GB bandwidth. Bare metal costs $0.001/GB. That's **150x difference**.

Most developers pay Vercel/Railway/Render out of inertia, not technical necessity.

**Catedral is the exit.**

---

## Why Developers Choose Catedral

### Stop Paying the Cloud Tax
- One server, one price. No surprise bills, no bandwidth metering, no "contact sales"
- A $7/mo Hetzner VPS + $20/mo Catedral Pro replaces $150+/mo of PaaS fees
- Know exactly what you pay. Forever.

### One Command, Not Twenty
- No YAML. No Docker Compose. No Kubernetes. No Terraform + Ansible + Nginx + Certbot
- `curl | sh` and you have infrastructure
- Deploy any app in seconds

### Complete Isolation per App (The Killer Feature)
- Each app runs in complete isolation—not shared like containers
- A vulnerability in Ghost cannot touch Plausible—they're completely separated

### Production-Grade Security Built-In
- **Runtime Protection**: Detects and blocks threats in real-time—not just logs, actually stops attacks
- **Hardened Environments**: Every app runs in a security-audited environment
- **Ephemeral Secrets**: Keys exist only during runtime—never persisted to disk
- **Vulnerability Scanning**: Automatic CVE scanning before every deployment with policy enforcement

### Updates That Don't Break Things
- Either fully applied or fully reverted
- Instant rollback if something goes wrong
- No partial updates leaving you in broken states

### Works Everywhere
- **On your server**: Hetzner, OVH, DigitalOcean, Vultr, bare metal, your closet server
- **On your laptop**: Full local development with the same security guarantees
- No vendor lock-in. Your config is portable. Your data is yours
- Works offline. Your infrastructure doesn't stop because someone else's cloud went down

### Container-Friendly

Want to use containers? Catedral has your back. Install container platforms with enterprise security:

```bash
catedral app install komodo     # Container management platform
catedral app install dokploy    # Self-hosted Vercel/Netlify alternative
catedral app install coolify    # Heroku & Netlify alternative
```

Catedral provides the security foundation. The container platform handles orchestration. Best of both worlds.

### App Catalog
Pre-configured apps ready to deploy in seconds:

```bash
catedral app install gitea        # Git hosting
catedral app install plausible    # Privacy-friendly analytics
catedral app install vaultwarden  # Password manager
catedral app install komodo       # Container management
catedral app install n8n          # Workflow automation
catedral app list                 # See all available apps
```

---

## Who It's For

- **Developers** who want cloud convenience without cloud prices
- **Startups** that need to stretch every dollar of runway
- **Agencies** managing multiple client projects on dedicated infrastructure
- **Security-conscious teams** that need real isolation, not container theater

---

## Installation

```bash
curl -fsSL https://catedral.dev/install | sh
```

That's it. The installer auto-detects your platform and installs the right binary.

### Verify Download (Recommended)

```bash
# Download checksums
curl -L -o CHECKSUMS.txt \
  https://github.com/catedral-dev/catedral/releases/latest/download/CHECKSUMS.txt

# Verify binary integrity
sha256sum -c CHECKSUMS.txt --ignore-missing
```

## Quick Start

```bash
# The wizard handles everything
catedral init

# Install apps
catedral app list
catedral app install ghost

# Manage
catedral status
catedral app status ghost
```

---

## Supported Platforms

| Binary | OS | Architecture | Where It Runs |
|--------|----|--------------|--------------|
| `catedral-linux-amd64` | Linux | Intel/AMD 64-bit | **Servers** — Hetzner, OVH, DigitalOcean, Vultr, AWS EC2, any VPS |
| `catedral-linux-arm64` | Linux | ARM 64-bit | Raspberry Pi 4/5, AWS Graviton, Oracle Ampere, Hetzner ARM |
| `catedral-darwin-amd64` | macOS | Intel | MacBooks/iMacs Intel (2015-2020) — for **local development** |
| `catedral-darwin-arm64` | macOS | Apple Silicon | MacBooks M1/M2/M3/M4 — for **local development** |

Works on any Linux server with root access.

---

## Passphrase-Protected Access

Even SSH access to your server isn't enough to control Catedral. All operations require unlocking with your passphrase first:

```bash
$ catedral app list
Error: Catedral is locked. Run 'catedral unlock' first

$ catedral unlock
Enter passphrase:
✓ Unlocked for this session

$ catedral app list
NAME         STATUS    UPTIME
ghost        running   3d 2h
gitea        running   15d 4h
plausible    running   7d 1h
```

**Session-based security:**
- Sessions expire automatically
- No persistent tokens stored on disk
- Even if an attacker gains SSH access, they cannot manage your infrastructure without the passphrase

---

## Pricing

| Plan | Apps | Price |
|------|------|-------|
| **Free** | 3 | $0 |
| **Pro** | Unlimited | $20/mo |
| **Enterprise** | Custom | Contact us |

No credit card required. No surprise bills. No "contact sales" for pricing.

---

<p align="center">
  <a href="https://catedral.dev">Documentation</a> •
  <a href="https://github.com/catedral-dev/catedral/releases">Releases</a>
</p>

<p align="center">
  <sub>Licensed under the <a href="https://catedral.dev/license">Catedral Software License Agreement</a>.</sub>
</p>
