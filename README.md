# 电力市场申报研究助手

这是一个面向电力市场申报研究的 Codex skill 仓库。

仓库主体使用英文 `SKILL.md`，方便在 Codex / agent 工作流里触发和复用；仓库说明文档保持中文，方便直接阅读和继续维护。

这个 skill 的定位不是“自动替你申报”，而是帮助研究员和算法工程师更稳地完成这些工作：

- 解读市场日报、披露信息和规则变动
- 审计申报策略假设、数据时点和口径一致性
- 复核回测结论、策略映射和风险边界
- 基于已有信息整理候选申报思路、主要风险和下一步研究问题

这个公开版本保持通用，不写死到任何特定区域、市场规则、内部数据源或私有执行流程。

## 适合谁用

- 电力现货 / 中长期交易研究员
- 做电力量价、策略、回测的平台或算法工程师
- 需要把模型输出翻译成业务可讨论结论的研究团队

## 它解决什么问题

电力市场研究里，常见问题往往不是“模型不够复杂”，而是：

- 决策时点和数据可见时点混在一起
- 市场规则、披露口径、结算口径没有先锁定
- 回测里能用的数据，实盘申报时其实看不到
- 模型分数直接被当成申报动作，没有明确动作映射
- 结论写得像确定答案，但实际依赖很多未说明的假设

这个 skill 的目标，就是把这些高频错误尽量前置拦下来。

## 能做什么

- 解读日报、快报、公告、披露材料，提炼对申报研究有用的市场信号
- 审核策略或模型是否存在未来信息泄露、时点穿越、口径漂移
- 复核回测是否说明了样本区间、动作映射、基准、分段表现和失效条件
- 把模型输出整理成 2-3 个候选申报场景，而不是伪装成唯一正确答案
- 明确列出关键假设、剩余不确定性、风险点和下一步应补的数据

## 不做什么

- 不直接替代交易员或研究负责人做最终申报
- 不默认所有区域、品种、阶段的市场规则一致
- 不在关键规则缺失时给出“确定性策略”
- 不把缺失输入、部分样本、口径不清的分析包装成可执行结论

## 仓库结构

```text
.
├─ .gitignore
├─ LICENSE
├─ README.md
├─ SKILL.md
├─ agents/
│  └─ openai.yaml
└─ references/
   ├─ backtest-review-checklist.md
   ├─ daily-report-analysis.md
   ├─ market-context-template.md
   ├─ output-templates.md
   ├─ privacy-and-sanitization.md
   └─ strategy-risk-checklist.md
```

## 使用方式

把整个目录放到：

- Windows: `%USERPROFILE%\\.codex\\skills\\power-market-bidding-research-assistant\\`
- macOS / Linux: `${CODEX_HOME:-$HOME/.codex}/skills/power-market-bidding-research-assistant/`

然后在支持自定义 skill 的环境里调用：

```text
Use $power-market-bidding-research-assistant to interpret a market report, audit a bidding strategy, or review a backtest before forming candidate bidding scenarios.
```

## 声明

这是一个研究辅助 skill，不是自动申报系统。

最终申报、合规复核、风险审批和执行落地，必须由具备业务与合规责任的人工完成。
