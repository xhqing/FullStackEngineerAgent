# CHANGELOG

## [Unreleased]

### 变更（T1 / T2 闭环归档：回归防护网与 Worker 测试约束全部落地，2026-11-13）

- **为什么改**：用户要求把 `TODO.md` 里剩下的两条待办都办完。两条现已全部落地，按 TODO 纪律移入归档，不留已完成事项冒充活跃待办。
- **改了什么**：① `TODO.md` 清空活跃条目（只剩「无活跃条目」）；② `TODO-archive.md` 新增「2026-11-13 T1 / T2 闭环归档」节，保留两条原文 + 完成说明——T1 附 8 个子项目的摸底 / 处置表（含 ghostty 暂不接入单测的三条理由与接入条件、cmux 首次只能在 CI 实跑的边界），T2 附 8 个子项目全部加节的 PR 清单。
- **回归检查**：① 归档保留原条目全文，一字不改；② 编号体系不变，T1 / T2 不复用；③ 版本号不动（文档类改动，不触发 bump / 发版）；④ 上一轮的 T3 归档条目未改动。

### 变更（T3 闭环归档：Hopper 遗留清理已完成，2026-11-13）

- **为什么改**：`TODO.md` 的 T3（清理 Hopper 遗留的 `cases/` 存量并给 TestEngineerAgent 仓库收尾）三项工作已全部完成——TestEngineerAgent 的 PR #18 里删掉了 `cases/`、加了双语 README + AGENTS 退役说明、把该仓库 TODO 全量归档。按 TODO 纪律，已完成的条目必须移入归档，不能留在活跃清单里冒充未办事项。
- **改了什么**：① `TODO.md` 删除 T3 条目（黄色节随之清空、节标题一并移除），只剩橘色的 T1 / T2；② 新建 `TODO-archive.md`，按「正文一字不改 + 状态标记」的规矩收录 T3 原文，附 `✅**已完成**（完成：2026-11-13 16:00）` 与三项完成说明。
- **回归检查**：① T1 / T2 两条活跃待办正文零改动；② 编号体系不变，T3 不复用；③ 版本号不动（文档类改动，不触发 bump / 发版）。

### 变更（测试定义权并入本项目：Hopper 从团队除名，2026-11-13）

- **为什么改**：用户 2026-11-13 决定把 Hopper（TestEngineerAgent）从团队除名，理由是开发工作流已经变成「Leader 给 Worker 出题」——由本项目在子项目 worktree 里先行写出测试、Worker 全程不改测试，就能达成同样的测试开发分离效果，独立的测试 agent 不再必要。同时明确：**只有 dev-agent 的子项目需要严格的测试开发分离范式与回归防护网**，其它 agent 的项目不涉及复杂软件开发，不需要这套范式。
- **改了什么**：① `AGENTS.md` 新增「测试与回归防护网」节——适用范围只覆盖本项目子项目；出题动线六条（时机固定在实现开工前 / 只写对外可观察行为 / 先红后绿 / 本地 commit 锁定 / Worker 只读可运行 / 必须挂 CI required check）；② 新建 `TODO.md`，承接 Hopper 交接的未完成待办（T1 防护网缺口、T2 子项目硬约束落地）与遗留清理（T3）；Hopper 其余 8 条在交接时已逐条核实闭环（Issue 全 CLOSED、代码已在 main）；③ 双语 README 的职责段与团队位置表同步。
- **回归检查**：① Leader / Worker 分工、worktree 命名、git 纪律等既有规则一字未动；② 新增测试约束只写在 `AGENTS.md`（只对 Leader 会话生效），Worker 侧约束按 `TODO.md` 的 T2 另行写进各子项目 `.pi/APPEND_SYSTEM.md`，不在本次范围；③ 版本号不动（文档与规则类改动，不触发 bump / 发版）；④ 中英双语 README 同轮同步。

### 变更（项目更名 FullStackEngineerAgent → dev-agent，2026-11-10）

