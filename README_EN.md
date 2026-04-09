[中文](./README.md)

# OpenClaw Source Code Anatomy

![License](https://img.shields.io/badge/license-MIT-green)
![Docs](https://img.shields.io/badge/docs-8%20articles-blue)
![Language](https://img.shields.io/badge/language-Chinese-orange)
![Lines](https://img.shields.io/badge/analyzed-1.2M%20lines-red)
![AI](https://img.shields.io/badge/AI%20Powered-Claude%20Code-purple)

> 📖 **Read Online:** https://anneheartrecord.github.io/openclaw-anatomy/

[OpenClaw](https://github.com/openclaw/openclaw) is an open-source personal AI assistant platform with 1.2M lines of TypeScript. 23+ messaging channels, 30+ LLM providers, 90+ extensions — all orchestrated through a WebSocket Gateway control plane.

This repository is a systematic technical analysis of OpenClaw's source code, with module-by-module breakdowns and hand-drawn technical illustrations.

Sister projects: [Claude Code Anatomy](https://github.com/anneheartrecord/claude-code-docs) | [Hermes Agent Anatomy](https://github.com/anneheartrecord/hermes-agent-anatomy)

## Table of Contents

| # | Article | Topics |
|---|---------|--------|
| 01 | Panoramic Overview | Architecture, code scale, positioning |
| 02 | Gateway Control Plane | WebSocket + JSON-RPC, authentication, device pairing |
| 03 | Agent Runtime | Conversation loop, provider failover, prompt generation |
| 04 | Extensions Plugin System | 90+ plugins, 150+ SDK exports, hook system |
| 05 | Multi-Channel Messaging | 23+ platform adapters, message normalization |
| 06 | Context Management | Token budgeting, compaction, memory flush |
| 07 | Memory & MCP | QMD indexing, temporal decay, tool protocol |
| 08 | Permissions & Deployment | Three-mode RBAC, pairing codes, multi-env deploy |

## License

MIT
