# idea-forge

A brainstorming skill for Claude Code (also works in Codex). It's for people who judge ideas well but get stuck generating them.

It shows a problem map before any ideas, generates about 30 ideas silently, and kills them with rules weighted by your goal (learning, competition, or business). You only see 5-7 finalists in a triage format, each with honest odds. It remembers your taste and every dead idea, so later sessions skip the slop.

## Install

Claude Code on Windows:
```powershell
git clone https://github.com/Rurtt/idea-forge
Copy-Item -Recurse idea-forge\idea-forge $HOME\.claude\skills\
```
On macOS or Linux: `cp -r idea-forge/idea-forge ~/.claude/skills/`

Codex: copy the same folder into `~/.codex/skills/`.

## Use
Say "brainstorm ideas for X" or "what should I build for this hackathon". On first use it asks 6 quick questions to fill `taste.md`. After that it learns from what you reject and lock.

Your `taste.md` and `graveyard.md` are personal. If you fork this repo, don't commit yours back.
