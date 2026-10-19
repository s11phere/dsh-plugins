# DSH Plugins

A curated collection of plugins for **DSH (DeepSeek Harness)** — academic search, paper reading, session workflows, notifications, and math rendering.

DSH 是一个可扩展的智能体工作环境。这个仓库是插件索引：每个插件保留自己的仓库、版本节奏和许可证，这里维护合集层面的分类与说明。

## 插件列表

### 研究与阅读 / Research & reading

| 插件 | 说明 |
| --- | --- |
| [`dsh-academic-search`](https://github.com/tianzeluo/dsh-academic-search) | 跨 arXiv、OpenAlex、Semantic Scholar、Crossref 的 CS/AI 学术检索；论文身份归并、有界引用链、arXiv 原文交接。六个工具，不调用模型 API。 |
| [`dsh-paper-reader`](https://github.com/tianzeluo/dsh-paper-reader) | 论文解读模式：生成带页码与章节锚点的结构化报告，并基于同一份解析产物回答追问。速览 / 解读 / 深读三档可选。 |

### 会话与工作流 / Session & workflow

| 插件 | 说明 |
| --- | --- |
| [`dsh-btw-sidebar`](https://github.com/tianzeluo/dsh-btw-sidebar) | Codex 风格的 `/btw`：把当前会话分叉到 DSH 原生右侧栏，继续使用完整会话与工具能力。 |
| [`dsh-away-notify`](https://github.com/tianzeluo/dsh-away-notify) | 只有当你不在 DSH 页面时，才为完成、出错、等待审批等事件弹桌面通知；点击回到对应会话。 |
| [`dsh-commandcode-quota`](https://github.com/tianzeluo/dsh-commandcode-quota) | 在会话页头查看 Command Code 套餐的 5 小时 / 每周 / 月度额度、重置倒计时与计费周期用量。 |

### 渲染 / Rendering

| 插件 | 说明 |
| --- | --- |
| [`dsh-tex-block-normalizer`](https://github.com/tianzeluo/dsh-tex-block-normalizer) | 修复 Pandoc 风格 `$$` 公式块被误解析的问题：公式首行丢失、正文被吞进 KaTeX 报错节点等。 |

## 安装

插件可以直接从 GitHub 安装。以侧栏会话为例：

```bash
dsh plugin --profile web add github:tianzeluo/dsh-btw-sidebar
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
- `plugins.json`：机器可读的插件清单，方便之后生成页面或检查清单。

每个插件的源码、构建产物和许可证保留在各自仓库中。

## 许可证

本仓库的索引文本以 CC BY 4.0 提供。各插件代码遵循其各自仓库中的许可证。

---

**English summary**: A curated index of DSH plugins for academic search, paper reading, session workflows, notifications, and math rendering. Every plugin links to its own public repository.
