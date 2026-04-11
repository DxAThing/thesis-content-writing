# GAP Analysis Framework

## Purpose

Systematically identify unresolved research challenges from the literature landscape.
A GAP is a concrete technical problem that no current method satisfactorily solves.

## GAP Identification Methods

### Method 1: Cross-Route Limitation Analysis
1. Collect all limitations from the literature landscape.
2. Look for **shared limitations** across different technical routes.
3. A shared limitation that persists despite multiple attempts is a strong GAP signal.

### Method 2: Missing Connection Detection
1. Identify pairs of technical routes that have complementary strengths.
2. Check if anyone has combined them.
3. If no successful combination exists, the interface is a potential GAP.

### Method 3: Failure Case Analysis
1. Look for reported failure cases or scenarios where all current methods degrade.
2. Verify these are non-trivial (they represent real-world needs, not edge cases).
3. Understand the technical root cause of the failure.

### Method 4: Metric Gap Detection
1. Identify important metrics that have not been adequately addressed.
2. Check if existing methods optimize for one metric at the expense of another.
3. A metric trade-off with no satisfactory resolution is a GA P.

## GAP Scoring Rubric

| Score | Importance Level | Criteria |
|-------|-----------------|----------|
| 🔴 High (5) | Major unsolved challenge | Multiple papers acknowledge it; no satisfactory solution; high practical impact |
| 🔴 High (4) | Significant opportunity | Few attempts; existing attempts show promising but insufficient results |
| 🟡 Medium (3) | Valid research direction | Some solutions exist but with notable limitations; room for improvement |
| 🟡 Medium (2) | Incremental but clear | Improvement is possible and measurable, but the gap is narrow |
| ⚪ Low (1) | Minor or nearly solved | Solutions exist and are mostly satisfactory; improvement is marginal |

## Output Template

```markdown
## GAP Analysis: [Topic Name]

> Based on literature landscape dated YYYY-MM-DD

| GAP ID | Description | Related Papers | Best Current Attempt | Why Unresolved | Importance |
|--------|-------------|----------------|---------------------|----------------|------------|
| G1 | [Concrete description] | Paper A, B, C | Paper D tried [approach] but [limitation] | [Root technical reason] | 🔴 High |
| G2 | ... | ... | ... | ... | 🟡 Medium |
| G3 | ... | ... | None attempted | ... | 🔴 High |

### GAP Relationship Map

[Optional: Mermaid diagram showing how GAPs relate to each other]

### Recommended Focus

Based on importance scoring and feasibility assessment:
1. **Primary target**: GAP G_
2. **Secondary target**: GAP G_
3. **Consider combining**: GAP G_ + GAP G_
```

## Quality Criteria

A good GAP analysis should:
- Identify at least 3 distinct GAPs
- Each GAP has a clear technical root cause (not just "needs improvement")
- At least one GAP is rated 🔴 High
- GAPs are not redundant (each targets a genuinely different challenge)
- "Why Unresolved" explains the technical barrier, not just "nobody tried"
