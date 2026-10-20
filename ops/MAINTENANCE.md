# 低维护承诺 — hotel-procurement-radar

> **原则**：建议 **每月最多 1 次** 主动维护。文档与 Skill 行为以「能核价、能说清结果落哪」为底线，不做花式重构。  
> **文档版本**：ops docs v0.1 · 2026-10-20（Asia/Shanghai）  
> **红线**：GitHub 推送/开 PR/改远端 **须晁总批准**；日常只改 box 或本地草稿。

---

## 1. 维护节奏

| 频率 | 做什么 | 不做 |
|------|--------|------|
| 每月 ≤1 次 | 抽测触发词；核对 Base 字段是否仍对齐；必要时改 ops 文档或记 changelog | 无故障时不改 Skill 大逻辑 |
| 有故障时 | 按 [`OPS.md`](./OPS.md) §8 排障；修配置/权限/表结构 | 不把密钥写进公开仓 |
| 有产品变更时 | 同步 `SKILL.md` 与本目录；更新 [`CHANGELOG.md`](./CHANGELOG.md) | 不同时大改 README 文案与数据源矩阵（拆次） |

---

## 2. 改什么 / 不改什么

### 建议改（低成本、高收益）

- 触发词验收句、故障表、字段名与实测不一致处
- `USER-GUIDE` vs `SKILL` 关于「自动写表」的说明统一（或加「以实测为准」脚注）
- clone 地址统一为 `https://github.com/chaoliuzhu65-tech/hotel-procurement-radar.git`
- 公开 README「运维与部署文档」入口（见仓库根 `README.md` / `GITHUB-README.md`，链到本目录）

### 默认不改

- 19 源矩阵的营销表述与 emoji 状态表（除非某源长期全挂）
- 引导卡片 JSON 视觉样式
- Web vs 本地 MCP 能力边界（自动下单仍仅本地）
- 与本仓无关的市场雷达 / BOLG / 十维文档
- 任何真实 `token` / `secret` / 客户报价 / 私人联系方式

---

## 3. 如何记录 Changelog

1. 在本目录 [`CHANGELOG.md`](./CHANGELOG.md) **顶部**追加一节（日期用 Asia/Shanghai）。
2. 分类建议：`Added` / `Changed` / `Fixed` / `Docs` / `Security`（Security 只写「轮换了本地密钥」，不写密钥内容）。
3. 若变更来自上游仓 `SKILL.md`，注明上游版本或 commit（短 SHA），并写「远端是否已推：否/待批」。
4. 单次维护结束在当次笔记或 [`CHANGELOG.md`](./CHANGELOG.md) 留一行：日期、改了哪些文件、是否建议开 PR（默认否，须晁总批准）。

### 条目模板

```markdown
## [docs-v0.x] - YYYY-MM-DD

### Docs
- …

### Changed
- …

### Notes
- 未推 GitHub；建议开 PR：否（等批）
```

---

## 4. 升级 Skill 的最小步骤

```bash
cd ~/.openclaw/workspace/skills/hotel-procurement-radar
git pull --ff-only origin main
# 重载 Agent skills → 发「查一下大白菜价格」验收
```

升级后若写表失败：先查权限与表是否存在（[`OPS.md`](./OPS.md) §8），再考虑改字段。

---

## 5. 何时打破「每月 1 次」

允许立即动手：
- 全源查价失败超过一个工作日
- Base 写入导致生产表结构损坏或权限大面积失效
- 公开仓出现密钥泄露（立刻轮换本地密钥 + 协调删历史，仍不擅自 push 除非已批）

其余需求进下月窗口或等批准的 PR。

---

*MAINTENANCE.md · 低维护*