- **为什么改**：用户要求把本项目名称改为 `dev-agent`，并同步全团队所有关联内容。团队 Agent 项目命名规则是「一律 `<职责>-agent` 全小写、连字符」（本 Agent 职责为全栈开发 → `dev-agent`），旧名 `FullStackEngineerAgent` 是帕斯卡式长名，与规则不符；`Atlas` 是人格名（人名风格），与项目名属两个层面，保持不变。
- **改了什么**：① GitHub 仓库 `xhqing/FullStackEngineerAgent` → `xhqing/dev-agent`（GitHub 自动重定向旧地址）、本地目录 `~/Developer/FullStackEngineerAgent` → `~/Developer/dev-agent`、`origin` 远端地址同步更新；② 双语 README 标题、图片 alt、正文称呼与底部署名链接改为 `dev-agent`；③ `AGENTS.md` 标题、Leader 会话 cwd 路径、worktree 命名反例同步改为 `dev-agent`；④ `assets/logo.svg` 文字改为 `dev-agent`（主标题字号 32 → 64、副标题 17 → 16，以适配新名字长度并过文字边界校验）、`assets/logo.png` 按同工艺重新渲染；⑤ 全局注册表、全局规则与技能文档、9 个子项目仓库的负责项目名引用、兄弟 agent README、xhqing 主页名册同步更新（各自仓库内提交）。
- **回归检查**：① 人格名 `Atlas` 一字未动——README「Atlas 是谁 / Who is Atlas」身份段、AGENTS.md「你是谁」角色段全部保留，只改项目名；② 历史 CHANGELOG 条目中的旧项目名保留不改写（历史事实）；③ 版本号不动（纯改名杂事，不触发 bump / 发版）；④ `assets/logo.svg` 过 `icon-design` 的文字边界硬校验（PASS）；⑤ 子项目清单与在手项目内容未改动。

### 变更（子项目 worktree 目录命名：必须以子项目名开头，2026-11-09）

- **为什么改**：用户发现 `~/Developer/FullStackEngineerAgent-turn-diff` 这种目录名看不出归属——它实际是 FullStackEngineerAgent 主仓库的分支，名字却像 turn-diff 子项目的 worktree。用户原话：「子项目的 worktree 名字禁止使用『agent 项目或者其它项目名字 + 子项目名字』的命名方式，这样我看不出来到底是哪一个项目的 worktree」。
- **改了什么**：`AGENTS.md` 的 Leader 分工第②步补上命名约束——worktree 目录名写成 `<子项目>-<事项>`，第一个项目名必须是子项目本身，禁止 `FullStackEngineerAgent-<子项目>` / `Atlas-<子项目>` 这类拼法，事项 slug 也不许恰好等于另一个子项目名。全局 `~/.pi/agent/AGENTS.md` 同步立规，并用扩展 `worktree-name-guard.ts` 工具强制（拦截违反命名的 `git worktree add` / `git worktree move`）。
- **回归检查**：① 只改规则文字，不涉及代码与运行行为；② 版本号不动（文档类改动，不触发 bump / 发版）；③ 「Leader / Worker 分工」其余规则一字未动；④ 判据与全局规则一致——名字前缀必须是本仓库（子项目）名，事项 slug 不许撞另一个项目名。

### 变更（README 顶部 LOGO 改走 markdown 图片语法 + PNG，修 VSCode 预览里不显示，2026-11-09）

- **为什么改**：用户反馈改到 r16 版本，VSCode 内置 Markdown 预览里只有徽章（shields.io 远程 SVG）能显示，顶部 LOGO 始终是破图（只剩 alt 文字和问号图标）。查 VSCode 1.145 内置 markdown 扩展的打包代码后定位到根因：预览只对 **markdown 语法的图片** `![]()` 重写 `src`（`renderer.rules.image` 里调 `asWebviewUri` 换成 webview 资源 URI），对**原生 HTML `<img src="...">` 是原样输出**（`html_block` / `html_inline` 直接 `return content`），只能靠 `<base href>` 去凑；原来的 LOGO 正是本地 `assets/logo.svg` + HTML `<img>`，走的就是这条没被重写的通道。徽章是 markdown 语法 + 远程 https 绝对地址，两个条件都踩对，所以只有它显出来了。
- **改了什么**：
  - 新增 `assets/logo.png`（640×200，由 `assets/logo.svg` 用 Chrome 无头模式按 2 倍分辨率渲染后再降采样，保留彩色 emoji 与渐变圆角）；`assets/logo.svg` 原样保留，作为可再编辑的源文件。
  - `README.md` / `README_cn.md` 顶部：`<img src="assets/logo.svg" width="640">` 改为 markdown 图片语法 `![FullStackEngineerAgent](assets/logo.png)`；外层 `<div align="center">` 保留，但用空行隔开，让图片走 markdown 解析、不被 HTML 块吞掉。
  - 出图尺寸按 640 宽：VSCode 预览样式表（`media/markdown.css`）里没有 `img { max-width: 100% }`，宽图会横向溢出出滚动条，所以 PNG 直接按展示尺寸出。
