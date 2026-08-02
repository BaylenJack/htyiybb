<div align="center">

# ⚡ 网络测速 · SpeedTest

**纯前端 · 单文件 · 零依赖的开源测速站**

一个深色现代风格、可直接部署的浏览器测速工具。测量你的网络 **延迟、抖动、下载与上传速度**，并配实时仪表盘呈现测速过程。

`index.html` 一个文件搞定一切——结构、样式、测速引擎全部内联，开箱即用。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Web%20%2F%20Desktop-blue)](#)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)
[![Made with ❤](https://img.shields.io/badge/Made%20with-%E2%9D%A4-ff69b4)](#)

</div>

---

## ✨ 特性

| | 说明 |
|---|---|
| 📡 **延迟 + 抖动** | 5 次探测取最小值，抖动 = 平均偏差；单个探测失败自动跳过 |
| ⬇️ **下载测速** | 3 路并发流式下载（每路 50MB），实时逐块累计 |
| ⬆️ **上传测速** | 2 路并发分批上传（每批 5MB），流量直达 Cloudflare 端点 |
| 🎛️ **实时仪表盘** | SVG 圆环进度 + 环内大数字，EMA 平滑逐帧显示 |
| 🎨 **速度分级** | 按阈值着色（极好 / 好 / 一般 / 差），一眼判断网络水平 |
| 🌐 **服务器信息** | 自动识别连接的 Cloudflare 边缘节点（城市 / ASN / IP） |
| 🛡️ **健壮性** | 单连接失败只跳过该连接，单阶段失败不中断整体流程 |
| 🔒 **隐私友好** | 测速数据仅在浏览器本地计算，除测速流量外不发送任何数据 |

## 🚀 快速开始

**方式一 · 本地静态服务器（推荐）**

```bash
git clone https://github.com/BaylenJack/htyiybb.git
cd htyiybb
python -m http.server 8000
```

浏览器访问 <http://localhost:8000>，点击圆形按钮开始测速。

**方式二 · 直接双击**

用浏览器打开 `index.html` 即可。测速流量是页面向 `https://speed.cloudflare.com` 发起的跨源请求（返回 `Access-Control-Allow-Origin: *`），从 `file://` 页面发起也能正常测速；若双击无反应，请改用本地服务器方式。

**方式三 · 部署到任意静态托管**

上传 `index.html` 到 GitHub Pages、Vercel、Netlify 或任意静态文件服务即可——零配置，开箱即用。

## 🔧 技术原理

- **测速端点**：[Cloudflare 公开测速接口](https://speed.cloudflare.com/) —— `__down?bytes=N`（下载 N 字节随机数据并流式输出，`bytes=0` 用于延迟探测）与 `__up`（上传，POST 任意数据体）
- **并发策略**：下载 3 路 / 上传 2 路并发，逼近真实可用带宽（同 speedtest.net 思路）
- **流式读取**：下载经 `ReadableStream` 逐块读取实时累计；上传按 5MB 批串行发送
- **精准计时**：`t0` 在首个数据块到达时置位，`lastByteAt` 记录末字节时刻；上传以 `bytesAtT0` 为基线消除 `N/(N-1)` 系统性高估
- **稳定段平均**：丢弃慢启动段（DNS / 连接 / TLS 冷启动），取稳定段平均吞吐作为最终值
- **EMA 平滑**：`requestAnimationFrame` 帧间差分 + α=0.2 指数移动平均，仪表盘数字流畅不抖动
- **超时兜底**：所有请求 `AbortSignal.timeout` 超时自动中止，挂起连接不会卡死流程

## 📁 目录结构

```
htyiybb/
├── index.html   # 唯一入口：结构 + 样式 + 测速引擎（全部内联，单文件）
├── README.md    # 本文档
└── LICENSE      # MIT 开源许可
```

## 🤝 贡献

欢迎任何形式的贡献——Bug 报告、功能建议、代码提交都行！

- **提 Issue**：遇到问题或想加功能，[开一个 issue](https://github.com/BaylenJack/htyiybb/issues/new)
- **提 PR**：Fork 后修改，提交 PR 即可；保持单文件原则（一切内联在 `index.html`）
- **行为准则**：友善、尊重、就事论事

## 📄 License

[MIT License](LICENSE) · Copyright (c) 2026 [BaylenJack](https://github.com/BaylenJack)

---

<div align="center">

**如果这个项目对你有帮助，欢迎 ⭐ Star 支持！**

</div>
