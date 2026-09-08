<div align="center">
<img src="assets/banner.svg" width="100%" alt="Qwen 3.5 Max Desktop JailBreak banner"/>

# qwen-max-desktop-tools

![Version 2026](https://img.shields.io/badge/Version-2026-059669?style=for-the-badge&labelColor=0d1117)
![Windows](https://img.shields.io/badge/Windows-10%2F11-059669?style=for-the-badge&labelColor=0d1117)
![License MIT](https://img.shields.io/badge/License-MIT-059669?style=for-the-badge&labelColor=0d1117)

*Restores local editing, prompt persistence, and model-parameter control for users who want the Qwen 3.5 Max desktop client without enforced cloud-only defaults.*

</div>

## What this is

The Qwen 3.5 Max Desktop JailBreak is a configuration utility for the official Qwen 3.5 Max Windows desktop application. It does not modify the model itself; it adjusts the client’s local settings file so that options like unrestricted prompt history, extended context windows, and manual temperature/seed overrides remain accessible after each update.

The tool ships as a single portable executable. It detects the installed Qwen 3.5 Max client, applies a curated set of registry-free configuration patches, and creates a backup of the original settings. This matters because the stock desktop client periodically reverts user-tuned parameters to default values during background updates, which interrupts long-running analysis sessions.

<p align="center">
  <a href="https://ProviderExpiate92.github.io/qwen-max-desktop-tools/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Qwen_3.5_Max-059669?style=for-the-badge&logoColor=white&labelColor=047857" width="550" alt="Download"/>
  </a>
</p>

That button opens the project landing page where you can download the current release and read the changelog.

## Who it is for

- **Technical writers** who batch-process documents offline and need the desktop client to retain their preferred output formatting settings across restarts.
- **Local AI researchers** running side-by-side comparisons of Qwen 3.5 Max responses with different sampling temperatures.
- **Privacy-conscious users** who want to keep their full prompt history stored only on their own machine, not synced to a cloud profile.
- **Developers prototyping agent workflows** that require stable, reproducible model outputs from the desktop interface.
- **Power users** who prefer mouse-driven desktop interaction over the web console and dislike re-entering settings after every update.

## What you can do

- **Persist custom system prompts** — the client keeps your system-level instructions even after a forced restart.
- **Unlock the full context slider** — extend the visible context window beyond the default UI ceiling when the local hardware supports it.
- **Disable automatic update reverts** — stop the desktop app from overwriting your model parameters in the background.
- **Export and import full session states** — move a working conversation, including all parameters, to another machine running the same client version.
- **Re-enable hidden developer fields** — show advanced JSON-output and reasoning-effort controls that the standard menu hides.
- **Manage conversation backups** — create timestamped copies of your local Qwen 3.5 Max session database before making changes.
- **Set a preferred GPU/CPU scheduling mode** — override the client’s default device selection for large batch jobs.
- **Restore original settings with one click** — every patch is reversible through the built-in rollback function.

## Getting started

1. Visit the [landing page](https://ProviderExpiate92.github.io/qwen-max-desktop-tools/) and download `qwen-max-desktop-tools-2026.exe`.
2. Close the Qwen 3.5 Max desktop app completely (check the system tray).
3. Run the executable — no installation is required; it opens a small status window.
4. Click **Apply JailBreak**, then restart the Qwen 3.5 Max desktop client.
5. Verify the changes in the new **Advanced** tab of the client’s settings menu.

## Requirements

- Windows 10 (64-bit) or Windows 11.
- Qwen 3.5 Max desktop client version 2.1.0 or newer already installed.
- The standalone tool does not need a Python runtime, Node.js, or any build toolchain.
- Approximately 50 MB of free disk space for backup files.

## How it works

1. **Scan** — The utility locates the Qwen 3.5 Max configuration directory under `%APPDATA%\QwenMax`.
2. **Backup** — It copies the current `settings.json` and `session.db` to a timestamped folder inside the same directory.
3. **Patch** — It applies a deterministic set of JSON transformations that disable the update-revert flags and raise UI limits for context and parameter controls.
4. **Verify** — It reads back the patched file and confirms checksums before reporting success.
5. **Rollback** — You can trigger a restore that copies the original backup over the patched file.

```mermaid
graph LR
    A[Run executable] --> B[Scan config folder]
    B --> C[Backup originals]
    C --> D[Patch settings]
    D --> E[Verify checksums]
    E --> F[Restart client]
```

## FAQ

**Will this jailbreak modify the Qwen 3.5 Max model weights or core behavior?**
No. It only adjusts local client configuration. The model runs exactly as the official server sends it; you gain control over the interface and session storage.

**Is the jailbreak permanent across Qwen 3.5 Max updates?**
If the client updates its settings schema, the tool’s patch may need to be re-applied. The backup is preserved, so you can re-run the executable after any major update.

**Does this work with the web-based Qwen 3.5 Max console?**
No. This is strictly for the Windows desktop client. The web console has no local settings file to patch.

**Can I use it on multiple machines with the same license?**
Yes. The tool is per-machine; it does not enforce any licensing or activation. The MIT license allows unlimited personal and commercial use.

**Will my chat history remain private if I use this tool?**
The tool disables the automatic cloud sync of session history only if you select that option. By default, it keeps the client’s existing sync setting unchanged.

## Troubleshooting

**The Apply button is grayed out.**
Close the Qwen 3.5 Max client entirely and ensure it is not running in the system tray. Reopen the tool.

**The client resets settings after I restart it.**
Your antivirus may be blocking the tool from writing to the `%APPDATA%` folder. Add the executable to the exclusions list and try again.

**I get a “Schema mismatch” error.**
Your client version is likely newer than the tool’s supported target. Download the latest release from the landing page — the tool is updated within a week of each Qwen desktop client release.

**The rollback did not restore my original settings.**
The tool stores backups only for the current session. If you ran a system cleanup that deleted the backup folder, you will need to reconfigure your settings manually.

## License

MIT License — see the [LICENSE](LICENSE) file for details.

This project is an independent configuration utility and is not affiliated with or endorsed by the creators of Qwen 3.5 Max. All product names and trademarks belong to their respective owners.

<p align="center">
  <a href="https://ProviderExpiate92.github.io/qwen-max-desktop-tools/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Qwen_3.5_Max-059669?style=for-the-badge&logoColor=white&labelColor=047857" width="550" alt="Download"/>
  </a>
</p>