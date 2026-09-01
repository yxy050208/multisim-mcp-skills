# Multisim MCP Skills

面向 Multisim MCP 的中文优先 Agent Skills，覆盖电路设计规划、受控实验、故障诊断、
实验比较、需求验收和实验报告。它们只提供工作流指令，实际能力来自
[`yxy050208/multisim-mcp`](https://github.com/yxy050208/multisim-mcp)。

> 非 NI 官方项目。真实 Multisim 自动化需要 Windows、本机已安装并授权的 Multisim，
> 以及正确配置的 Multisim MCP。Skills 不包含 NI 软件、模型、样例或本机密钥。

## Skills

| Skill | 用途 |
| --- | --- |
| `multisim-circuit-workflow` | 从安装诊断到成图、仿真、分析和报告的完整工作流 |
| `multisim-create-experiment` | 先比较技术方案，再受控生成并验证电路实验 |
| `multisim-debug-circuit` | 诊断故障并评估最小、可逆的电路修改 |
| `multisim-compare-experiments` | 比较 baseline 与 candidate 的设置、测量和证据 |
| `multisim-verify-requirements` | 将设计要求转换成 PASS / FAIL / 未验证判据 |
| `multisim-write-lab-report` | 基于真实实验产物生成中英双语报告 |

## skills.sh / 通用 Agent 安装

先查看仓库中可用的 Skills：

```bash
npx skills add yxy050208/multisim-mcp-skills --list
```

安装一个 Skill 到 Codex：

```bash
npx skills add yxy050208/multisim-mcp-skills \
  --skill multisim-create-experiment \
  --agent codex --copy --yes
```

安装全部 Skills 到 Codex：

```bash
npx skills add yxy050208/multisim-mcp-skills \
  --skill '*' --agent codex --copy --yes
```

同一仓库也可安装到 Claude Code、Cursor、OpenClaw 和 skills CLI 支持的其他 Agent。

## ClawHub / OpenClaw

发布审核完成后，可按单个 Skill 安装：

```bash
openclaw skills install @yxy050208/multisim-create-experiment
openclaw skills install @yxy050208/multisim-debug-circuit
```

ClawHub 页面和最终命令以各 Skill 发布页显示为准。

## 安全边界

- 先规划、审阅和验证，再执行写入或仿真。
- 不把“候选可采用”解释为自动覆盖授权。
- 不把缺失数据猜成实验结果。
- API Key 只保留在本机环境变量或受信任客户端配置中。
- 不分发 NI 专有文件、提取模板或授权安装内容。

## English summary

Chinese-first Agent Skills for the Multisim MCP circuit-engineering workflow.
They guide planning, controlled experiment generation, debugging, comparison,
acceptance verification, and evidence-backed reporting. The skills contain no
NI software, licensed templates, circuit samples, or credentials.

## License

MIT-0. ClawHub also distributes published skills under MIT-0.
