# Alignment Report Template

```markdown
## Claim-Evidence Alignment Report

> **Paper**: [Title]
> **Report Date**: YYYY-MM-DD
> **Report Mode**: Build / Verify / Fix

### Summary
| Metric | Count |
|--------|-------|
| Total Claims | N |
| ✅ Supported | X |
| ⚠️ Partial | Y |
| ❌ Unsupported | Z |
| **Pass Rate** | X/N (XX%) |

### Detailed Mapping

| # | Claim | Type | Location(s) | Evidence | Status | Action Required |
|---|-------|------|-------------|----------|--------|----------------|
| C1 | [claim text] | Performance | Abstract L3, Intro ¶4 | Table 2 (row 5), Figure 5 | ✅ | None |
| C2 | [claim text] | Necessity | Intro ¶3, Method ¶8 | Table 4 ablation (row 2) | ⚠️ | Soften to "contributes to" |
| C3 | [claim text] | Efficiency | Abstract L5 | ❌ No data | ❌ | Add latency table OR remove claim |

### Consistency Flags
- [ ] [Any numbers that differ between Abstract and Table]
- [ ] [Any metric name mismatches]
- [ ] [Any claim wording stronger than evidence supports]

### Recommended Actions
1. **C2**: Change "is essential for" to "improves" in Introduction ¶3.
2. **C3**: Either add Table 5 with inference speed comparison, or remove efficiency claim from Abstract.
```
