# Evidence Mapping Criteria

## What Counts as Evidence

Evidence is a specific, verifiable element in the paper that supports a claim.

### Valid Evidence Types
| Type | Example |
|------|---------|
| **Table result** | "Table 2 shows our method achieves 35.2 PSNR vs. 34.1 for Baseline A" |
| **Figure visualization** | "Figure 5 shows our method produces fewer artifacts" |
| **Ablation result** | "Table 4 (row 3) shows removing Module A drops PSNR by 2.1" |
| **Statistical test** | "p < 0.01 under paired t-test" |
| **Qualitative example** | "Figure 7 shows our method handles occlusion better" |
| **Analysis chart** | "Figure 8 shows the attention maps focus on relevant regions" |

### Invalid Evidence
- "We believe our method is better" — opinion, not evidence
- Reference to another paper's results — not from this paper's experiments
- Proof sketch without formal derivation — insufficient for formal claims

## Sufficiency Criteria

### For Performance Claims
- ✅ Supported: Results shown on at least one standard benchmark with standard metrics; improvement is clear and consistent.
- ⚠️ Partial: Results shown but improvement is marginal, inconsistent across settings, or on non-standard benchmark only.
- ❌ Unsupported: No quantitative comparison shown.

### For Necessity Claims ("Module X is essential")
- ✅ Supported: Ablation shows clear performance drop when module is removed/replaced.
- ⚠️ Partial: Ablation shows minor drop, or only on one dataset.
- ❌ Unsupported: No ablation for this module.

### For Generalization Claims
- ✅ Supported: Tested on at least one out-of-distribution or cross-domain setting with positive results.
- ⚠️ Partial: Only tested on very similar settings.
- ❌ Unsupported: Only in-distribution results.

### For Efficiency Claims
- ✅ Supported: Runtime/memory/parameter count reported and compared against baselines.
- ⚠️ Partial: Only one metric reported (e.g., parameters but not runtime).
- ❌ Unsupported: No efficiency measurements.

## Consistency Check

After mapping evidence to claims, verify:
1. Numbers in Abstract/Introduction match numbers in Tables/Figures.
2. Claim wording strength matches evidence strength (do not claim "significantly" if delta is 0.1%).
3. Claims use the same metric names as the tables.
