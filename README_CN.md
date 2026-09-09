# Contra —— 写作者的魔鬼代言人

> [English](./README.md) | **中文**

**不要发布任何未经最刻薄读者攻击过的文章。**

Contra 是一个浏览器侧边栏插件，在你发布长文之前对它进行压力测试。选中任意文本——Substack 长文、产品发布稿、观点评论——三个相互独立的对抗性 AI 内核并行开工，把结构化的发现实时渲染成红、黄、绿三色卡片。

[![Manifest V3](https://img.shields.io/badge/Manifest-V3-blue)]() [![Chrome + Edge](https://img.shields.io/badge/Chrome%20%2B%20Edge-支持-4285F4)]() [![定价](https://img.shields.io/badge/Pro-%249%20终身买断-166534)]() [![遥测](https://img.shields.io/badge/遥测-零-b91c1c)]()

---

## 三位编辑

| 内核 | 职责 | 产出 |
|---|---|---|
| ⚔️ **苛刻挑刺者** | 找出 3 个最致命的逻辑断点——刻薄的专家读者会逐字引用来攻击你的那些句子 | 红卡，按严重度分级 |
| 🔍 **盲区猎犬** | 并行且**独立**运行：未被审视的利益相关方、未言明的假设、2024–2026 的反例证据 | 黄卡，附反例与置信度 |
| 🛡️ **立论锻造师** | 把最脆弱的论述预先加固（Prebunking），让反对者无从下嘴 | 绿卡，原句/改写对照 |

两个分析内核互相看不到对方的输出——真实的分歧就是产品本身。每条改写都锚定到具体的漏洞编号。

## 核心特性

- **并行双核引擎 + 合成改写**：比直接问模型多出 ≥50% 的新颖发现（Framework Gain ≥ 1.5，由评测体系强制保障）
- **阶段化进度**：每核独立计时、思考期安抚文案、骨架屏卡片——零死屏焦虑
- **一键导出**完整审查报告为 `.txt`
- **中英双语界面**；审查输出语言跟随被审文章
- **任意网页可用**：Readability 全文提取，或划词 → 右键 →"发送选区到 Contra"
- **新手引导**：首次打开 30 秒上手

## 架构级隐私

- **BYOK**——自带 API Key：支持 Anthropic、OpenAI、OpenRouter、DeepSeek、Qwen、Doubao、Kimi。没有 Contra 服务器，你的文章从浏览器直发你选择的供应商。
- **静态加密**——Key 在本机 AES-GCM 加密存储；Pro 可加口令金库。
- **零遥测**——无分析、无跟踪、无账号。
- **一键撤销**——即刻清空本机全部密钥。

详见：[隐私政策](./PRIVACY.md)

## 定价

**免费版**：挑刺内核 · 七家供应商全开 · 每日 10 次
**Pro —— $9 终身买断**：三核全开 · 不限次数 · 自定义端点 · 口令金库

一次性购买，无订阅、无账号。收银由合规的 MoR（记录卖方）平台处理（支持全球银行卡、含税）；卡密通过邮件发送，在设置 → 激活 Pro 中粘贴即可。

## 安装

- **Chrome Web Store / Microsoft Edge Add-ons**：审核中，链接即将上线
- **手动安装（开发者模式）**：下载最新 Release zip 解压，`chrome://extensions` → 开发者模式 → 加载已解压的扩展程序

## 开发

基于 [WXT](https://wxt.dev/) + React 19 + TypeScript + Tailwind CSS v4 构建。

```bash
npm install
npm run dev        # 热重载侧边栏
npm run build      # chrome-mv3 生产构建
npm run build:edge # edge 构建
npx vitest run     # 190+ 单元/契约测试
npm run eval       # 引擎量化评测（BYOK，报告写入 eval/reports/）
```

引擎配备量化质量门槛：LLM-as-Judge 评分、视角独特性比率（CUR）、反迎合配额，基于 6 篇策展文集——任何 prompt 改动不得使门槛退化。

## 许可证

Contra 是商业软件，见 [LICENSE](./LICENSE)。引擎方法论灵感来自 MIT 许可的上游项目 Baker Street。

---

*别再发布一遇到抬杠就站不住脚的论证。先让 Contra 过一遍。*
