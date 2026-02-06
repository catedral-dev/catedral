<p align="center">
  <img src="assets/logo.svg" alt="Catedral" width="200">
</p>

<p align="center">
  <strong>Security Layer for Container Platforms</strong>
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

## v0.2.0 — What's New

| Feature | Description |
|---------|-------------|
| 🏰 **Hardened microVMs** | Maximum isolation, each VM is a fortress |
| 🛡️ **eBPF immune system** | Neutralizes anomalies instantly at kernel level |
| 🌐 **Local or remote** | Deploy on this machine or any server via SSH |
| 📦 **Container-friendly** | Run Komodo/Dokploy/Coolify secured inside microVMs |
| 🔐 **Ephemeral secrets** | Injected at runtime, never touch disk |

**Setup wizard handles everything:** NixOS conversion, Cloudflare Tunnel, secrets.

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
| Coolify runs on Docker over normal Linux | Coolify runs in Docker INSIDE a hardened microVM |
| A compromised container can escalate | A compromised container dies in the microVM, doesn't touch the host |
| Secrets stored on disk | Ephemeral secrets in RAM only |
| Trust that Docker isolates properly | Hardware-level isolation (Firecracker) |

### The Analogy

**Catedral is to Coolify what Cloudflare is to Nginx.**

- Cloudflare doesn't replace your web server—it protects it
- Catedral doesn't replace your container orchestrator—it hardens it

```bash
catedral app install coolify   # Coolify now runs in a hardened microVM
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

### 💰 Stop Paying the Cloud Tax
- One server, one price. No surprise bills, no bandwidth metering, no "contact sales"
- A $7/mo Hetzner VPS + $19/mo Catedral Pro replaces $150+/mo of PaaS fees
- Know exactly what you pay. Forever.

### ⚡ One Command, Not Twenty
- No YAML. No Docker Compose. No Kubernetes. No Terraform + Ansible + Nginx + Certbot
- `curl | sh` and you have infrastructure
- Deploy any app in under 60 seconds

### 🔒 Real Isolation, Not Theater
- Each app runs in its own microVM with its own dedicated kernel
- Hardware-enforced boundaries—not namespaces pretending to be secure
- One compromised app can't touch the others

### 🛡️ Military-Grade Security Built-In
- **eBPF Runtime Protection**: Kernel-level monitoring that detects and blocks threats in real-time—not just logs, actually stops attacks
- **Hardened Kernels**: Every microVM runs a hardened NixOS kernel scoring 90+ on Lynis security audits
- **SOPIX Compliance**: Security architecture designed for military-grade operational security
- **Ephemeral Keys**: Encryption keys exist only in RAM during runtime—never persisted to disk
- **Vulnerability Scanning**: Automatic CVE scanning before every deployment with policy enforcement
- **Secrets Never Touch Disk**: All sensitive data encrypted with Age (X25519 + Argon2id), decrypted only in memory

### 🔄 Break Things Fearlessly
- Atomic deployments: either fully applied or fully reverted
- Instant rollback to any previous state
- No partial updates leaving you in broken states

### 🌍 Works Everywhere
- **On your server**: Hetzner, OVH, DigitalOcean, Vultr, bare metal, your closet server
- **On your laptop**: Full local development with the same security guarantees
- No vendor lock-in. Your config is portable. Your data is yours
- Works offline. Your infrastructure doesn't stop because someone else's cloud went down

### 📦 Container-Friendly

Want to use containers? Catedral has your back. Install container platforms **secured inside microVMs**:

```bash
catedral app install komodo     # Container management platform
catedral app install dokploy    # Self-hosted Vercel/Netlify alternative
catedral app install coolify    # Heroku & Netlify alternative
```

Catedral provides the security foundation—hardened VMs, eBPF protection, encrypted secrets. The container platform handles orchestration. Best of both worlds.

### 📦 App Catalog
Pre-configured apps ready to deploy in seconds:

```bash
catedral app install gitea        # Git hosting
catedral app install plausible    # Privacy-friendly analytics
catedral app install vaultwarden  # Password manager
catedral app install komodo       # Container management
catedral app install n8n          # Workflow automation
catedral app list                 # See all available apps
```

Every app runs in its own isolated microVM with dedicated resources and security policies.

---

## Who It's For

- **Developers** who want cloud convenience without cloud prices
- **Startups** that need to stretch every dollar of runway
- **Agencies** managing multiple client projects on dedicated infrastructure
- **Security-conscious teams** that need real isolation, not container theater
- **NixOS enthusiasts** tired of hostile tooling

---

## Installation

```bash
curl -fsSL https://catedral.dev/install | sh
```

That's it. The installer auto-detects your platform and installs the right binary.

## Quick Start

```bash
# The wizard handles everything
catedral init

# Install apps
catedral app list
catedral app install ghost

# Manage
catedral vm list
catedral app status ghost
```

The setup wizard guides you through:
- Local or remote server setup
- Automatic NixOS conversion (Ubuntu/Debian)
- Cloudflare Tunnel configuration
- Passphrase and secrets setup

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
│     → Local dev, remote management, testing                 │
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

---

## Security Architecture

Catedral isn't just a deployment tool—it's a security platform.

| Layer | Protection |
|-------|------------|
| **Runtime** | eBPF-based kernel monitoring blocks threats in real-time |
| **Isolation** | Each app in its own microVM with dedicated hardened kernel |
| **Secrets** | Age encryption (X25519), keys only exist in RAM |
| **Network** | Encrypted overlay mesh between nodes |
| **Audit** | Complete trail of every action for compliance |
| **Scanning** | Automated CVE detection before deployment |

**Lynis Score 90+**: Every microVM kernel passes security hardening benchmarks that most production servers fail.

---

## Pricing

| Plan | Apps | Price |
|------|------|-------|
| **Free** | 3 | $0 |
| **Pro** | Unlimited | $19/mo |
| **Enterprise** | Source code | Custom |

No credit card required. No surprise bills. No "contact sales" for pricing.

---

<p align="center">
  <a href="https://catedral.dev">Documentation</a> •
  <a href="https://github.com/catedral-dev/catedral/releases">Releases</a>
</p>

<p align="center">
  <sub>Elastic License 2.0. See LICENSE for details.</sub>
</p>
