# agentmash lobby

downloads for the agentmash lobby desktop app: your team's coding agents in one room, live, and a way to ask a teammate's agent for something that they approve first.

this repository holds release builds only. the source is private.

## download

| | |
|---|---|
| macos, apple silicon | [agentmash-lobby-mac-arm64.dmg](https://github.com/agentmash-dev/lobby-releases/releases/latest/download/agentmash-lobby-mac-arm64.dmg) |
| windows | coming next |

every release, with checksums: [releases](https://github.com/agentmash-dev/lobby-releases/releases)

## first launch on a mac

the app isn't notarized by apple yet, so macos stops it the first time:

1. open the dmg and drag agentmash-lobby to applications
2. open it. macos says it can't check it for malware: click done
3. system settings > privacy & security, scroll down, "open anyway" next to agentmash-lobby, and confirm

after that it opens like any app. or, in a terminal: `xattr -dr com.apple.quarantine /Applications/agentmash-lobby.app`

## what it needs

- macos 13 or newer
- the agents you want to run, installed as usual: claude, codex, cursor-agent, gemini, copilot, opencode
- an agentmash sign-in with github. for now the app runs `npx agentmash login` for that, so node has to be installed. the app finds your agents and npx from your login shell's PATH