- **回归检查**：① 只改文档与图片资源，不涉及代码与运行行为；② 中英双语 README 同轮同步；③ 版本号不动（纯文档改动，不触发 bump / 发版）；④ 徽章区与正文其余内容一字未动；⑤ 用 markdown_it 实渲染复核，输出结构为 `<div align="center"><p><img src="assets/logo.png" …></p></div>`，可确认图片是 markdown 图片 token（会走 VSCode 的 src 重写通道），居中效果不变。

### 变更（本项目与子项目的 `AGENTS.md`、`.pi/` 改为完全独立，2026-11-08）

- **为什么改**：用户 2026-11-08 决定「Agent 项目与其子项目二者的 AGENTS.md（项目规则）和 .pi 目录之间应该完全无关」——各自只放本项目真实需要的规则与工具，这样才能同时满足两边的特异性需求。原做法（子项目挂 `AGENTS.md` 软链接 + `.pi/settings.json` 引用本项目四个资源目录）有两个毛病：跨仓库路径引用是隐式依赖，本项目改名 / 子项目单独 clone / 换机器都会静默失效；而「只允许追加、不许重述」的纪律本身就说明两层混在一起有事。实测本项目 `.pi/` 里四个资源目录根本不存在，8 个子项目引用的全是空目录。
- **改了什么**：重写本项目 `AGENTS.md` 的「子项目」节（节标题改为「与子项目完全独立」），删掉旧的「身份层软链接 + 能力层路径引用 + 只允许追加」三条，改为「两边完全独立」的四条（子项目那边怎么做 / 本项目这边怎么做 / 为什么 / 安全网不受影响）；顶部注释同步；「子项目文档」那条改为「子项目不再靠软链接读取本项目规则」。8 个子项目仓库侧同步做了实体 `AGENTS.md` + 删 `.pi/settings.json` 交叉引用（各自的 PR 在本仓库之外）。
- **顺带修正**：子项目清单里 turn-diff 的说明原写「cmux 面板能力已移除」，与实现不符——`turn-diff` v2.2.0 仍有 `view` / `render` 两个动词把改动交给 cmux 面板（`cmux diff` / `cmux open`），已改正。

### 新增（CI 门禁：validate 检查 + main 分支 strict 保护）

- **为什么改**：用户 2026-11-03 立规「新建仓库一律必须 strict 模式的 PR CI」，并要求 28 个不合规的存量仓库统一执行最新标准。本项目此前在 PR 上没有门禁——改动合进 main 全靠人工把关，PR 可以拿旧 main 上通过的检查直接合并，回归防护存在缺口。本次补齐团队要求的「三件套」：PR 上真实跑的 CI 检查 + 挂成 required status check + `required_status_checks.strict = true`。
- **改了什么**（2026-11-03）：新增 `.github/workflows/validate.yml`（PR 与 main push 触发，检查名 `validate`）与 `.github/scripts/validate.py`（仓库卫生检查：必备文件存在、敏感文件未被跟踪、被跟踪文件不超过 10 MB、README 相对链接有效、Python / Shell 语法检查）；main 分支保护补挂 required check `validate` 并设 `strict=true`。
- **边界**：检查只做确定性、低误报的项目（required check 一旦误报就会卡住正常 PR，所以宁可少查）；不改动仓库任何原有内容。

## [未发布]

### 变更（版权声明写入个人署名 `xhqing` + 主页 URI，本仓库对 commit skill 第 9g 步归一规则取例外）

