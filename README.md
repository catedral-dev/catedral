<p align="center">
  <img src="assets/logo.svg" alt="Catedral" width="200">
</p>

<p align="center">
  <strong>Deploy self-hosted apps in isolated microVMs. One command. NixOS underneath.</strong>
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

## The Problem

Cloud infrastructure became an unnecessary tax. Vercel charges $0.15/GB bandwidth. Bare metal costs $0.001/GB. That's **150x difference**.

Most developers pay Vercel/Railway/Render out of inertia, not technical necessity.

**Catedral is the exit.**

---

## Why Developers Choose Catedral

### 💰 Stop Paying the Cloud Tax
- One server, one price. No surprise bills, no bandwidth metering, no "contact sales"
- A $4/mo Hetzner server + $19/mo Catedral Pro replaces $150+/mo of PaaS fees
- Know exactly what you pay. Forever.

### ⚡ One Command, Not Twenty
- No YAML. No Docker Compose. No Kubernetes. No Terraform + Ansible + Nginx + Certbot
- `curl | sh` and you have infrastructure. A junior dev can deploy without being DevOps
- Deploy any app in under 60 seconds

### 🔒 Real Isolation, Not Theater
- Each app runs in its own VM with its own kernel
- One compromised app can't touch the others
- Not namespaces pretending to be secure—real boundaries

### 🔄 Break Things Fearlessly
- Atomic deployments: either fully applied or fully reverted
- Instant rollback to any previous state
- No partial updates leaving you in broken states

### 🌍 Works Everywhere
- Runs on your hardware—Hetzner, OVH, your closet server
- No vendor lock-in. Your config is portable. Your data is yours
- Works offline. Your infrastructure doesn't stop because someone else's cloud went down

### 🛡️ Security Without a PhD
- Secrets encrypted at rest. No plaintext configs
- Vulnerability scanning before deploy
- Real-time monitoring of what's actually running

---

## Who It's For

- **Indie hackers** paying $60-150/mo for things that run fine on a $4 VPS
- **LATAM & SEA developers** where $20/mo Vercel Pro is a luxury
- **DevOps freelancers** managing 5-10 client servers with scripts and prayers
- **Developers burned** by Netlify's $55 overage charges or AWS weekend surprises
- **NixOS enthusiasts** tired of hostile tooling

---

## Installation

```bash
curl -fsSL https://catedral.dev/install | sh
```

That's it. The installer auto-detects your platform and installs the right binary.

## Quick Start

```bash
catedral app install komodo      # Deploy in seconds
catedral app install plausible   # Add another
catedral app list                # See what's running
```

---

## Supported Platforms

| Binary | OS | Architecture | Where It Runs |
|--------|----|--------------|--------------|
| `catedral-linux-amd64` | Linux | Intel/AMD 64-bit | **Servers** — Hetzner, OVH, DigitalOcean, Vultr, AWS EC2, any VPS |
| `catedral-linux-arm64` | Linux | ARM 64-bit | Raspberry Pi 4/5, AWS Graviton, Oracle Ampere, Hetzner ARM |
| `catedral-darwin-amd64` | macOS | Intel | MacBooks/iMacs Intel (2015-2020) — for **local development** |
| `catedral-darwin-arm64` | macOS | Apple Silicon | MacBooks M1/M2/M3/M4 — for **local development** |

**In practice:**

```
┌─────────────────────────────────────────────────────────────┐
│  Your laptop (macOS/Linux)                                  │
│  └─ catedral-darwin-arm64 or catedral-linux-amd64           │
│     → Run remote commands, development, testing             │
└─────────────────────────────────────────────────────────────┘
                           │
                           │ SSH / API
                           ▼
┌─────────────────────────────────────────────────────────────┐
│  Your server (Linux)                                        │
│  └─ catedral-linux-amd64 (99% of cases)                     │
│     → Where microVMs and apps actually run                  │
└─────────────────────────────────────────────────────────────┘
```

**99% of users need:** `catedral-linux-amd64` on the server (Hetzner, OVH, etc.)

---

## Pricing

| Plan | Apps | Price |
|------|------|-------|
| **Free** | 3 | $0 |
| **Pro** | Unlimited | $19/mo |
| **Enterprise** | Source code | Custom |

No credit card required. No surprise bills. No "contact sales" for pricing.

---

## The Anti-PaaS

Catedral is the tool we wished existed.

You shouldn't need a PhD in DevOps to deploy a web app securely. You shouldn't pay 150x markup for bandwidth. You shouldn't wake up to a $2000 AWS bill.

**Your server. Your rules. Your cathedral.**

---

<p align="center">
  <a href="https://catedral.dev">Documentation</a> •
  <a href="https://github.com/catedral-dev/catedral/releases">Releases</a>
</p>

<p align="center">
  <sub>Proprietary. See LICENSE for details.</sub>
</p>
