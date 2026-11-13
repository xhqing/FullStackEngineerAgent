# TODO（dev-agent · Atlas · 全栈开发工程师）

> 活跃待办清单。条目按紧急度分节，节内按记录时间排序。处理完毕移入 `TODO-archive.md`。
> 个人隐私类待办写 `TODO.local.md`（不入 git），编号与公开版共用同一套空间。
>
> 本文件于 2026-11-13 建立：Hopper（TestEngineerAgent）当天从团队除名，其未完成待办按用户指令全部交接给本项目（其余 8 条在交接时已核实闭环，见 `~/.pi/agent/docs/agents-registry.md` 的除名记录）。

## 🟠 橙色紧急度

- [ ] **T1** 把回归防护网补到 dev-agent 的每个子项目：逐个实测「有没有跑测试的 required check」，缺口补齐（记录：2026-11-13 15:44）
  **背景**：Hopper 除名后测试职责归本项目，但真实缺口比「谁出题」大得多——**没进门禁的测试等于没写**。2026-11-13 交接时核实的现状：
  - ✅ **pi-harness**：全量测试 + 类型检查跑在 `build-check-test`，是 main 的 required check。
  - ✅ **ghostty-launcher**：`node --test` 测试套件 + CI 门禁（Issue #1 时建的）。
  - ✅ **codef**：CI 跑 shellcheck / AppleScript 语法 / 回归守卫 / 版本一致性 / 错误路径测试。
  - ✅ **XPilot**：pytest 全量 + 关键静态检查，CI 执行。
  - ❌ **cmux**：`cmuxTests/` 有真实测试（含 `EmptyWindowStateTests.swift`），但 PR 门禁 `checks` 只做四项轻量检查（Swift `swiftc -parse` / 配置 schema / 测试接线 / gitleaks），**一条测试都不跑**——写入的用例只在有 Xcode 的机器上手工跑。
  - ❌ **turn-diff**：没有测试目录，没有任何测试。
  - ❓ **mp4-player**：待摸底（VSCode 扩展项目，需确认有无测试框架与 CI）。
  - ❓ **ghostty**：分叉的 Zig 终端项目，有 CI 但测试覆盖待摸底。
  **要做什么**：
  ① 先把上面「❓」两项实测定案（框架有无 / CI 跑不跑测试 / 是否 required），把结论写回本条。
  ② **cmux 加一条跑测试的 required step**：必须遵守它的硬约束（`.pi/APPEND_SYSTEM.md`：不能把完整构建塞进 PR 门禁，`build-macos` 实测 2~4 小时）——目标是**只跑 `cmuxTests` 的轻量 step**（实测耗时后再定超时），不是编译整个 app；改门禁时不能改 `checks` 这个 job 名（分支保护的必过检查认这个名字）。
  ③ **turn-diff 建首批测试**：按它的技术栈（pi 扩展 + 命令行 / TypeScript）选 vitest，先覆盖「本轮 diff 计算」这条核心逻辑（纯 git 逻辑、可脱离 UI 断言），再把测试挂进 CI required check。
  ④ mp4-player / ghostty 按摸底结论决定要不要补，缺的照 ②③ 的形态补。
  **边界**：一项目一个 worktree + PR（不要跨仓库一把梭）；cmux 的门禁改动先实测耗时再上线，别凭印象写超时。

- [ ] **T2** 把「Worker 不得改测试」的硬约束写进各子项目的 `.pi/APPEND_SYSTEM.md`（记录：2026-11-13 15:44）
  **背景**：Worker 会话只加载**自己子项目**的 `.pi/APPEND_SYSTEM.md`（pi 不向上继承项目配置），而 `dev-agent` 的 `AGENTS.md` 只在 Leader 会话里加载。所以「测试只读 + 可运行」「碰到测试问题终止上报」这两条如果不写进子项目，Worker 根本看不到，规则就空转——它会照常顺手改测试来适配实现。
  **要做什么**：给 8 个活跃子项目（ghostty-launcher、pi-harness、ghostty、cmux、turn-diff、codef、mp4-player、XPilot）的 `.pi/APPEND_SYSTEM.md` 各加一节，写清三件事：① 测试文件（测试目录、`*.test.*` / `*.spec.*` / `test_*.py` / `conftest.py` 等）对 Worker **只读 + 可运行**，新建 / 修改 / 删除 / 移动一律禁止；② 碰到测试跑不通或断言与 Issue 预期不符 → 终止开发、上报 Leader（`Atlas`）或用户裁决，不得自行改测试迁就实现；③ 测试的写入权在 Leader 出题这一步（带 `# TEST_CASES_WRITE_OK`），Worker 不得自行加标记。
  **边界**：逐子项目建 worktree + PR；文案按各项目已有风格写，不复制整段 dev-agent 规则。

## 🟡 黄色紧急度

- [ ] **T3** 清理 Hopper 遗留的 `cases/` 存量并给 TestEngineerAgent 仓库收尾（记录：2026-11-13 15:44）
  **背景**：原 Hopper 的 T3 交接过来。`~/Developer/TestEngineerAgent/cases/zcode-cli/pending/` 下还压着两组未完成需求（`custom-env-rename`、`model-picker-env-prefix`，各含 `requirement.md` + 一份 `.test.ts`），而 zcode-cli 项目已于 2026-10-14 取消——这两组需求不再做。各子项目的 `test-cases/` 旧目录已核查为 0 个（无需迁移）。
  **要做什么**：① 确认两组旧需求不再做（zcode-cli 已取消即定案），删掉本项目 `cases/` 目录；② TestEngineerAgent 仓库加退役说明（双语 README 顶部一句「已于 2026-11-13 从团队除名，测试职责并入 dev-agent，仓库保留为存档」+ `AGENTS.md` 同口径 + CHANGELOG 一条），避免公开读者误以为它还在服务团队；③ 该仓库 `TODO.md` 的活跃条目全部归档（标「已完成」或「已转移至 dev-agent」）。
  **边界**：TestEngineerAgent 的改动走它自己的仓库 PR；归档条目正文一字不改，只加状态标记。