- **为什么改**：用户 2026-11-08 要求「自己的名字出现在版权声明中」，让作品被使用时能追溯到本人。原写法 `Copyright (c) 2026 All Contributors` 有两层缺陷：其一，`All Contributors` 是集合概念，不构成《最高人民法院关于审理著作权民事纠纷案件适用法律若干问题的解释》（法释〔2002〕31 号）第七条所称「署名的自然人、法人或者其他组织」，无法据此享受「署名即视为权利人」的举证便利；其二，该行不含任何可追溯标识，第三方看到后无从定位到具体作者。
- **改了什么**（2026-11-08）：
  - `LICENSE.md` 版权行：`Copyright (c) 2026 All Contributors` → `Copyright (c) 2026 xhqing <https://github.com/xhqing>`。主体在前（自然人，落得进司法解释七条的推定范围）、URI 在尖括号内（可追溯标识，指认该 GitHub 账号即本人）。
  - `README.md` / `README_cn.md`：授权段的版权行与「使用方引用示例」同步改为 `xhqing`。
  - **不写 `and contributors`**：用户 2026-11-08 明确「目前也没想过要接受 contributor」。版权声明反映事实、不预留位置；日后若接收他人的实质贡献，再同步补为 `xhqing and contributors` 或另立 CLA。
  - `.commit-cache.md` 的 `attribution-name` 标记说明改写——由「已归一为 All Contributors」改为「本仓库有意个人署名、不做归一」，并写明依据与边界，确保后续 `/commit` 不会被 commit skill 第 9g 步静默回改。
- **回归检查**：① 不涉及代码与运行行为；② 双语 README 同轮同步（版权行、示例署名两处）；③ 版本号不动（文档类改动，不触发 bump / 发版）；④ MIT 的授权条款正文一字未动——只改 `the above copyright notice` 的具体持有人，不影响授权范围；⑤ `LICENSE.md` 徽章与许可证类型仍为 MIT，与「本项目是软件项目」的定性一致。
- **与全局规则的冲突及处理（如实记录）**：commit skill 第 9g 步要求「README / README_cn / LICENSE 三份文件的版权人统一 `All Contributors`，不出现具体个人名」。本次通过 `.commit-cache.md` 的缓存标记**显式豁免**并记录理由，属有记录的例外、非静默绕过。遗留问题：9g 这条规则本身与上述司法解释的口径不一致（强制所有项目使用无法落到法律主体的集合式版权人），本仓库的例外只解决单点；全队其余 37 个仓库仍为 `All Contributors`，是否修订规则并统一全队属需单独评估的事项，本次未擅自批量改动。

### 变更（评估 CC BY 4.0 后保持 MIT——本项目是软件项目；署名条款消除「要求」与「请」的自相矛盾）

- **为什么改**：用户 2026-11-08 提出 5 项署名诉求（权利来源不被抹掉、出纠纷能证明是自己写的、被使用时能被知道、借作品引流攒声誉、希望转载者注明出处），并要求评估现有 MIT + `All Contributors` 是否够用。评估过程中曾一度改为 CC BY 4.0，理由是「仓库主体是 Markdown、MIT 的授权对象是 software、两者对不上」。但用户随后提出关键反驳并成立：**本项目的 Markdown 不是给人读的文档，是给 LLM 读的程序逻辑**——`AGENTS.md` 定义 agent 的身份、职责与行为边界，`.pi/` 下是配置、技能与扩展，删掉或改写它们会直接改变程序行为。据此本项目的产物具备软件的「功能性」本质（产生技术效果而非审美表达），MIT 原文 `this software and associated documentation files` 完全覆盖（`AGENTS.md` 本身是 software，README 是 associated documentation）。因此撤销换许可证的决定，两条理由：① 「对象错位」这个前提不成立；② Creative Commons 官方明确**不建议**将 CC 许可证用于软件（CC 许可不含专利授权条款、无源码分发要求、与现有软件许可证组合时兼容性复杂），拿 CC BY 4.0 覆盖一个软件项目的核心文件违背其官方指引。
- **改了什么**（2026-11-08）：
  - `README.md` / `README_cn.md`：「License & Attribution」/「许可与署名」节重写——一句话讲清 MIT 的唯一条件（分发副本或实质性部分时须携带版权声明与许可证全文），并明说除此之外不要求通知、不要求在界面致谢、不要求取得许可；原署名请求改为明确标注「只是请求、不是义务」的礼节性提及。修掉的病根是旧文案「标题写『署名要求』、正文写『请保留……』」——这两个词在法律上是相反的意思，属自相矛盾，且会让读者误以为存在无法执行的义务。
  - `LICENSE.md`、License 徽章、版权人写法（`All Contributors`）均维持不变——与全队其它 37 个仓库及 commit skill 第 9g 步的归一口径一致。
