[English](./README_EN.md)

# OpenClaw 源码解剖

![License](https://img.shields.io/badge/license-MIT-green)
![Docs](https://img.shields.io/badge/docs-8%20articles-blue)
![Language](https://img.shields.io/badge/language-中文-orange)
![Lines](https://img.shields.io/badge/analyzed-1.2M%20lines-red)
![AI](https://img.shields.io/badge/AI%20Powered-Claude%20Code-purple)

> 120 万行 TypeScript，一个个人 AI 助手平台的完整拆解 — 从 Gateway 控制面到 90+ Extensions 插件体系

[OpenClaw](https://github.com/openclaw/openclaw) 是一个开源的个人 AI 助手平台。你在自己的设备上跑一个 Gateway，它帮你连接 WhatsApp、Telegram、Slack、Discord 等 23+ 个消息渠道，对接 30+ 个 LLM Provider，通过 90+ 个 Extensions 插件扩展能力。

和 Hermes Agent 的 Python 单体架构不同，OpenClaw 用 TypeScript 写了一个完整的**插件化平台**。核心是一个 WebSocket Gateway 控制面，所有能力通过 Extensions 挂载。IM 渠道是插件，LLM Provider 是插件，工具是插件，连记忆系统都是插件。

这个系列对 OpenClaw 的源码做了系统化的技术分析，配有大量手绘风格技术插图。

## 文档目录

### 全景篇

| 篇章 | 内容 | 关键发现 |
|------|------|---------|
| [01-全景图](docs/01-全景图.md) | 架构分层、代码规模、定位分析 | 120 万行 TypeScript，Gateway + Extensions 双核架构 |

### 核心架构篇

| 篇章 | 内容 | 关键发现 |
|------|------|---------|
| [02-Gateway 控制面](docs/02-Gateway控制面.md) | WebSocket + JSON-RPC、认证、设备配对 | call.ts 30,872 行、150 个 RPC 方法 |
| [03-Agent Runtime](docs/03-Agent-Runtime.md) | 对话循环、Provider failover、prompt 生成 | 事件驱动 + 多 Provider 自动切换 |
| [04-Extensions 插件体系](docs/04-Extensions插件体系.md) | 90+ 插件、SDK、Hook 系统 | 五阶段生命周期 + requireApproval 审批 |

### 功能模块篇

| 篇章 | 内容 | 关键发现 |
|------|------|---------|
| [05-多渠道消息系统](docs/05-多渠道消息系统.md) | 23+ 平台适配、消息标准化 | 统一消息格式 + 渠道状态机 |
| [06-上下文管理](docs/06-上下文管理.md) | Token 预算、Compaction、Memory Flush | 五阶段 Compaction + 20K 保护底线 |
| [07-记忆系统与 MCP](docs/07-记忆系统与MCP.md) | QMD 索引、时序衰减、MCP 工具协议 | 向量 + 时序混合检索 |
| [08-权限与部署](docs/08-权限与部署.md) | 三模式权限、配对码、多环境部署 | Pairing Code + SSL pinning |

## 关键数据

| 指标 | 数据 |
|------|------|
| 版本 | v2026.3.28 |
| TypeScript 文件 | 6,259+ 个 |
| 代码总量 | ~1,200,000 行 |
| Gateway | 294 个文件 |
| Extensions | 90+ 个插件 |
| 消息渠道 | 23+ 个 |
| LLM Provider | 30+ 个 |

## 姊妹篇

- [Claude Code 源码解剖](https://anneheartrecord.github.io/claude-code-docs/) — 51 万行 TypeScript，工程驱动的编程助手
- [Hermes Agent 源码解剖](https://anneheartrecord.github.io/hermes-agent-anatomy/) — 33 万行 Python，研究驱动的全栈 Agent

## 目标读者

正在做 Agent 产品的工程师、对多渠道 AI 助手架构感兴趣的开发者、想了解大型 TypeScript 项目如何做插件化设计的技术人。
