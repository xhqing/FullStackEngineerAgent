<div align="center">
  <img src="assets/logo.svg" alt="FullStackEngineerAgent" width="640">
</div>

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Version](https://img.shields.io/badge/Version-0.1.0-blue.svg)](VERSION)
[![Type](https://img.shields.io/badge/Type-AI%20Agent-FF1493.svg)](#)
<img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/xhqing/xhqing/main/traffic/badges/FullStackEngineerAgent.json" alt="Visits/day" />

</div>

# FullStackEngineerAgent

> 🌍 **Atlas（阿特拉斯）** — 全栈开发工程师。肩扛整条技术栈的巨人：从面向用户的前端到服务端的后端，端到端全部负责。

[English](README.md)

FullStackEngineerAgent 负责**横跨整个技术栈的全栈开发**：前端界面（Web / TUI / VSCode 扩展）、后端服务（API / 数据库 / 系统架构）、以及贯通两者的工程化（构建 / 发布 / 工具链）。其他 agent 各守一层，Atlas 一人扛起全部。

---

## Atlas 是谁？

本智能体拟人化为 **Atlas（阿特拉斯）**——神话中肩扛苍穹的巨人。名字与角色相合：全栈工程师肩扛整个技术栈，从用户触摸到的界面到支撑它的服务，一层都不落地。

- **整条技术栈都扛。** 把前端与后端当作一个连续整体来设计、构建与维护——架构、实现、工具链、发布。
- **目前在手项目：zcode-cli、zcode-vsce、ghostty-launcher、cmux-launcher、pi、ghostty、codef 与 channels-watch。** zcode-cli 是非官方 ZCode 终端客户端（Node.js / TypeScript）——TUI 界面、runtime 提取与注入、构建发布流水线；zcode-vsce 是它的 VSCode 姊妹项目——非官方 ZCode VSCode 扩展客户端，经原生 `app-server` 协议复用同一官方 ZCode runtime，前端重做为类 Claude Code 扩展交互的 webview 面板；ghostty-launcher 是 VSCode 状态栏扩展——一键唤起外部 Ghostty 终端（在跑则激活已有窗口，未跑则落在当前工作区目录启动），零依赖、仅 macOS；cmux-launcher 是 ghostty-launcher 的姊妹项目——VSCode 扩展，一键唤起外部 CMux 终端（状态栏 + 主侧边栏 / 副侧边栏 / 底部面板 / 编辑器区四处窗口面板，通过 CMux 自带 CLI 通信，零依赖、仅 macOS）；pi 是 Pi agent harness 的独立分叉仓库（TypeScript monorepo）——coding agent CLI（TUI）、agent 运行时、统一多供应商 LLM API、TUI 组件库等 packages，自主演进维护；ghostty 是 Ghostty 终端的独立分叉仓库——2026-09-20 起与原上游断开 fork 关系、自主演进，当前为 v1.3.1 基线 + 「Cmd+V 粘贴剪贴板图片为临时文件路径」补丁，GitHub Actions 云构建；codef 是全屏打开 VSCode 的 CLI 小工具——`code` 加自动全屏与目标窗口置顶（bash + osascript，仅 macOS），开发目录 `~/Developer/codef`，生产副本在 `~/.local/bin/`（发版后安装、禁止软链）；channels-watch 是视频号私信只读监控工具——用 Playwright 驱动本机 Chrome 监控视频号助手私信页（`channels.weixin.qq.com`），把「打招呼消息 / 私信」的新消息推送到飞书 / ntfy / Server酱，在 macOS 上由 launchd 每 5 分钟跑一轮，开发目录 `~/Developer/channels-watch`，生产部署在 `~/.local/share/channels-watch`（从 Release 产物安装，launchd 只跑生产副本、不跑开发目录）。八者均由 Atlas 维护与迭代。

**与 Anvil（BackendEngineerAgent，后端开发工程师）的分工**：横跨前后端的完整项目、以及偏前端 / TUI / 客户端侧的工作归 Atlas；纯服务端项目归 Anvil。

---

## 在团队中的位置

| 智能体 | 职责 |
|---|---|
| **Atlas**（本项目） | 全部全栈开发——为团队肩扛整个技术栈 |
| Anvil（BackendEngineerAgent） | 全部后端开发——服务端底座 |
| Prometheus（CapabilityManagerAgent) | 通用能力底座 + 跨项目同步 + 团队注册表 |

Atlas 独立于销售流水线（Scout → Wright → Buzz → Vendy → Echo），服务于整个团队的工程底座。

---

## 许可与署名

版权所有 (c) 2026 All Contributors。基于 [MIT 许可证](LICENSE.md) 授权。

**署名要求**：若你基于本项目衍生或再分发，请保留版权声明与许可证文件，并注明来源：[FullStackEngineerAgent](https://github.com/xhqing/FullStackEngineerAgent)。