- **回归检查**：① 无代码逻辑与运行行为变更，纯 README 文本调整，不影响 `AGENTS.md` 的规则效力与任何子项目；② 双语 README 同轮同步（信息点、口径一致）；③ 版本号不动——文档类改动，不触发 bump / 发版；④ `.commit-cache.md` 的 `license` / `attribution-name` 标记与实际状态一致，无需改写。
- **遗留说明（如实记录）**：诉求「转载者必须注明出处」在 MIT 与任何 OSI 认证的软件许可证下都拿不到强制力——这是软件许可证体系的设计（可强制的是「保留声明」，不是「展示署名」），不是用错许可证。要强制署名只能改用 CC BY 4.0 这类文字作品许可证，但那与「本项目是软件项目」的定性冲突。当前取舍：**定性优先（保持软件定性 + 全队一致），署名请求以礼节形式表达、不具强制力**。诉求「能证明是我写的」由公开发布时间戳（commit / tag，推送后不可伪造）与可选的著作权登记承担，不依赖版权声明行——这本来也不该由许可证解决。


### 变更（项目规则文件本体统一改为 `AGENTS.md`，`CLAUDE.md` 弃用，2026-11-05）

- **为什么改**：用户 2026-11-05 立规「所有注册表项目与全局的规则文件本体统一用 `AGENTS.md`，`CLAUDE.md` 弃用」。pi 的上下文文件候选顺序是 `AGENTS.override.md` > `AGENTS.md` > `CLAUDE.md`（同一目录只加载第一个存在的），本体放在 `AGENTS.md` 后 `CLAUDE.md` 根本不参与加载——两份并存只会形成双份内容、随时漂移。
- **改了什么**：项目根 `CLAUDE.md` 改名为 `AGENTS.md`（实体本体，原先的 `AGENTS.md → CLAUDE.md` 软链接已删除）；项目内引用「项目 `CLAUDE.md` / 全局 `CLAUDE.md`」的条文、skill、hook、脚本与 README 同步改为 `AGENTS.md`。
- **回归检查**：加载顺序不受影响（`AGENTS.md` 本就排在 `CLAUDE.md` 之前）；子项目根目录的 `AGENTS.md` 软链接仍指向本项目 `AGENTS.md`，目标不变、照常解析。

### 变更（移除访问量徽章，配合停用集中式流量采集）

- **为什么改**：用户 2026-11-04 决定停用 xhqing 仓库的集中式访问量采集，同时不再在各仓库 README 展示访问量徽章。徽章的数据源必须由采集任务每天刷新，采集停掉之后徽章会冻结在旧值，而徽章文案写的是「Visits/day (14d)」——数字不再更新却仍显示成实时数据，留着反而误导读者。
- **改了什么**：`README.md` / `README_cn.md` 顶部徽章区删除那一枚 shields.io 访问量徽章（整行删除，数据源 `https://raw.githubusercontent.com/xhqing/xhqing/main/traffic/badges/<仓库名>.json`）；License / Version / Type 等其它徽章与正文一个字未动。
- **回归检查**：只删这一整行，徽章区所在的 `<p align="center">` / `<div>` 结构与相邻徽章不受影响；README 其余内容零改动。

### 变更

- **子项目「Agent 进驻」改为「`AGENTS.md` 软链接 + 真实 `.pi/` 目录（资源引用）」（2026-10-30 用户修订）**。为什么改：用户 2026-10-30 修订全局规则——旧版把子项目 `.pi` 整个软链接到本项目的 `.pi`，等于把「共享」与「独占」压在同一个符号上：子项目往 `.pi` 写任何东西都会直接落进本项目（污染全部兄弟子项目、并进本仓库 git 历史），而 `AGENTS.md` 没有 include 机制、用复制做超集必然漂移。改了什么：①`CLAUDE.md`「子项目」节改写为 2026-10-30 版（身份层 `AGENTS.md` 软链接保持一致；能力层为各子项目自己真实的 `.pi/` 目录，内用 `settings.json` 按路径引用本项目四个资源目录；写明「子项目 `.pi` 只允许追加、不得重述基座规则，专属规则用 `APPEND_SYSTEM.md` 不用 `SYSTEM.md`」）；②本项目名下 6 个子项目（codef / ghostty-launcher / ghostty / mp4-player / pi-harness / XPilot）的 `.pi` 软链接就地换成真实目录 + `settings.json`，`AGENTS.md` 软链接维持不变（本地挂载与各子项目仓库提交在本会话完成，各子项目 CHANGELOG 分记）。验证：在临时探针项目里用同一份 `settings.json` 形式引用 `~/Developer/ExecutiveAssistantAgent/.pi/skills` 并放一个本地点探 skill，`pi --approve -p` 一次性列出外部引用与本地的 18 个技能（机制生效）；在 codef 目录 `pi --approve -p` 回答身份为 Atlas、未报路径错误。备注：本项目 `.pi/` 仍是空目录（只有 `.gitkeep`），四个被引用的资源目录尚不存在，pi 对不存在的资源路径不报错（已实测；以后新增资源放入即自动生效，无需改子项目）。

