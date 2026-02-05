<p align="center">
  <img src="assets/logo.svg" alt="Catedral" width="400">
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

## Installation

```bash
curl -fsSL https://github.com/catedral-dev/catedral/releases/latest/download/catedral-linux-amd64 -o /usr/local/bin/catedral
chmod +x /usr/local/bin/catedral
catedral init
```

## Quick Start

```bash
catedral app install komodo    # Deploy Komodo
catedral app install plausible # Deploy Plausible Analytics
catedral app list              # See running apps
```

## Why Catedral?

- **One command**: No YAML, no Docker, no Kubernetes
- **Real isolation**: Each app runs in its own VM
- **NixOS**: Atomic updates, instant rollback
- **Security**: Built-in monitoring and scanning

## Plans

| Plan | Apps | Price |
|------|------|-------|
| Free | 3 | $0 |
| Pro | Unlimited | $19/mo |
| Enterprise | Source code | Custom |

## Documentation

https://catedral.dev

## License

Proprietary. See LICENSE for details.
