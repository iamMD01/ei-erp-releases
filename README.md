# EI ERP — releases

Signed Linux desktop releases for **EI ERP**, a secure college ERP.

> Source code is private. This repository contains **only signed release artifacts and update manifests**.

## Install (Debian / Ubuntu)

1. Open the [releases page](https://github.com/iamMD01/ei-erp-releases/releases).
2. Download `EI-ERP_<version>_amd64.deb`.
3. Install it:

```bash
sudo apt install ./EI-ERP_<version>_amd64.deb
```

## Auto-update

EI ERP checks the update manifest for its baked-in channel.

| Channel | Audience | Manifest |
|---|---|---|
| `alpha` | builder / owner | [channel-alpha/latest.json](https://github.com/iamMD01/ei-erp-releases/releases/download/channel-alpha/latest.json) |
| `beta` | pilot staff | created at the first beta release |
| `stable` | whole college | created at the first stable release |

Updates are downloaded and verified with the updater public key before installation.
`.deb` updates ask for your admin password (polkit/sudo).

## Verify

Each release includes a `.sig` file (minisign signature). The app verifies the
signature automatically before installing an update. Do not install an artifact
without its `.sig`.

## Channels

- **alpha** — frequent prereleases; may break.
- **beta** — pilot staff; feature-complete but still testing.
- **stable** — production.

Alpha and beta releases are GitHub prereleases. Stable releases are full releases.

## Security

- Only signed artifacts are published here.
- The source code stays private.
- The updater private key is never in this repository or in the app.

## Linux package

The current Linux package is `.deb`. AppImage is deferred until the
AppImageLauncher/bundler issues are resolved.