- **双语 README「在手项目」段对齐为六项（`pi` → `pi-harness`、补入 XPilot，2026-10-26）**。为什么改：接手 XPilot 后自查发现 README 与 `CLAUDE.md` 已不一致——README 仍写五项、`pi` 也未随 2026-10-23 的目录改名更新为 `pi-harness`（当时只改了 CLAUDE.md 与注册表），对外说明与实际维护范围对不上。改了什么：`README.md` / `README_cn.md` 第 29 段同步——标题列举改为六项，`pi` 改称 `pi-harness`，新增 XPilot 一句话说明（xray 后端的 CLI 代理工具箱、开发目录 `~/Developer/XPilot`、2026-10-26 由已注销的 NetOpsAgent 项目移交、从 GitHub Release 的 wheel 安装），结尾「五者」改「六者」。

- **XPilot 子项目移交至 Atlas（2026-10-26 团队结构调整）**。为什么改：用户 2026-10-26 注销 Hermes（NetOpsAgent）这个 Agent，其名下唯一子项目 XPilot 移交本项目负责，全局 `~/.pi/agent/docs/agents-registry.md` 已先行改完，本项目文件须与之保持一致。改了什么：`CLAUDE.md`「当前子项目清单」补入 `XPilot（~/Developer/XPilot，2026-10-26 由已注销的 NetOpsAgent / Hermes 移交）`；XPilot 仓库根目录两条身份软链接的指向由 `../NetOpsAgent/` 改为 `../FullStackEngineerAgent/`（该仓库侧改动记其自己的 CHANGELOG）。

- **pi 子项目本地目录改名 pi-harness（2026-10-23）**。为什么改：GitHub 仓库已于 2026-10-18 改名为 `xhqing/pi-harness`，本地开发目录仍是 `~/Developer/pi`，与仓库名不一致、也容易与上游 `earendil-works/pi` 混淆。改了什么：①`~/Developer/pi` → `~/Developer/pi-harness`；②`CLAUDE.md`「当前子项目清单」同步更新为 `pi-harness（~/Developer/pi-harness）`；③全局注册表的 pi 侧权威副本与 `.claude` 遗留副本的子项目行同步为 `pi-harness`（CapabilityManagerAgent 的 `pi/agent` 镜像及其 CHANGELOG 另记）；④`~/.pi/agent/trust.json` 的旧项目路径替换为新路径。另：本机全局 pi 由 0.0.6 升级到 0.0.7（安装路径变为 `node_modules/pi-coding-agent`，「Update Available」提示里的 Changelog 链接随之指向 `xhqing/pi-harness`）。

- **文档路径口径更新（2026-10-17）：全局权威源迁至 `~/.pi/agent/`**。为什么改：2026-10-17 全局规则 / 技能 / 文档的权威源迁至 `~/.pi/agent/`（旧 `~/.claude/` 为遗留副本、勿再修改；仅 CC 侧 hooks 原位保留）。改了什么：CLAUDE.md 4 处引用更新——`~/.claude/CLAUDE.md`（通用工作规则 / 通用工作纪律 2 处）、`~/.claude/`（通用能力来源）、`~/.claude/docs/agents-registry.md`（子项目映射权威）→ 均改为 `~/.pi/agent/...`。登记与镜像口径同步记 CapabilityManagerAgent 侧。

- **channels-watch 退役（2026-10-17 用户决定）**。为什么改：用户决定 channels-watch 不再维护——本地卫生处理、删除本地项目文件、注册表移除；本项目文件须与注册表保持一致。改了什么：①「目前在手项目」段移除 channels-watch 描述、结尾更新取消/退役说明；②「当前子项目清单」同步移除；③双语 README 在手项目段同步（六者 → 五者，附退役说明）。登记侧与镜像同步记 CapabilityManagerAgent 侧（本地清理与注册表编辑由 Kit 会话执行）。

