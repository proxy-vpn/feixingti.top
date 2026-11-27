# 飞星梯 `feixingti.top` · 内容站 SEO 方案

> 维护方：`proxy-vpn` ｜ 站点：<https://feixingti.top/> ｜ 面板：<https://app.feixingti.top/>
> 技术栈：Hugo 0.147.7 + 共享主题 `brand-docs` + Cloudflare Pages / nginx 静态托管
> 本文件既是仓库首页，也是本站 SEO 策略基线。每次策略调整须同步更新文末「变更记录」。

---

## 一、先校准预期：GitHub 仓库在 SEO 里的真实作用

- GitHub 对 README、Profile、Issue、PR、Wiki、Gist 中的用户生成链接统一注入 `rel="nofollow"`，由 HTML sanitizer 处理，仓库设置无法关闭。2026 年 11 月的独立核查再次确认：`github.com` 域名权重虽高（DA≈92），但**不向本站传递 PageRank**。
- 因此：**README 里的 `https://feixingti.top/` 不会直接涨权重**。
- 本仓库真正的价值是 **E-E-A-T 身份层 + 开发者信任信号**：
  1. 公开、持续更新的提交记录，证明「背后有真实维护者」——这对个人向产品尤其重要；
  2. 教程源文件、配置示例、测速脚本可被开发者 fork / 引用，带来**自然外链**；
  3. 与站点 `/about/` 页互相印证，站点结构化数据用 `sameAs` 指向本仓库，形成闭环。
- 结论：这是**信任资产**，不是外链神器。外链增长靠第三节的渠道组合。

---

## 二、定位与关键词地图

### 2.1 站群分工（本站 = 个人 / 开发者向）

| 站点 | 目标人群 | 搜索意图 | 主战场 |
|---|---|---|---|
| **feixingti.top（本站）** | 个人 / 开发者 / 内容爱好者 | 信息 + 交易 | 客户端教程、AI 工具解锁、流媒体、节点测速 |
| pobiren.top | 跨境电商 / 外贸团队 | 商业调查 + 交易 | IEPL/IPLC 专线、住宅 IP、防关联 |
| kuaifei.top | 团队向 | 商业调查 | 专线 / 出海网络 |
| tkya.us.ci | 第三方评测 | 商业调查 | 品牌对比、评测 |

> 本站关键词以**「怎么做」类信息词**为主，与团队向站点形成意图隔离，避免同集团内耗。

### 2.2 关键词分层

**品牌词（护城河）**
`飞星梯` · `飞星梯官网` · `feixingti` · `app.feixingti.top`

**核心商业词（主战场）**
`Clash 订阅教程` · `Shadowrocket 使用教程` · `V2Ray 订阅导入` · `ChatGPT 解锁` · `Netflix 解锁` · `海外网络 个人` · `性价比 代理`

**长尾信息词（起量主力，KD 低）**
`Clash Verge 怎么导入订阅` · `小火箭 订阅链接怎么用` · `Shadowrocket 节点测速怎么看` · `ChatGPT 网络错误怎么解决` · `Netflix 检测到代理怎么办` · `sing-box 配置教程`

### 2.3 现有页面 → 目标关键词映射

| 页面 | 主关键词 | 意图 | 状态 |
|---|---|---|---|
| `/` | 飞星梯 / 海外网络个人 | 品牌+交易 | 已上线 |
| `/guides/clash-quickstart/` | Clash 订阅导入教程 | 信息 | 已上线 |
| `/guides/shadowrocket-ios/` | Shadowrocket 使用教程 | 信息 | 已上线 |
| `/guides/client-compare/` | Clash / V2Ray / sing-box 对比 | 商业调查 | 已上线 |
| `/guides/speedtest/` | 节点测速怎么看 | 信息 | 已上线 |
| `/guides/troubleshooting/` | 代理常见报错排查 | 信息 | 已上线 |
| `/solutions/ai-tools/` | ChatGPT / Claude 访问 | 信息 | 已上线 |
| `/solutions/streaming/` | Netflix / YouTube 解锁 | 信息 | 已上线 |

### 2.4 内容缺口（优先补）

1. `sing-box` 专项配置教程（搜索上升，本站仅提及未成篇）；
2. 移动端场景：`Android v2rayNG` 图文教程；
3. 解码测速指标：延迟 / 抖动 / 丢包分别影响什么（可从 `/guides/speedtest/` 拆出独立页）；
4. FAQ 结构化：把首页 4 个 FAQ 扩展为独立 FAQ 页并上 `FAQPage` schema。

---

## 三、外链与权重建设（核心）

### 3.1 站群内链矩阵（唯一完全可控的 dofollow 来源）

