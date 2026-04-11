# Three-Dimension Diagnostic — Detailed Guide

## Overview

This framework adapts the PRD three-perspective diagnostic for academic research.
Before committing to any research direction, verify it from three angles.

## Conversation Style

- Ask 1-2 questions at a time, not all at once.
- Progress naturally through dimensions; skip questions the user has already answered.
- If the user is stuck on a dimension, help them think through it instead of skipping.

---

## Dimension 1: Academic Value

**Goal**: Confirm the research addresses a real, significant, and novel problem.

### Questions (ask selectively)

1. "这个问题解决之后，领域中会有什么新能力或新理解？"
   - Looking for: concrete new capability, not vague "improvement"

2. "你针对的 failure case 或 limitation 是否足够重要？（还是只存在于极端场景？）"
   - Looking for: practical significance, not edge cases

3. "你的核心 insight 是什么？和已有方法的本质差异在哪里？"
   - Looking for: genuine novelty, not incremental parameter tuning

4. "目前有没有其他组在做类似的工作？你和他们的差异是什么？"
   - Looking for: competitive landscape awareness

### Red Flags
- The user cannot articulate what is new beyond "we use X for Y"
- The targeted failure case is trivial or contrived
- Multiple concurrent works with nearly identical approach

---

## Dimension 2: Technical Feasibility

**Goal**: Confirm there is a realistic technical path to results.

### Questions (ask selectively)

1. "你的方法的核心 pipeline 是什么？能否用 3-5 步描述？"
   - Looking for: clear technical plan, not vague intentions

2. "有没有初步实验或 pilot study？结果如何？"
   - Looking for: at least some evidence the direction works

3. "预期的 baseline 有哪些？你打算怎么做公平比较？"
   - Looking for: awareness of comparison methodology

4. "方法中最难的部分是什么？如果这部分做不出来，有没有退路？"
   - Looking for: risk awareness and fallback planning

### Red Flags
- No clear technical path ("we'll figure it out as we go")
- No preliminary evidence of any kind
- The hardest component has no fallback

---

## Dimension 3: Resource Constraints

**Goal**: Confirm the research is achievable with available resources.

### Questions (ask selectively)

1. "需要什么计算资源？你现在能用到什么？"
   - Looking for: compute reality check

2. "需要什么数据？是公开的还是需要自己收集/标注？"
   - Looking for: data availability

3. "目标 deadline 是什么？（投稿截止 / 毕业答辩）"
   - Looking for: timeline reality check

4. "有没有关键依赖项？（特殊硬件、合作者数据、外部 API）"
   - Looking for: blocking dependencies

### Red Flags
- Compute needs far exceed available resources with no plan to bridge
- Critical data does not exist and creation timeline is unknown
- Timeline is unrealistically tight for the scope

---

## Diagnostic Summary Template

After completing all three dimensions:

```markdown
## Research Direction Diagnostic Summary

### Academic Value Assessment
- Problem significance: [High/Medium/Low] — [reason]
- Novelty: [High/Medium/Low] — [reason]
- Competition risk: [High/Medium/Low] — [reason]
- **Overall**: [Ready to proceed / Needs strengthening in ...]

### Technical Feasibility Assessment
- Technical route clarity: [Clear/Partial/Unclear]
- Preliminary evidence: [Strong/Some/None]
- Risk mitigation: [Has fallback/No fallback]
- **Overall**: [Ready to proceed / Needs pilot experiment / Needs route rethink]

### Resource Fit Assessment
- Compute: [Sufficient/Tight/Insufficient]
- Data: [Available/Needs work/Unavailable]
- Timeline: [Comfortable/Tight/Unrealistic]
- **Overall**: [Ready to proceed / Needs resource planning / Needs scope reduction]
```
