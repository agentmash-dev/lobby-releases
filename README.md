# agentmash lobby

downloads for the agentmash lobby desktop app: your coding agents side by side on your own logins, your team's sessions next to yours, and a way to ask a teammate's agent for something that they approve first. the download page is [agentmash.dev/download](https://agentmash.dev/download).

this repository holds release builds only. the source is private.

## download

| | |
|---|---|
| macos, apple silicon | [agentmash-lobby-mac-arm64.dmg](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-mac-arm64.dmg) |
| macos, intel | [agentmash-lobby-mac-x64.dmg](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-mac-x64.dmg) |
| windows 10 and 11, x64 | [agentmash-lobby-win-x64-setup.exe](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-win-x64-setup.exe) (new: tell us what breaks) |

every release, with checksums: [releases](https://github.com/agentmash-dev/lobby-releases/releases)

## install on a mac, one command

```
curl -fsSL https://github.com/agentmash-dev/lobby-releases/releases/latest/download/install.sh | sh
```

it picks your mac's kind (apple silicon or intel), downloads the latest zip, checks it against the release's SHA256SUMS, puts the app in /Applications and opens it. what curl downloads isn't marked for gatekeeper, so the app opens right away while it isn't notarized yet. the script is [install.sh](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/install.sh) in each release: read it first if you like.

## updates

from 0.26.0 the app updates itself: a newer release shows in its status bar (and in the app menu's check for updates…). one click downloads it, checks it against the release's SHA256SUMS and the app's signature, and restarts the app on it; on windows it runs the new installer. an older copy updates once more with the command above or a download.

## first launch on a mac, from the dmg

the app isn't notarized by apple yet, so macos stops it the first time:

1. open the dmg and drag agentmash-lobby to applications
2. open it. macos says it can't check it for malware: click **done**, not "move to trash"
3. system settings > privacy & security, scroll down, "open anyway" next to agentmash-lobby, and confirm

after that it opens like any app.

## first launch on windows

the installer isn't signed yet, so windows warns the first time: "windows protected your pc". click "more info", then "run anyway". it installs for you only, no admin needed, and asks where.

## what it needs

- macos 13 or newer (apple silicon or intel), or windows 10 or 11 (x64)
- the agents you want to run, installed as usual: claude code, cursor, github copilot, opencode, goose, antigravity cli, or gemini cli on a gemini api key. its agents page installs each one with its maker's own command, in a terminal. codex stays off for now: its conversations open in history and go on in another agent
- an agentmash sign-in with github: the app does it itself. node is needed only to connect the agentmash hooks to terminal agents like claude (`npx agentmash`). on a mac the app finds your agents and npx from your login shell's PATH, and in ~/.local/bin and ~/.opencode/bin where their installers put them
