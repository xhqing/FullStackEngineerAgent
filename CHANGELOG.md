# CHANGELOG

## [未发布]

### 变更

- **子项目清单新增 zcode-vsce**（`.claude/CLAUDE.md` 子项目清单、README.md、README_cn.md）。为什么改：用户立项新建 zcode-vsce——ZCode 的非官方 VSCode 扩展客户端（后端复用 zcode-cli 提取的官方 runtime、走 `app-server` 协议，前端为类 CC 扩展交互的 webview），与 zcode-cli 平行、同归 Atlas 负责；按「子项目清单须与全局映射表一致」规则同步登记。改了什么：`目前在手项目` 表述补 zcode-vsce、子项目清单加 `zcode-vsce（~/Documents/Projects/zcode-vsce）`；zcode-vsce 的 `.claude/` 已按超集规则配置（settings 三件套逐字节一致、CLAUDE.md 内容随附）。

## [0.1.0] - 2026-08-22

### 新增

- 项目立项：新建 FullStackEngineerAgent（Atlas，全栈开发工程师）——团队第 16 位成员，负责横跨前端与后端的完整开发工作（前端界面 / 后端服务 / 贯通两者的工程化），独立于销售流水线。为什么：团队此前只有纯后端工程师 Anvil，横跨前后端的项目（如 zcode-cli 这类 TUI 客户端）需要一位端到端负责的全栈角色。
- `.claude/` 脚手架：角色化 `CLAUDE.md`（你是谁 / 工作原则 / 工具 / 约束 / 子项目同步 / 位置）+ `settings.json`（hooks 空配置）+ `settings.local.example.json`（入库模板）+ `settings.local.json`（本机配置，`.gitignore` 忽略）。按「通用能力开源单一出口」规则不内置通用 skill / rules 副本。
- `assets/logo.svg`：640×200 渐变横幅（紫 → 蓝，圆角 rx=28，emoji 主体 + 项目名 + 职称），按 icon-design 规范绘制。
- 中英双语 `README.md` / `README_cn.md`：含 logo、标准徽章（License / Version / Type + 团队 Visitors 访问量徽章）、拟人名介绍、与 Anvil 的分工、团队位置、许可与署名。
- `LICENSE.md`（MIT，版权署名 All Contributors）、`VERSION`（0.1.0）、`.gitignore`（docs / node_modules / .DS_Store / settings.local.json / tmp / artifacts / __pycache__ / .env 系列）。
- 子项目关系登记：zcode-cli 为本项目的首个子项目，`.claude/` 维护超集关系（权威源 → 子项目超集，自动同步）。
