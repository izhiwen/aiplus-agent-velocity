# AiPlus Agent Velocity

[中文 README](README.zh-CN.md)

## The Pain

The agent says a task will take five hours. You nod and go get coffee. Twenty minutes later it says "done." Next week the same agent estimates another five hours for a similar task. Again, twenty minutes. No one writes down the actual time. The pattern repeats until you stop trusting any estimate at all.

## The Solution

AiPlus Agent Velocity records every estimate and actual completion time as local JSONL under `.aiplus/velocity/`. It detects human-time bias when estimates anchor on engineer hours instead of agent minutes. After a few records, it produces p50 and p90 AI-native estimates and shows a next-estimate adjustment. No raw prompts are stored. No data uploads. Normal records rotate at 200, rare cases at 20.

## Quick Start

If you already have AiPlus:

```bash
cd MyProject
aiplus install codex
aiplus velocity init
aiplus velocity estimate --task-type compact-hardening --human-estimate 5h
```

Or clone the standalone source:

```bash
git clone https://github.com/izhiwen/aiplus-agent-velocity.git
cd aiplus-agent-velocity
```

See `core/schemas/` for the JSON schemas.
