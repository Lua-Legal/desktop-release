# Lua Legal Desktop Releases

This repository hosts public binaries for the Lua Legal desktop app. The application source code lives in the private [`Lua-Legal/desktop-v2`](https://github.com/Lua-Legal/desktop-v2) repository, but every push to its `latest-release` branch automatically publishes signed & notarized builds here.

## Download

- **Latest release:** https://github.com/Lua-Legal/desktop-release/releases/latest  
- **Specific versions:** https://github.com/Lua-Legal/desktop-release/releases

Each release includes:
- `Lua Legal-<version>-arm64.dmg` – signed & notarized installer
- `latest-mac.yml` – metadata for in-app auto-updates
- `Lua Legal-<version>-arm64.dmg.sha256` – checksum for manual verification

## Installation

1. Download the `.dmg` from the release page.
2. Open the disk image and drag **Lua Legal.app** into `/Applications`.
3. Launch the app. Gatekeeper will recognise the notarized binary; if prompted, choose “Open”.

## Auto-Updates

The desktop app is configured to check `https://github.com/Lua-Legal/desktop-release` for updates every few hours (and once shortly after launch). When a new version is available:
- You’ll see an in-app notification.
- You can choose when to download/install.
- Updates install automatically on quit after download.

If updates appear stuck, ensure the app is installed inside `/Applications` and that network access to GitHub’s CDN is allowed.

## Verifying Downloads

To verify the downloaded DMG:

```bash
shasum -a 256 "Lua Legal-<version>-arm64.dmg"
```

Compare the output with the `.sha256` file published alongside the release.

## Support

For help, reach out to support@lualegal.ai or open a ticket through the in-app help menu.
