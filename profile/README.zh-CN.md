<p align="center">
  <img src="./assets/x-one-avatar.png" width="132" alt="X-One AI avatar">
</p>

<h1 align="center">X-One AI</h1>

<p align="center">
  面向 Safe Agent Operations 的开源工具。
</p>

<p align="center">
  Agentic DevSecOps · MCP safety · AI agent workflow evidence
</p>

<p align="center">
  <a href="./README.md">English</a>
</p>

## 方向

X-One 构建面向 Safe Agent Operations 的工具，帮助团队在开发工作流中更安全地采用 AI agents 和 MCP tools。

我们关注：

- MCP tool safety
- agent permissions
- secret 与配置风险
- CI safety gates
- agent-generated PR evidence
- 可调试、可审计的 agent 工作流

## 已发布工具

| 项目 | 作用 | 成熟度 |
|---|---|---|
| [mcp-audit](https://github.com/X-One-AI/mcp-audit) | 扫描 MCP 与 agent 配置中的高风险权限、secret、不安全命令、CI 安全缺口、baseline、exception 和团队 policy gate。 | Stable production track |
| [agent-pr-evidence](https://github.com/X-One-AI/agent-pr-evidence) | 为 AI agent 生成的 PR 生成可审查的安全与交付证据。 | 已发布 |
| [agent-failure-packet](https://github.com/X-One-AI/agent-failure-packet) | 为失败 agent run 生成脱敏、可共享的调试包。 | 已发布 |

## 数据与演练资产

| 项目 | 作用 | 成熟度 |
|---|---|---|
| [mcp-risk-index](https://github.com/X-One-AI/mcp-risk-index) | 维护有证据支撑的常见 MCP server 与权限风险索引。 | 已发布 |
| [ai-incident-lab](https://github.com/X-One-AI/ai-incident-lab) | 提供 AI agents、MCP tools 和 agent-generated code 的事故模拟案例。 | 已发布 |
| [homebrew-tap](https://github.com/X-One-AI/homebrew-tap) | X-One CLI 工具的 Homebrew 分发渠道。 | Distribution infrastructure |

## 决策仓库

| 项目 | 作用 | 决策规则 |
|---|---|---|
| [ai-prod-check](https://github.com/X-One-AI/ai-prod-check) | 生产检查想法的决策仓库。 | 吸收、写成文章、观察或拒绝。 |
| [agent-trace](https://github.com/X-One-AI/agent-trace) | tracing platform 想法的决策仓库。 | 有价值的证据想法进入 `agent-failure-packet`，否则观察或拒绝。 |
| [oss-doctor](https://github.com/X-One-AI/oss-doctor) | 通用 repo-health 想法的决策仓库。 | 有证据支撑的事实进入 `mcp-risk-index`，否则观察或拒绝。 |

组合治理和成熟度门槛记录在 [Portfolio Health](../docs/portfolio-health.md)。

## 安装

```bash
python3 -m pip install xone-mcp-audit
brew tap X-One-AI/tap
brew install mcp-audit
```

其它已发布项目包可通过 PyPI、TestPyPI、GitHub Releases 和 Homebrew formulae 安装。

## 工程原则

- 目标是生产级好用，不是 demo 级能用。
- 优先 local-first 和可审查，再考虑托管自动化。
- 用证据支撑判断，不做模糊安全承诺。
- 团队 policy、baseline、exception 和 release artifact 都应该版本化。
- 每个项目引用共享的 One Person Team 工作方式，同时保留自己的约束与 skill。

## 给 builder 和团队

如果你的团队正在把 AI agents 接入仓库、终端、CI 或 MCP servers，最先要回答的问题很简单：

> 这个 agent 能触碰、执行、泄露或修改什么，而且可能没人注意到？

X-One 的存在，就是为了让这个问题更容易被回答。
