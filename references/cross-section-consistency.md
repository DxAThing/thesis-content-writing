# Cross-Section Consistency Check

## Purpose

Detect inconsistencies across sections that hurt reader trust and reviewer impression.
Any sub-skill may load this file when revising or reviewing multi-section drafts.

## Check Items

### 1. Terminology Consistency

- The same concept must use the same term throughout the paper.
- After defining a term, do not switch to a synonym without explanation.
- Common violations: alternating between "feature extraction" and "representation learning" for the same module; mixing "训练集" and "训练数据集" within one chapter.

### 2. Symbol and Notation Consistency

- Each mathematical symbol must have exactly one meaning across the entire paper.
- Define symbols at first use; do not redefine with a different meaning later.
- Check: superscript/subscript conventions, bold/italic conventions, set notation consistency.

### 3. Abbreviation Consistency

- Define the full form at first use in each of: Abstract, Introduction, and main body.
- After definition, always use the abbreviation (do not randomly revert to full form).
- If a new abbreviation is introduced in Method, it should be used consistently in Experiments.

### 4. Cross-Reference Validity

- Every "Section X.Y", "Figure N", "Table M", "Equation (K)" reference must point to an existing target.
- Check that the referenced content matches what the reference claims.
- Flag dangling references (e.g., "as shown in Figure 3" when Figure 3 does not exist).

### 5. Claim Consistency

- Claims in Abstract must align with claims in Introduction and Conclusion.
- Quantitative results cited in Abstract/Introduction must match the actual numbers in Experiments.
- Contribution lists in Introduction must correspond to actual sections in Method.

## How to Run

1. Extract all defined terms, abbreviations, and symbols from Method and Introduction.
2. Scan all sections for usage of each item.
3. Flag any inconsistency as a minor or major issue depending on severity.
4. Report in a structured table:

| Item | Definition Location | Inconsistency Location | Type | Severity |
|------|-------------------|----------------------|------|----------|
| ... | Section X.Y | Section A.B | term/symbol/abbrev/ref | major/minor |
