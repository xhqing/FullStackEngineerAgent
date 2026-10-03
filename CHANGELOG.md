# CHANGELOG

## [未发布]

### 新增

- **新建子项目 codef（`~/Developer/codef`，全屏打开 VSCode 的 CLI 小工具）并纳入子项目清单**。为什么改：用户要把 `codef` 命令（原先内嵌在 `~/.zshrc` 的 shell 函数，多窗口时不置顶、时序不可靠）从个人配置提升为正式项目——建独立 git 仓库作开发目录、交 Atlas 维护，`~/.local/bin/` 作为生产目录（发版后安装、禁止软链，运行版本与开发版本隔离）。改了什么（2026-09-22）：①新建 codef 仓库初版 0.1.0（单文件 bash + osascript：打开前后窗口标题 diff 锁定本次目标窗口 → 菜单栏 Window 菜单聚焦（跨 Space / 已全屏有效）→ AXFullScreen 检查后条件全屏，修复三田：置顶错窗口 / 固定 sleep 时序落空 / 已全屏被误退出；详见该仓库 CHANGELOG）；②权威源「目前在手项目」与「当前子项目清单」加入 codef，六个子项目（zcode-cli、zcode-vsce、ghostty-launcher、cmux-launcher、pi、ghostty）随附版同步；③全局注册表映射表加 codef 行；④`~/.zshrc` 旧 codef 函数删除（换指向说明行），生产副本 `~/.local/bin/codef` 与仓库 v0.1.0 对齐；⑤codef 本地 `git init`，开源到 GitHub 待用户确认。

### 变更

- **ghostty 子项目转为独立分叉仓库，去除上游同步表述**（权威源 CLAUDE.md、五个子项目随附版、双语 README、全局注册表 + 镜像）。为什么改：用户于 2026-09-20 决定 ghostty 仓库（xhqing/ghostty）断开与原上游 ghostty-org/ghostty 的 fork 关系、独立分叉自主维护（GitHub 已是独立仓库状态），旧文案「跟上游版本 rebase 维护」会误导后续会话去做上游同步。改了什么：①ghostty 在手项目 / 清单 / README / 注册表表述改为「2026-09-20 起断开 fork 关系、自主演进，v1.3.1 基线 + 贴图补丁，主分支 main」；②ghostty 仓库侧同步：main 重置到补丁线、删 7 个上游遗留分支、删 paste-image 分支（历史并入 main）、build.yml 触发分支改 main、MEMO M1 改为「自主判断手动移植上游重要改进」、仓库描述改独立 fork 说明、fork CHANGELOG 记断开条目；③镜像同步记 CapabilityManagerAgent CHANGELOG。

### 新增

- **新建子项目 ghostty（`~/Developer/ghostty`，Ghostty 终端个人维护 fork）并纳入子项目清单**。为什么改：用户要给原生 Ghostty 加「Cmd+V 粘贴剪贴板图片为临时文件路径」能力（cmux 同款体验，方案源自上游被关闭的 PR ghostty-org/ghostty#11571，经本机双实验验证可行），经 fork + 云构建 + 实测通过后正式成为长期维护仓库（跟上游 stable tag rebase）。改了什么（2026-09-20）：①fork 上游到 xhqing/ghostty，分支 `paste-image` = v1.3.1 + 32 行补丁（`NSPasteboard+Extension.swift` 图片兑底分支）；②新建 `.github/workflows/build.yml`（标准 macOS runner + Zig 0.15.2 + Xcode 26.2 + ad-hoc 签名，构建途中排掉三个坑：Zig 0.15.2 tarball 新命名、Xcode 26.6 SDK 与 Zig 链接不兼容、改 Info.plist 与签名顺序）；③tag `v1.3.1-paste.1` + GitHub Release（产物 universal Ghostty.app.zip）；④本机正式版从 Release 产物安装替换；⑤权威源「目前在手项目」与「当前子项目清单」加入 ghostty，五个子项目随附版同步；⑥全局注册表映射表加 ghostty 行、Atlas 职责行过时列举改为概括式；⑦补历史欠账：cmux-launcher 纳入时漏更新双语 README 在手项目段与注册表映射表（当时 CHANGELOG 亦未记），本次一并补齐；zcode-cli、zcode-vsce 随附版同时落后 cmux 一版，一并补齐；pi 断 fork 时双语 README 描述仍写「跟上游同步」，一并修正为独立分叉表述。

- **新建子项目 cmux-launcher（`~/Developer/cmux-launcher`）并加入子项目清单**。为什么改：用户要求新建一个 ghostty-launcher 的姊妹项目——从 VSCode 一键唤起外部 CMux 终端，且唤出入口要覆盖主侧边栏 / 副侧边栏 / 底部面板（Panel）/ 编辑器区（Edit area）四处。改了什么（2026-09-20）：①新建 cmux-launcher 项目初版 0.1.0（零依赖 VSCode 扩展，通过 CMux 自带 CLI 的 Unix socket 接口实现窗口枚举 / 聚焦 / 新建，状态栏按钮 + 四处窗口面板，详见该仓库 CHANGELOG）；②权威源「目前在手项目」与「当前子项目清单」加入 cmux-launcher，ghostty-launcher、pi 两个子项目随附版同款行同步（zcode-cli、zcode-vsce 无 CLAUDE.md，无需同步）；③cmux-launcher 本地 `git init`，开源到 GitHub 待用户确认。

### 变更

- **pi 转为独立分叉仓库，去除上游同步表述**（根 `CLAUDE.md` + 四个子项目随附版 + 全局注册表镜像）。为什么改：用户已于 2026-09-19 在 GitHub 断开 xhqing/pi 与 earendil-works/pi 的 fork 关系（isFork=false），此后分叉开发、与原始上游无关；旧文案「个人 fork、跟上游同步」会误导后续会话去做上游同步合并。改了什么：①权威源「目前在手项目」里 pi 的描述改为「独立分叉仓库……不再同步上游」；②zcode-cli、zcode-vsce、ghostty-launcher、pi 四个子项目的随附版同款行同步；③pi 根 `CLAUDE.md` 项目指南同步改写三处（Atlas 职责去掉同步合并并修正权威源路径悬空引用（`.claude/CLAUDE.md` → 根 `CLAUDE.md`）、仓库定位改独立分叉、删「上游同步时移植 AGENTS.md 变更」句）；④pi 本地 `git remote remove upstream`（pi 侧变更记 pi 仓库 `packages/coding-agent/CHANGELOG.md`）。

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
