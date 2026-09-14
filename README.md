# decision-records 决策记录

Decisions without recorded reasons get re-litigated forever — every few weeks someone reopens the same question because nobody remembers why it was closed.

没有记录理由的决策会被反复重新争论——每隔几周就有人重开同一个问题，因为没人记得它当初为什么被关掉。

## Why / 为什么

"Use X" is a fact that goes stale. "Use X because Y; we rejected Z" is a decision the next person can respect — or consciously revisit with full information. The expensive decisions are the ones that are expensive to reverse **or** expensive to re-argue; those are the ones worth one short record.

"用 X"是一个会过期的事实。"用 X，因为 Y；否决了 Z"是一个下个人可以尊重的决策——或者带着完整信息有意识地重开。昂贵的决策是那些难以回退**或**难以重新争论的决策——它们才值得一条简短的记录。

## The format / 格式（5 行就够）

```
### 2026-09-14 — Use plan B for syncing
- Decision: sync via UUID, not timestamps
- Alternatives: timestamps (rejected: clock skew across devices)
- Why: IDs survive offline edits; timestamps silently drop concurrent rows
- Reversible? yes — migration script exists
```

No template ceremony, no approval workflow. One file (`decisions.md`) or one section in the project's existing doc, next to the work it governs.

不要模板仪式，不要审批流程。一个文件（`decisions.md`）或项目现有文档里的一节，放在它治理的工作旁边。

## Rules that make it work / 关键规则

- **The why is the payload.** 结论三个月就过期，理由存活得更久。结论过期，理由还在教育人。
- **Append-only.** 重开旧决策 = 写一条新记录标记 supersedes the old one — 历史保持可读，演变过程清晰可见。Rewriting history is how records rot.
- **Record at the moment of decision.** 会后补记的记录补的是记忆，不是理由。
- **Keep it where the project lives.** In the repo, beside the code — a decision doc nobody passes on their way to work is a decision doc nobody reads.

## Install / 安装

```bash
git clone https://github.com/ChenneyZhuang/decision-records ~/.claude/skills/decision-records
```

One SKILL.md, zero dependencies. MIT. v0.1.0.

单个 SKILL.md，零依赖。MIT 许可，v0.1.0。
