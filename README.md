# DevoCleaner

Reclaim disk space from years of build artifacts, package caches, and AI agent leftovers - without touching your source code.

DevoCleaner scans your dev folders for the heavy stuff that piles up over time (`node_modules`, `target`, `__pycache__`, Xcode `DerivedData`, Gradle caches, agent transcripts, and dozens more), groups duplicates intelligently, and moves them safely to the Trash so you can recover anything you didn't mean to delete.

## Download

Grab the latest signed and notarized `.dmg` for macOS from the [Releases page](https://github.com/AA1labs/DevoCleaner/releases/latest). The DMG is a universal binary - works on both Apple Silicon (M1+) and Intel Macs.
Windows and Linux builds are on the roadmap.

The app is signed and notarized by Apple, so it launches silently on first run - no Gatekeeper warning.

## Features

### Smart artifact detection
Recognises 30+ categories out of the box:

- **Build outputs** - Rust `target`, Node `node_modules`, Next.js `.next`, Nuxt `.nuxt`, Vite/Webpack `dist`, Gradle, Maven, Go vendor, CocoaPods, Composer vendor, Elixir `_build`/`deps`, Ruby `.bundle`, Flutter, Android, Xcode DerivedData
- **Language caches** - Python `__pycache__`, virtualenvs, Dart pub cache, Git pack cache
- **AI agent leftovers** - Claude Code, Cursor, Kiro, GitHub Copilot, VS Code Copilot, Windsurf, Codex, Dyad, Kimi, Void, TabNine, and a generic detector for the rest

### Safe by default
Every "delete" goes to the system Trash, not `rm -rf`. You can always restore from Recycle Bin / Finder Trash if you change your mind.

### Grouped duplicates
When dozens of `__pycache__` or `node_modules` share the same parent name (e.g. all under `rich/` or `react/`), they collapse into a single expandable row showing total size and shared path - no more scrolling through 50 near-identical entries.

### Fast, parallel scanning
Powered by Rust + Rayon for true parallel directory traversal. Tens of thousands of dirs scan in seconds, with a streaming UI so you can start selecting before the scan finishes.

### Smart filtering
- Tabbed view: **Build artifacts** vs **AI Agents**
- Per-category sidebar with running totals
- Sort by size, path, or category
- Configurable agent-artifact size threshold (skip the small fry)

### Built-in auto-update
The app checks this repo for new releases on launch. When one is found, click the **Update** button in the header to download, verify, and install in place - no manual reinstall.

## Privacy

DevoCleaner runs entirely on your machine. No telemetry, no analytics, no network requests other than the update check against this repository's releases.

## License

Proprietary. Copyright (c) 2026 AA1 Labs. All rights reserved. See [LICENSE](LICENSE) for the full end-user license agreement. Free for personal and internal business use; redistribution and reverse engineering are not permitted.