- **子项目「Agent 进驻」软链接网络落地（2026-10-17 用户修订）**。为什么改：用户 2026-10-17 修订智能体专属文件规则——实体（`CLAUDE.md` / `AGENTS.md` / `.claude/` / 项目级 `.pi/`）只属 Agent 项目，子项目改挂两条指回负责 Agent 的软链接（在子项目目录开会话即继承负责 Agent 身份 / 规则 / 技能）；详见全局 `~/.claude/docs/agents-registry.md`「智能体专属文件归属与子项目映射（2026-10-17 修订）」。改了什么：①新增 `AGENTS.md → CLAUDE.md` 软链接（pi 侧上下文别名）；②新增 `.pi/`（含 `.gitkeep`）供子项目软链接挂载；③`CLAUDE.md`「子项目」节更新为 2026-10-17 版（两条软链接随仓库提交、后台会话仍限 Agent 项目根目录、`.claude/` 不纳入）；④本 Agent 名下 5 个子项目（ghostty-launcher / codef / pi / ghostty / mp4-player）各挂 `AGENTS.md`、`.pi` 两条软链接并随仓库提交（各子项目 CHANGELOG 分记，本地挂载由 Kit 会话执行）。

## [0.1.4] - 2026-10-14

### 变更

- **取消三个子项目（zcode-cli、zcode-vsce、cmux-launcher；2026-10-14 用户决定）**。为什么改：用户 2026-10-14 决定不再维护这三个项目；全局注册表已将其列入「已取消的子项目」（本地项目资料删除、GitHub 远端仓库保留为存档），本项目文件须与注册表保持一致。改了什么：①「目前在手项目」段移除三个项目的描述、结尾改为取消说明；②「当前子项目清单」同步移除；③双语 README 在手项目段同步（九者 → 六者，附取消说明）。登记侧与镜像同步记 CapabilityManagerAgent 侧。

### 变更

- **codefs 更名回退 codef（用户 2026-10-13 决定）**。为什么改：用户明确——项目与命令保持 `codef` 命名、命令不要改名（「把项目名字改成 codefs」的本意不包括命令，更名扩大化了）；命令共三个：`codef` / `codef left` / `codef --version`（仅新增 `--version` 属预期）。改了什么：①「目前在手项目」与「当前子项目清单」两处名称 / 路径回退（`~/Developer/codefs` → `~/Developer/codef`）；②双语 README 在手项目段同步回退；③全局注册表映射表与分支保护清单回退（镜像同步记 CapabilityManagerAgent 侧）；codefs 仓库侧的回退与 0.4.1 发版见该仓库 CHANGELOG。

### 变更

- **codef 项目更名 codefs（2026-10-13 用户决定）**。为什么改：用户要求把 codef 项目（命令 / 脚本 / GitHub 仓库 / 本地开发目录）统一更名 codefs，本项目权威源与登记需随更。改了什么：①「目前在手项目」与「当前子项目清单」两处的名称 / 路径更新（`~/Developer/codef` → `~/Developer/codefs`）；②双语 README 在手项目段同步；③全局注册表映射表 Atlas → codefs 行更新（镜像同步记 CapabilityManagerAgent 侧）；codefs 仓库自身的改名与 `--version` 新增见该仓库 CHANGELOG v0.4.0。

### 变更

- **迁移项目指南到 `DEVELOPMENT.md`，删除智能体专属文件**（2026-10-12 新规）：`CLAUDE.md` / `AGENTS.md` / `.claude/` / `.pi/` 等智能体专属文件不再保留；有价值内容（项目指南 / 上游开发规则等）已迁入普通文档。


### 变更

- **子项目规则更新：子项目不再携带智能体专属文件（2026-10-12 用户修订）**。为什么改：用户修订全局规则——`CLAUDE.md` / `AGENTS.md` / `.claude/` / 项目级 `.pi/` 等智能体专属文件只有 Agent 项目允许拥有，非 Agent 项目（含子项目）一律不得存在；后台开启 pi 会话只能以 Agent 项目根目录为工作目录。改了什么：①本项目 CLAUDE.md「子项目」节改写为新规表述（清单、跨目录工作方式、文档落点；原「子项目 `.claude/` 超集」规则废止）；②清理全部 7 个子项目的智能体专属文件，有价值内容迁入各自普通文档 `DEVELOPMENT.md`（zcode-vsce / ghostty-launcher / codef / channels-watch / mp4-player 的项目指南；pi 的项目指南 + 上游 Development Rules + 原 `.pi/skills` 两份文档；ghostty 的上游开发指南），pi 的 `.pi/` 开发辅助扩展与 prompts 随删（git 历史可回溯）；③全局注册表映射表与全局 CLAUDE.md 由 Kit 侧更新。

