# 孙宇晨（Justin Sun）资料归档

> 抓取时间：2026-08-01  
> 路径：`C:\Users\A\Documents\Codex\2026-08-01\ni-ha\sun-yichen-archive\`  
> 抓取人：Codex

## ⚠️ 关于"书籍/音频全文"的说明

孙宇晨已公开**正式出版过一本自传**：

| 项目 | 信息 |
|---|---|
| 中文书名 | 《这世界既残酷也温柔》 |
| 英译名 | *Brave New World* |
| 作者 | 孙宇晨（Sun, Yuchen） |
| 出版社 | 九州出版社（Jiuzhou Press） |
| ISBN | 978-7510850660 |
| 出版时间 | 2017 |

**这本是有版权的图书，本归档不含盗版全文。** 建议通过以下合法渠道获取：
- 京东 / 当当 / 淘宝
- 中国国家图书馆 馆藏
- 出版社官网
- 海外：WorldCat → 找当地图书馆借阅

其他"他讲过的话"的公开来源见下方。

---

## 📁 文件清单（按重要性）

### 🔥 核心传记/介绍（推荐先读）

| 文件 | 字节 | 说明 |
|---|---|---|
| `wiki-en-plain.txt` | 12,933 | **英文维基百科纯文本版**——最完整、最权威的公开简介 |
| `wiki-en.txt` | 29,057 | 英文维基 HTML 提取版（含结构） |
| `wiki-zh.txt` | 13,652 | 中文维基百科纯文本版 |
| `forbes-justin-sun.txt` | 16,606 | Forbes 个人页面 |
| `wiki-en-source-intro.txt` | 3,581 | 维基 wikitext 原文（含 reference 引用） |

### 🛠️ 孙宇晨自己署名/参与的官方技术文档

| 文件 | 说明 |
|---|---|
| `tip-13-justin-sun-author.md` | **TRON Improvement Proposal #13：Account System Standard，作者：Justin Sun**（2018）|
| `java-tron-README.md` | java-tron 仓库 README（孙宇晨作为 TRON 创始人的项目主仓库）|
| `tron-tips.md` | TRON 改进提案列表（含多个由孙宇晨或波场团队署名的 TIP）|
| `tron-doc-en.md` | TRON 英文文档 |
| `tron-docs-index.txt` | TRON 官方文档索引 |
| `gh-tronprotocol-repos.txt` | 波场官方 GitHub 组织下所有仓库列表 |

### 📰 媒体报道/采访（搜索结果页）

| 文件 | 字节 | 来源 |
|---|---|---|
| `coindesk-tag-justin-sun.txt` | 6,456 | Coindesk 标签页 |
| `techcrunch-search.txt` | 5,797 | TechCrunch 搜索 |
| `cointelegraph-justin-sun.txt` | 4,992 | Cointelegraph 标签 |
| `decrypt-search.txt` | 19,010 | Decrypt 搜索（部分内容为 JS 加载，文本不完整）|
| `sina-finance.txt` | 15,139 | 新浪财经 |
| `coinmarketcap-tron.txt` | 15,838 | CoinMarketCap TRON 页面 |

### 🌐 社交媒体/其他

| 文件 | 说明 |
|---|---|
| `x-justinsuntron.txt` | X（推特）个人页 @justinsuntron（注：内容需登录才能看）|
| `youtube-justin-sun.html` | YouTube 搜索结果（视频页）|
| `weibo.html` | 微博搜索页 |
| `substack-justinsun.html` | Substack 主页（暂无公开文章）|
| `douban-justin-sun.html` | 豆瓣读书搜索（无孙宇晨著书籍）|

### 🔧 抓取脚本/原始 HTML（参考用）

- `*.html` — 抓回的原始网页
- `*.json` — API 抓回的 JSON
- `extract_text.py` / `extract_text2.py` / `extract_all.py` — 提取纯文本的脚本

---

## 📚 关键事实速览（来源：英文维基）

- **出生**：1990-07-30，青海西宁
- **教育**：北京大学历史系本科、宾夕法尼亚大学东亚研究硕士
- **创业**：
  - 2014 创办锐波公司（Peiwo App）
  - 2017 创立 TRON（波场），发行 TRX
  - 2018 以 1.4 亿美元收购 BitTorrent
  - 后收购 Poloniex、HTX（原火币）
- **外交**：2021-2023 任格林纳达常驻 WTO 大使
- **财富**：Forbes 2026 年 4 月估 85 亿美元，全球第 411 位
- **法律**：2023 年 3 月被 SEC 起诉（出售未注册证券、市场操纵）；2025 年 2 月案件被 SEC 撤销（特朗普就任后）
- **出版**：2017 年自传《这世界既残酷也温柔》

---

## 🚧 抓取失败的来源（供参考，未来可补）

下列来源因反爬/限流/付费墙无法直接获取内容：

- 百度百科（403）
- WSJ / NYT / Bloomberg（401/403）
- The Block（Cloudflare）
- The Verge / Forbes 子文章（403）
- Wikipedia API（429 限流，但通过网页 HTML 方式拿到了）
- Google Books API（429 限流）
- Amazon / Goodreads（防爬）
- 中信出版社、京东商品页（未尝试，可手抓）

---

## 🛠️ 如何扩展

如需补全，建议手动：

1. 打开 Wikipedia 中关于他的条目，复制"References"区里 Forbes / Bloomberg / The Verge / WSJ 的具体文章 URL，再用 `Invoke-WebRequest` 抓。
2. TRON 自己的 YouTube 频道有大量演讲录像（`youtube-justin-sun.html` 里有视频 ID 列表），可用 `yt-dlp` 抓音频，再用 `whisper` 转写。
3. 一些中文新闻（财新、第一财经）需付费，可考虑通过 archive.org Wayback Machine 找历史快照。
4. 关注他本人在 X / 微博 / Substack 发布的"长文"，那是最高质量的一手材料。

---

> 本归档只收集**公开可合法获取**的内容。**未收录任何盗版电子书/盗版音频。**
