# homebrew-context-bar

Homebrew tap for **[ContextBar](https://github.com/htahaozlu/context-bar)** —
local-first repository context generator with a native macOS menubar
companion and WidgetKit extension for Claude Code and Codex usage.

## Install

One-liner:

```sh
brew install --cask htahaozlu/context-bar/context-bar
```

`brew` auto-taps `htahaozlu/homebrew-context-bar` on first install. Or tap
explicitly:

```sh
brew tap htahaozlu/context-bar
brew install --cask context-bar
```

## Upgrade

```sh
brew update
brew upgrade --cask htahaozlu/context-bar/context-bar
```

`livecheck` is wired to the GitHub releases, so `brew outdated --cask`
picks up new versions automatically.

## Uninstall

```sh
brew uninstall --cask context-bar
brew untap htahaozlu/context-bar
```

Add `--zap` to also remove `~/.context-bar`, the shared App Group
container (`~/Library/Group Containers/DQJT5BCZCM.com.htahaozlu.contextbar`),
preferences, and saved application state:

```sh
brew uninstall --cask --zap context-bar
```

## What's inside ContextBar

- **Repository context**: stable `.context-bar/` artifacts +
  agent-readable `AGENT.md` / `CLAUDE.md` snapshots regenerated on every
  refresh.
- **Native macOS menubar companion**: AppKit popover with active agent,
  context %, rolling 5h / 7d limits, parallel sessions, and a live theme
  picker.
- **WidgetKit extension** (small / medium / large): same usage surface in
  Notification Center or on the desktop, sandboxed with the App Group
  entitlement so it passes `chronod` enrolment on macOS 14+ (including
  macOS 26 Tahoe).
- **Share Today's HUD**: render the current HUD as a PNG card from the
  popover footer or headlessly via `CONTEXTBAR_SHARE_RENDER_PATH`.
- Built for Claude Code, Codex, and any tool that writes session
  transcripts under `~/.claude` or `~/.codex`.

## Requirements

- macOS Ventura (13) or later. Universal binary: Apple Silicon + Intel.
- The DMG is signed with Developer ID (`Hasan Taha Ozlu`,
  team `DQJT5BCZCM`) and notarized by Apple — no Gatekeeper bypass
  needed.

## Links

- Main repo / docs: <https://github.com/htahaozlu/context-bar>
- Releases: <https://github.com/htahaozlu/context-bar/releases>
- Changelog: <https://github.com/htahaozlu/context-bar/blob/main/CHANGELOG.md>
- File issues against the **main repo**, not this tap.

## Why a separate tap?

Homebrew's core `homebrew-cask` repository requires GitHub projects to
hit a notability threshold (≥75 stars / ≥30 forks / ≥30 watchers) before
new casks are accepted. ContextBar is young; in the meantime this tap
gives users a single `brew install` command and a working `livecheck`
+ auto-upgrade flow. When the main repo grows past the threshold the
cask will be submitted to `homebrew/homebrew-cask` and this tap will be
kept as a fallback / mirror.
