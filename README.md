# Catedral

Self-hosted app deployment on NixOS with isolated microVMs.

## Installation

```bash
curl -fsSL https://github.com/catedral-dev/catedral/releases/latest/download/catedral-linux-amd64 -o /usr/local/bin/catedral
chmod +x /usr/local/bin/catedral
catedral init
```

## Features

- **One Command Deploy**: `catedral app install <name>`
- **NixOS Conversion**: Convert Ubuntu/Debian to NixOS
- **MicroVM Isolation**: Each app in its own Firecracker VM
- **Security**: Tetragon eBPF + Trivy scanning
- **Auto-Upgrade**: Self-updating binary

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
