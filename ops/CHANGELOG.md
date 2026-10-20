# Changelog — hotel-procurement-radar 运维文档

本文件记录 **ops 文档与运维约定** 的变更，不等于上游 Skill 功能版本号。  
上游 Skill 版本见仓内 `SKILL.md`（当前公开为 v4.0-open）。  
日期均为 **Asia/Shanghai**。

格式参考 Keep a Changelog；版本号用于 docs 切片（`docs-v0.x`）。

---

## [docs-v0.1] - 2026-10-20

### Added

- 新建可公开低维护运维包 `ops/`（晁总已批准合入本仓）：
  - [`OPS.md`](./OPS.md) — 安装/升级、触发词、数据源容灾、Base 字段、日常检查、排障、已知限制
  - [`MAINTENANCE.md`](./MAINTENANCE.md) — 每月最多 1 次维护承诺；改/不改清单；changelog 写法
  - [`CHECKLIST.md`](./CHECKLIST.md) — 上线 / 周检 / 月度 / 故障快检勾选清单
  - `CHANGELOG.md` — 本文件
- 根目录 `README.md` 与 `GITHUB-README.md` 追加「运维与部署文档」，链接指向 `ops/OPS.md` 等
- 文档起点对齐学习笔记 2026-10-13 §3 与公开仓 `main` 上 `README.md` / `GITHUB-README.md` / `SKILL.md` / `USER-GUIDE.md`

### Docs

- 明示 **USER-GUIDE「导出 🔜」与 SKILL「自动写表」不一致 → 以实测为准**
- 区分 Web 版 vs 本地 MCP（自动下单仅本地）
- 声明非本仓：市场雷达 / BOLG / 十维（如 `delong-ai-radar`）不混入本稿
- Base 仅公开**字段名**；token/secret 仅占位符
- clone 地址统一为 `https://github.com/chaoliuzhu65-tech/hotel-procurement-radar.git`

### Notes

- 草稿元数据（交付回执、README 补丁原稿）不入库
- 晁总已批准发布；本切片随 PR 合入 `main`

---

*CHANGELOG.md · docs 起点 2026-10-20*