- 三站 footer 互链已配置（`pobiren.top` / `kuaifei.top` / `tkya.us.ci`）。
- **补强**：在教程正文做上下文内链。例如「Clash 快速上手」末尾自然链接 `/guides/speedtest/` 教读者验证节点；「AI 工具」页链接 `/guides/troubleshooting/` 处理报错。
- 锚文本用主题描述，不用「点这里」。
- 评测站 `tkya.us.ci` 以「深度合作品牌」披露链接到本站，保持披露透明。

### 3.2 真实外链渠道（个人向站点专属打法）

| 渠道 | 链接属性 | 预期 | 具体做法 |
|---|---|---|---|
| 开源客户端生态（Clash Verge / sing-box 等）社区 | dofollow / UGC | **高** | 贡献文档、提 Issue 解答，链接作为参考资料自然出现 |
| 技术社区（V2EX / 掘金 / Linux.do） | UGC / 部分 dofollow | 中高 | 发「新手配置避坑」长文，先给价值再给链接 |
| GitHub 资源清单 / Awesome 列表 | nofollow 但高曝光 | 中 | 提 PR 收录本站教程（真实有用才会被合并） |
| 开发者博客 / 教程站 | dofollow | 中 | 互换「延伸阅读」，或供稿被引用 |
| 问答平台（知乎等） | nofollow | 引流 | 回答配置类问题，附来源链接 |
| 行业目录 / AI 工具导航站 | dofollow | 中 | 提交站点资料，NAP 一致 |

> 注意：纯甩链接在开发者社区极易被判 spam。**先把问题答清楚，链接只是补充**。

### 3.3 可被引用的内容资产（linkable assets）

1. **一键配置模板仓库**（Clash / sing-box 示例配置，开源可 fork）——与 GitHub 身份层联动最强；
2. **节点测速脚本**（开源，输出 RTT/抖动/丢包表格），可被技术博客引用；
3. **客户端配置对照表**（各平台导入步骤一页通览），易被收藏与引用；
4. **报错代码速查表**（按错误码 → 原因 → 解法），长尾流量 + 引用双收。

### 3.4 白帽红线

- 不买链接、不参与 PBN、不刷 star；
- 不在 README 堆砌关键词（GitHub 有反 spam 机制）；
- 不做 doorway pages / 隐藏文本；
- 外链增长保持自然节奏。

---

## 四、站内技术 SEO 检查表

- [x] `robots.txt` 允许抓取并声明 sitemap
- [ ] 验证 `sitemap.xml` 可访问、全部 URL 返回 200
- [ ] 全站 self-referencing canonical（检查 `head.html`）
- [ ] JSON-LD：Organization + Article + FAQPage + BreadcrumbList（核验有效性）
- [ ] Core Web Vitals：LCP < 2.5s / INP < 200ms / CLS < 0.1
- [ ] 图片 WebP 化 + `alt` + 显式尺寸；教程截图压缩 < 100KB
- [ ] 404 返回真实 404，非软 404
- [ ] 面板站 `app.feixingti.top` 保持 `noindex`，与内容站隔离

---

## 五、90 天执行节奏

| 阶段 | 时间 | 重点动作 | 交付物 |
|---|---|---|---|
| P1 基础 | 第 1–2 周 | 修 canonical / sitemap / JSON-LD；注册 GSC、Bing WMT、百度资源平台；提交 sitemap | 技术体检报告 |
| P2 内容 | 第 3–6 周 | 补 sing-box / v2rayNG / FAQ 三篇；完成 4 个可引用资产中的 2 个 | 内容集群完成 |
| P3 外链 | 第 5–10 周 | 开源社区贡献 3 次；技术社区长文 2 篇；资源清单 PR 2 次 | 外链台账 |
| P4 迭代 | 第 11–13 周 | 按 GSC 数据优化「有展现无点击」词；复盘 KPI | 月度复盘报告 |

---

## 六、度量与 KPI

- **工具**：Google Search Console（主）、Bing Webmaster Tools、百度资源平台、GitHub Insights（星标 / fork 作为信任信号，非排名因子）。
- **核心指标**：非品牌词展现 / 点击、目标词平均排名、引荐域名数、索引覆盖率。
- **目标（12 个月）**：非品牌自然流量 +50%；30% 目标词进 Top 3；技术健康 ≥90 分。
- **节奏**：每周记录，每月复盘；至少 8 周数据才判断趋势。

---

## 变更记录

| 日期 | 变更 | 操作人 |
|---|---|---|
| 2026-11-27 | 初版 SEO 方案；明确 GitHub nofollow 事实与开发者社区打法 | SEO 策略 |
