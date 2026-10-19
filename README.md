# DSH Plugins

A curated collection of plugins for **DSH (DeepSeek Harness)** — research, reading, web access, session workflows, and rendering.

DSH 是一个可扩展的智能体工作环境。这个仓库是插件索引：每个插件保留自己的仓库、版本节奏和许可证，这里维护合集层面的分类、说明与可用状态。

> **Status / 状态**：5 个插件已公开，8 个仍在本地迭代。未公开的插件只在这里列出，不包含源码。

## 插件列表

### 研究与阅读 / Research & reading

| 插件 | 说明 | 状态 |
| --- | --- | --- |
| `dsh-academic-search` | 跨 arXiv、OpenAlex、Semantic Scholar、Crossref 的 CS/AI 学术检索；论文身份归并、有界引用链、arXiv 原文交接。六个工具，不调用模型 API。 | 本地迭代中 |
| `dsh-paper-reader` | 论文解读模式：生成带页码与章节锚点的结构化报告，并基于同一份解析产物回答追问。 | 本地迭代中 |
| `dsh-courseware-reader` | 课件解析与考前复习：梳理知识点，生成带出处的复习报告与考点速查表。 | 本地迭代中 |
| `dsh-autoresearch` | 研究工作流：从已有证据发现问题、综合论文、设计有界实验、撰写可追溯稿件。纯技能插件。 | 本地迭代中 |

### 网络访问 / Web access

| 插件 | 说明 | 状态 |
| --- | --- | --- |
| [`dsh-web-search-keyless`](https://github.com/s11phere/dsh-web-search-keyless) | 无需密钥、不消耗模型回合的搜索 provider；Bing RSS 为主，DuckDuckGo Lite 兜底。 | 公开 |
| `dsh-web-fetch-tun` | 在 Clash / mihomo 的 fake-ip、TUN 环境下仍可工作的 `ctx.web` fetch provider，保留 SSRF 防护。 | 本地迭代中 |
| `dsh-web-fetch-deepseek` | 把抓取交给 DeepSeek 官方 Fetch 接口的 provider，适合本地匿名抓取被网络环境拒绝时使用。 | 本地迭代中 |

### 会话与工作流 / Session & workflow

| 插件 | 说明 | 状态 |
| --- | --- | --- |
| [`dsh-btw-sidebar`](https://github.com/s11phere/dsh-btw-sidebar) | Codex 风格的 `/btw`：把当前会话分叉到 DSH 原生右侧栏，继续使用完整会话与工具能力。 | 公开 |
| `dsh-session-drag-reference` | 把左侧会话列表里的会话直接拖进输入框，插入官方会话引用芯片。 | 本地迭代中 |
| [`dsh-away-notify`](https://github.com/s11phere/dsh-away-notify) | 只有当你不在 DSH 页面时，才为完成、出错、等待审批等事件弹桌面通知；点击回到对应会话。 | 公开 |
| [`dsh-commandcode-quota`](https://github.com/s11phere/dsh-commandcode-quota) | 在会话页头查看 Command Code 套餐的 5 小时 / 每周 / 月度额度、重置倒计时与计费周期用量。 | 公开 |
| `dsh-plugin-sync` | 通过一台可 ssh 的云主机，在两台设备之间同步插件源码、启用清单与插件配置。 | 本地迭代中 |

### 渲染 / Rendering

| 插件 | 说明 | 状态 |
| --- | --- | --- |
| [`dsh-tex-block-normalizer`](https://github.com/s11phere/dsh-tex-block-normalizer) | 修复 Pandoc 风格 `$$` 公式块被误解析的问题：公式首行丢失、正文被吞进 KaTeX 报错节点等。 | 公开 |

## 安装

已公开的插件可以直接从 GitHub 安装。以无密钥搜索为例：

```bash
dsh plugin --profile web add github:s11phere/dsh-web-search-keyless
```

安装后重启 `dsh web` 并刷新页面。不同插件对 DSH 版本、profile 和操作系统的要求写在各自仓库的 README 中。

## 设计原则

- **补真实缺口**：先确认工作流里到底缺什么，再决定要不要写插件。
- **优先宿主接缝**：能在 DSH 已有的 seam 上解决，就不额外包一层模型调用。
- **按需开启**：常驻能力尽量做成项目级开关，避免污染每个会话的工具目录。
- **可验证**：安装脚本、平台差异和失败模式都写进 README，而不是只留一句“装完即用”。

## 仓库结构

这个仓库是索引而不是 monorepo：

- `README.md`：分类、说明与安装入口。
- `plugins.json`：机器可读的插件清单，方便之后生成页面或检查状态。

每个插件的源码、构建产物和许可证保留在各自仓库中。未公开的插件不在此仓库分发。

## 许可证

本仓库的索引文本以 CC BY 4.0 提供。各插件代码遵循其各自仓库中的许可证。

---

**English summary**: A curated index of DSH plugins for academic search, paper and courseware reading, keyless web access, session workflows, notifications, and math rendering. Public plugins link to their own repositories; plugins still in local development are listed without source code.
