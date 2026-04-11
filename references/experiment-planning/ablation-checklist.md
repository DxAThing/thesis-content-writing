# Ablation Checklist — Automated Derivation Rules

## Purpose

Systematically generate ablation experiments from the method pipeline.
Prevents missing important ablations that reviewers will ask about.

## Derivation Procedure

### Input
The method pipeline figure or module list from `paper-storyline` or `research-prd`.

### Rule 1: Module-Level Ablations
For every module M in the pipeline:
- **Remove-M**: Remove the module entirely (use skip connection or default value).
- **Replace-M**: Replace with the simplest baseline alternative.
- Purpose: Shows the module contributes positively.

### Rule 2: Design Choice Ablations
For every non-trivial design choice D (architecture, loss function, training strategy):
- **Variant-D**: Swap in the most obvious alternative design.
- Purpose: Shows our specific design is better than the naive choice.

### Rule 3: Interaction Ablations
For pairs of modules that are conceptually coupled (M_i, M_j):
- **Remove-both**: Remove M_i and M_j simultaneously.
- Compare: (Full) vs (−M_i) vs (−M_j) vs (−M_i −M_j).
- Purpose: Shows whether modules are complementary (combined effect > sum of individual effects).

### Rule 4: Hyperparameter Sensitivity
For key hyperparameters H:
- Test 3-5 values spanning a reasonable range.
- Report metric curve.
- Purpose: Shows robustness and helps readers reproduce.

## Checklist Template

```markdown
## Ablation Checklist

### Module Ablations
| ID | Ablation | Type | Variant Description | Expected |
|----|----------|------|--------------------|---------| 
| A1 | Remove [Module A] | Remove | Skip connection | Drop ~X |
| A2 | Replace [Module A] with [Baseline] | Replace | Simple alternative | Our A > baseline |

### Design Choice Ablations
| A3 | [Choice 1] → [Alternative] | Variant | [Description] | Our choice better |

### Interaction Ablations
| A4 | Remove [A] + [B] | Interaction | Both removed | Combined > individual |

### Hyperparameter Sensitivity
| A5 | [Param] = {v1, v2, v3, v4, v5} | Sensitivity | Range sweep | Stable within range |
```

## Priority Assignment
- 🔴 Core: Every novel module and every novel design choice must have an ablation.
- 🟡 Important: Interaction tests for coupled components.
- ⚪ Nice-to-have: Hyperparameter sensitivity (but reviewers often ask).
