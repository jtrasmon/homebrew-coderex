# Coderex Homebrew tap

Official Homebrew recipes for [Coderex](https://coderex.com) — the terminal for
AI coding agents, reachable from any browser.

## Install

```bash
# The desktop app (macOS, Apple Silicon)
brew install --cask jtrasmon/coderex/coderex

# The headless daemon + CLI, no GUI — for servers, CI, or a lean local setup
brew install jtrasmon/coderex/coderex
```

Both can be installed side by side: the cask gives you `Coderex.app`, the formula
gives you the `coderex` binary on your `PATH`. (The app bundles the same binary,
so you only need the formula if you want the control surface without the GUI.)

## After installing the formula

```bash
coderex serve            # start the headless daemon (local socket only)
coderex serve --remote   # also join the end-to-end-encrypted relay
coderex status           # what every agent is doing
coderex --help           # full command list
```

Docs: <https://coderex.com/docs>

## Notes

- **Apple Silicon, macOS 14+.** Linux support is planned; Windows after that.
- The cask declares `auto_updates true` because Coderex ships its own signed
  updater. `brew upgrade` is a no-op for the app — it updates itself. The
  **formula** does not self-update, so `brew upgrade` is how you update that one.
- Both recipes `livecheck` against the same release feed the in-app updater
  reads, so `brew outdated` stays accurate.

## Contributing

This tap is generated. Recipes are maintained in the Coderex client repo under
`packaging/homebrew/`, and `version` + `sha256` are bumped automatically by CI on
every release — please don't hand-edit them here.
