# Catedral

Deploy self-hosted apps in isolated microVMs. One command. NixOS underneath.

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
