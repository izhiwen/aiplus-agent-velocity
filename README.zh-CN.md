# AiPlus Agent Velocity

[English README](README.md)

## 痛点

agent 说一个任务要 5 小时。你点头去喝咖啡。20 分钟后它说"做完了"。下周同一个 agent 对类似任务又估 5 小时。又是 20 分钟。没人记下实际时间。这个模式反复出现，直到你不再相信任何估时。

## 解决方案

AiPlus Agent Velocity 把每次估时和实际完成时间记为本地 JSONL，存在 `.aiplus/velocity/` 下。它检测 human-time bias：当估时锚定在工程师小时而不是 agent 分钟时触发提醒。积累几条记录后，它输出 p50 和 p90 的 AI-native 估时，并显示 next-estimate adjustment。不存 raw prompt，不上传数据。普通记录保留最新 200 条，rare case 保留最新 20 条。

## 快速开始

如果你已安装 AiPlus：

```bash
cd MyProject
aiplus install codex
aiplus velocity init
aiplus velocity estimate --task-type compact-hardening --human-estimate 5h
```

或 clone standalone 源码：

```bash
git clone https://github.com/izhiwen/aiplus-agent-velocity.git
cd aiplus-agent-velocity
```

JSON schema 见 `core/schemas/`。
