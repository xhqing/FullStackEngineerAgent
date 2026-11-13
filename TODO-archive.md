# TODO 归档（dev-agent · Atlas）

> 本文件归档已处理（已完成 / 已更新 / 已放弃 / 已转移）的待办条目，正文原样保留供回溯；编号不复用。
> 编号空间与 `TODO.md`、`TODO.local.md`、`TODO-archive.local.md` 共用。

## 🟡 黄色紧急度

- [ ] **T3** 清理 Hopper 遗留的 `cases/` 存量并给 TestEngineerAgent 仓库收尾（记录：2026-11-13 15:44）
  **背景**：原 Hopper 的 T3 交接过来。`~/Developer/TestEngineerAgent/cases/zcode-cli/pending/` 下还压着两组未完成需求（`custom-env-rename`、`model-picker-env-prefix`，各含 `requirement.md` + 一份 `.test.ts`），而 zcode-cli 项目已于 2026-10-14 取消——这两组需求不再做。各子项目的 `test-cases/` 旧目录已核查为 0 个（无需迁移）。
  **要做什么**：① 确认两组旧需求不再做（zcode-cli 已取消即定案），删掉本项目 `cases/` 目录；② TestEngineerAgent 仓库加退役说明（双语 README 顶部一句「已于 2026-11-13 从团队除名，测试职责并入 dev-agent，仓库保留为存档」+ `AGENTS.md` 同口径 + CHANGELOG 一条），避免公开读者误以为它还在服务团队；③ 该仓库 `TODO.md` 的活跃条目全部归档（标「已完成」或「已转移至 dev-agent」）。
  **边界**：TestEngineerAgent 的改动走它自己的仓库 PR；归档条目正文一字不改，只加状态标记。

  ✅**已完成**（完成：2026-11-13 16:00）
  **完成说明**：三项全部落地并各自 PR 合并——① `TestEngineerAgent` 仓库的 `cases/` 目录已删除（该仓库 PR #18，仅剩 zcode-cli 两组未完成需求，zcode-cli 已于 2026-10-14 取消）；② 该仓库 `README.md` / `README_cn.md` 标题下加退役说明（双语同步）、`AGENTS.md` 顶部加同口径说明，写明已从团队除名、测试职责并入 dev-agent、仓库保留为存档；③ 该仓库 `TODO.md` 十条活跃条目全量移入其 `TODO-archive.md`（8 条经核实已完成、2 条转移至本项目 `TODO.md` 的 T1 / T3），清单清空。
