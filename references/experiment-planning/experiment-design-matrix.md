# Experiment Design Matrix Template

## Purpose

Map every major claim in the paper to a concrete validation experiment.
This ensures no claim is left unsupported in the final paper.

## Template

```markdown
## Claim-Experiment Matrix: [Paper Name]

| Claim ID | Claim Statement | Experiment Type | Dataset(s) | Metric(s) | Baseline(s) | Priority | Status |
|----------|-----------------|-----------------|------------ |-----------|-------------|----------|--------|
| C1 | [Exact claim text] | Comparison | [Dataset] | [Metric ↑/↓] | [Method A, B] | 🔴 Core | ⬜ Pending |
| C2 | [Exact claim text] | Ablation | [Dataset] | [Metric] | Full vs -X | 🔴 Core | ⬜ Pending |
| C3 | [Exact claim text] | Generalization | [Dataset] | [Metric] | Full model | 🟡 Important | ⬜ Pending |
| C4 | [Exact claim text] | Efficiency | - | Latency, Params | [Method A] | 🟡 Important | ⬜ Pending |
| C5 | [Exact claim text] | Analysis | [Dataset] | Qualitative | - | ⚪ Nice-to-have | ⬜ Pending |
```

## Status Tracking

| Status | Meaning |
|--------|---------|
| ⬜ Pending | Not started |
| 🔄 Running | Experiment in progress |
| ✅ Supported | Results support the claim |
| ⚠️ Partial | Results partially support; claim may need softening |
| ❌ Failed | Results do not support; claim must be revised or removed |

## Quality Checks

After filling the matrix:
1. Every 🔴 Core claim has at least one experiment → if not, add one.
2. Every experiment maps to at least one claim → if not, either remove the experiment or find its claim.
3. No claim references a metric that is not in the matrix → complete the metrics column.
