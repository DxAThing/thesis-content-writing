# Experiment Log Template

## Purpose

Provide a structured format for recording experiment results.
Each experiment session gets one log entry. These logs feed into the claim-experiment matrix.

## Template

```markdown
## Experiment Log Entry

### Metadata
- **Experiment ID**: EXP-[sequential number]
- **Date**: YYYY-MM-DD
- **Tests Claim**: [Claim ID from matrix]
- **Type**: Comparison / Ablation / Generalization / Efficiency / Analysis

### Configuration
- **Model**: [Model variant or checkpoint]
- **Dataset**: [Name, split, size]
- **Key Hyperparameters**: [lr, batch_size, epochs, etc.]
- **Hardware**: [GPU type × count]
- **Training Time**: [hours]
- **Random Seed**: [seed value(s)]

### Results

| Metric | Ours | Baseline A | Baseline B | Delta vs Best |
|--------|------|-----------|-----------|---------------|
| [Metric 1 ↑] | ... | ... | ... | +X.X |
| [Metric 2 ↓] | ... | ... | ... | -X.X |

### Observations
- [What worked as expected]
- [What was surprising]
- [What failed or underperformed]
- [Any unexpected behavior or bug encountered]

### Claim Impact Assessment
| Claim | Previous Status | Updated Status | Reason |
|-------|----------------|---------------|--------|
| C[N] | ⬜ Pending | ✅ Supported | [Brief explanation] |

### Artifacts
- Checkpoint: [path]
- Log file: [path]
- Visualization: [path, if any]

### Next Steps
- [ ] [Follow-up experiment if results are inconclusive]
- [ ] [Additional ablation suggested by results]
```

## Usage Rules

1. Fill one entry per distinct experiment run. Do not merge multiple runs into one entry.
2. Always record the random seed for reproducibility.
3. "Observations" should include surprises and failures, not just successes.
4. Update the claim-experiment matrix status immediately after recording.
