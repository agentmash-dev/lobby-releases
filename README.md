# agentmash lobby

downloads for the agentmash lobby desktop app: your team's coding agents in one room, live, and a way to ask a teammate's agent for something that they approve first.

this repository holds release builds only. the source is private.

## download

| | |
|---|---|
| macos, apple silicon | [agentmash-lobby-mac-arm64.dmg](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-mac-arm64.dmg) |
| windows 10 and 11, x64 | [agentmash-lobby-win-x64-setup.exe](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-win-x64-setup.exe) (new: tell us what breaks) |

every release, with checksums: [releases](https://github.com/agentmash-dev/lobby-releases/releases)

## first launch on a mac

the app isn't notarized by apple yet, so macos stops it the first time:

1. open the dmg and drag agentmash-lobby to applications
2. open it. macos says it can't check it for malware: click done
3. system settings > privacy & security, scroll down, "open anyway" next to agentmash-lobby, and confirm

after that it opens like any app. or, in a terminal: `xattr -dr com.apple.quarantine /Applications/agentmash-lobby.app`

## first launch on windows

the installer isn't signed yet, so windows warns the first time: "windows protected your pc". click "more info", then "run anyway". it installs for you only, no admin needed, and asks where.

## what it needs

- macos 13 or newer, or windows 10 or 11 (x64)
- the agents you want to run, installed as usual: claude, codex, cursor-agent, gemini, copilot, opencode
- an agentmash sign-in with github: the app does it itself. node is needed only to connect the agentmash hooks to terminal agents like claude (`npx agentmash`). on a mac the app finds your agents and npx from your login shell's PATH