## [0.1.3] - 2026-10-09

### 变更

- **子项目状态登记：zcode-cli 与 cmux-launcher 短期搁置（2026-10-09）**。为什么改：用户决定这两个项目短期不再维护——cmux-launcher 的本地开发目录已归档（`~/Documents/Projects-archive/cmux-launcher-2026-10-09.tar.gz`）后删除，zcode-cli 本地目录亦已删除（远端仓库与其流水线保持现状、不做处理；bump PR 与每日失败任务按用户口径搁置不动）。改了什么：①权威源「目前在手项目」与「当前子项目清单」两处标注「zcode-cli、cmux-launcher 自 2026-10-09 起短期搁置」；②七个既存子项目随附版同步最新全文（zcode-vsce、ghostty-launcher、pi、ghostty、codef、channels-watch、mp4-player——zcode-cli 与 cmux-launcher 本地目录已删除、无随附版可同步）；③全局注册表映射表两行加搁置标注（镜像同步记为 CapabilityManagerAgent 侧）；④cmux-launcher 的未完成项按 TODO 纪律归档：T1（开源到 GitHub）标 `✅已放弃` + 理由，归档副本内新增 `TODO-archive.md`、`CHANGELOG.md` 记搁置条目并重打包（同一归档路径）；⑤双语 README 的公开介绍不改（项目归属未变，仅在内部权威源标注状态）。

## [0.1.2] - 2026-10-09

### 新增

- **mp4-player 纳入子项目（`~/Developer/mp4-player`）**。为什么改：用户 2026-10-09 指示把 mp4-player（VSCode 视频播放扩展，上游 Brodazz/mp4-player 的独立仓库；仓库基建——main 分支保护 + CI + auto-merge——已于同日完成）登记为 Atlas 子项目并补齐三件套（权威源 / 随附版 / 全局注册表）。改了什么：①权威源「目前在手项目」与「当前子项目清单」加入 mp4-player（含开发目录与「从 GitHub Release 的 vsix 安装」说明）；②其余 8 个子项目（zcode-cli、zcode-vsce、ghostty-launcher、cmux-launcher、pi、ghostty、codef、channels-watch）随附版同步到最新全文，mp4-player 自身随附版（项目指南 + Atlas 全文，`AGENTS.md` 软链）经核对与权威源逐字节一致；③全局注册表映射表加 Atlas → mp4-player 行（镜像同步与 CapabilityManagerAgent 侧记录由 Prometheus 处理）；④双语 README 在手项目段加入 mp4-player（维护项目数「八者」改为「九者」）。

## [0.1.1] - 2026-10-09

### 新增

- **channels-watch 纳入子项目（`~/Developer/channels-watch`），并完成生产/开发隔离部署**。为什么改：用户 2026-10-09 指示把视频号私信只读监控工具 channels-watch 立项开源（仓库 `xhqing/channels-watch`，v0.1.0 已发布）并移交 Atlas 负责，需完成侧登记（权威源 / 随附版 / 双语 README）与接手首事（生产/开发隔离改造，见该仓库 `TODO.md` T1）。改了什么：①权威源「目前在手项目」与「当前子项目清单」加入 channels-watch（含开发目录与生产部署路径说明）；②八个子项目（zcode-cli、zcode-vsce、ghostty-launcher、cmux-launcher、pi、ghostty、codef、channels-watch）随附版同步到最新全文（顺手修正 zcode-cli、zcode-vsce、ghostty-launcher 三份随附版旧快照的漂移——清单版本落后、句读与权威源不一致）；③双语 README 在手项目段加入 channels-watch，并补上此前遗漏的 codef（codef 纳入时 README 未同步，本次一并修正，「六者」改为「八者」）；④生产部署：从 v0.1.0 Release 归档把 `watch.py` 安装到 `~/.local/share/channels-watch/`（与开发目录逐字节一致），launchd 改指生产副本，运行时数据（`config.json` / `state.json` / `profile/` / `logs/`）迁移至生产目录（登录态与去重状态延续、无重复推送），部署后首轮运行验证正常；⑤该仓库侧同步更新 plist 模板与双语 README 部署说明、补 CHANGELOG 条目、T1 归档（详见该仓库 CHANGELOG）。

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
