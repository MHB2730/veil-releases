# Veil — Releases

Public **release channel** for the Veil desktop app (an offline legal-document
anonymiser). This repository holds only:

- `latest.json` — the version manifest the in-app updater reads, and
- the signed installer for each version, published as a **GitHub Release** asset.

The application **source code is private**. Nothing here exposes it.

## How updates work
Veil checks `latest.json` once at launch, in a separate process, *before* the app locks
itself offline and *before* any matter is opened — so the process that handles your
documents never touches the network. If a newer version is listed, Veil offers to
download the installer (verified by SHA-256) and install it.

## `latest.json`
```json
{
  "version": "0.1.0",
  "installer_url": "https://github.com/MHB2730/veil-releases/releases/download/v0.1.0/Veil-Setup-0.1.0.exe",
  "sha256": "<hex>",
  "notes": "..."
}
```

Releases are published with `packaging/publish.ps1` from the private source repo.
