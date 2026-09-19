# CHANGELOG

## [未发布]

### 变更

- **子项目清单新增 pi**（`.claude/CLAUDE.md`、AGENTS.md、README.md、README_cn.md）。为什么改：用户明确将 pi（`~/Developer/pi`，Pi agent harness 的个人 fork，fork 自 earendil-works/pi，origin 为 xhqing/pi）交由 Atlas 负责，成为第四个子项目；按「新增子项目时同步更新清单」与「清单须与全局映射表一致」规则同步登记。改了什么：①`目前在手项目` 补 pi（TypeScript monorepo：coding agent CLI / agent 运行时 / 统一多供应商 LLM API / TUI 组件库，跟上游同步并做个人维护）；②子项目清单加 `pi（~/Developer/pi）`；③双语 README 在手项目段同步；④全局注册表映射表已同步加行（镜像同步记 CapabilityManagerAgent CHANGELOG）；⑤pi 的 `.claude/CLAUDE.md` 新建（项目指南 + Atlas 全文随附；pi 项目 `.gitignore` 已忽略 `.claude/`，不进 git；根 AGENTS.md 为上游开发规则、保留不动），zcode-cli、zcode-vsce、ghostty-launcher 的随附版同步两处变更（顺手修复 ghostty-launcher 随附版滞后：其在手项目行仍为无 ghostty-launcher 自身的旧快照，本次一并更新到最新）。

### 变更

- **子项目清单新增 ghostty-launcher**（`.claude/CLAUDE.md`、README.md、README_cn.md）。为什么改：用户新建 ghostty-launcher——VSCode 状态栏一键唤起外部 Ghostty 终端的扩展（在跑激活已有窗口 / 未跑带工作区目录启动，零依赖、仅 macOS），并明确交由 Atlas 管理；按「子项目清单须与全局映射表一致」规则同步登记。改了什么：①`目前在手项目` 补 ghostty-launcher；②子项目清单加 `ghostty-launcher（~/Developer/ghostty-launcher）`；③双语 README 在手项目段同步；④全局注册表映射表已同步加行（镜像同步记 CapabilityManagerAgent CHANGELOG）；⑤ghostty-launcher 的 `.claude/CLAUDE.md` 已按超集规则配置（项目指南 + Atlas 全文随附），zcode-cli、zcode-vsce 的随附版同步两处变更。（`.claude/CLAUDE.md`）。为什么改：①全局通用规则已全部迁入 `~/.claude/CLAUDE.md`、`~/.claude/rules/` 目录废弃，本项目两处指向旧目录的引用失效；②全局 find-skill skill 已删（实际使用中从未用到），通用能力句式不再提及。改了什么：①「遵守通用工作规则（见全局 `~/.claude/rules/`）」与「通用工作纪律（三个规则文件名）见全局 `~/.claude/rules/`」两处改指 `~/.claude/CLAUDE.md`；②「（anysearch 实时搜索、find-skill 找 skill 等）」→「（anysearch 实时搜索等）」。子项目 zcode-cli、zcode-vsce 副本已按超集规则同步（不另记其 CHANGELOG）。

### 变更

- **CLAUDE.md 子项目清单路径更新**（`.claude/CLAUDE.md`）。为什么改：项目现址在 `~/Developer/`（`~/Documents/Projects/` 旧址已弃用，2026-09-08 迁移收尾时发现清单仍指旧路径），避免后续会话被引导到不存在的位置；本次连同子项目 zcode-cli、zcode-vsce 及其两个功能分支 worktree（zcode-cli-model-picker、zcode-cli-custom-env-rename）的同款行一并对齐（超集关系保持一致）。改了什么：子项目清单中 zcode-cli、zcode-vsce 的路径由 `~/Documents/Projects/` 更新为 `~/Developer/`。

- **子项目清单新增 zcode-vsce**（`.claude/CLAUDE.md` 子项目清单、README.md、README_cn.md）。为什么改：用户立项新建 zcode-vsce——ZCode 的非官方 VSCode 扩展客户端（后端复用 zcode-cli 提取的官方 runtime、走 `app-server` 协议，前端为类 CC 扩展交互的 webview），与 zcode-cli 平行、同归 Atlas 负责；按「子项目清单须与全局映射表一致」规则同步登记。改了什么：`目前在手项目` 表述补 zcode-vsce、子项目清单加 `zcode-vsce（~/Documents/Projects/zcode-vsce）`；zcode-vsce 的 `.claude/` 已按超集规则配置（settings 三件套逐字节一致、CLAUDE.md 内容随附）。

## [0.1.0] - 2026-08-22

### 新增

- 项目立项：新建 FullStackEngineerAgent（Atlas，全栈开发工程师）——团队第 16 位成员，负责横跨前端与后端的完整开发工作（前端界面 / 后端服务 / 贯通两者的工程化），独立于销售流水线。为什么：团队此前只有纯后端工程师 Anvil，横跨前后端的项目（如 zcode-cli 这类 TUI 客户端）需要一位端到端负责的全栈角色。
- `.claude/` 脚手架：角色化 `CLAUDE.md`（你是谁 / 工作原则 / 工具 / 约束 / 子项目同步 / 位置）+ `settings.json`（hooks 空配置）+ `settings.local.example.json`（入库模板）+ `settings.local.json`（本机配置，`.gitignore` 忽略）。按「通用能力开源单一出口」规则不内置通用 skill / rules 副本。
- `assets/logo.svg`：640×200 渐变横幅（紫 → 蓝，圆角 rx=28，emoji 主体 + 项目名 + 职称），按 icon-design 规范绘制。
- 中英双语 `README.md` / `README_cn.md`：含 logo、标准徽章（License / Version / Type + 团队 Visitors 访问量徽章）、拟人名介绍、与 Anvil 的分工、团队位置、许可与署名。
- `LICENSE.md`（MIT，版权署名 All Contributors）、`VERSION`（0.1.0）、`.gitignore`（docs / node_modules / .DS_Store / settings.local.json / tmp / artifacts / __pycache__ / .env 系列）。
- 子项目关系登记：zcode-cli 为本项目的首个子项目，`.claude/` 维护超集关系（权威源 → 子项目超集，自动同步）。
