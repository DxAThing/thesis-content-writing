# Idea Card Template

## Purpose

The Idea Card is the final output of the idea incubation process.
It serves as the input to `research-prd/SKILL.md` for systematic research planning.

## Template

```markdown
# Idea Card: [Concise Name]

## One-Line Position
> Solve [what technical challenge] in [which field/task],
> via [what method direction],
> expected to achieve [what contribution/advantage].

## Core GAP
- **GAP ID**: [from GAP analysis]
- **Source papers**: [papers that expose this gap]
- **Best current attempt**: [paper that came closest, and what they did]
- **Why insufficient**: [specific technical reason the gap remains]

## Core Insight
> [One sentence describing the key technical insight that motivates your approach.
>  This should answer: "Why do we believe our approach can work where others failed?"]

## Expected Contributions
1. [Contribution 1: type + brief description]
2. [Contribution 2: type + brief description]
3. [Optional: Contribution 3]

## Key Uncertainties
- [ ] **Hypothesis 1**: [what you assume is true but haven't verified]
  - Validation method: [how to test this before full-scale experiments]
- [ ] **Hypothesis 2**: [another assumption]
  - Validation method: [how to test]

## Three-Dimension Scores
| Dimension | Score | Key Reason |
|-----------|-------|------------|
| Academic Value | X/5 | ... |
| Technical Feasibility | X/5 | ... |
| Resource Fit | X/5 | ... |

## Resource Requirements
- **Compute**: [GPU type × count × estimated hours]
- **Data**: [datasets needed, availability status]
- **Timeline**: [estimated total duration]
- **Dependencies**: [external tools, collaborators, access requirements]

## Related Work Anchors
- [Paper A] (Author, Year) — [relationship: builds upon / contrasts with / complements]
- [Paper B] (Author, Year) — [relationship]
- [Paper C] (Author, Year) — [relationship]

## Next Step
→ Proceed to `research-prd/SKILL.md` for systematic research planning.
```

## Usage Notes

- The Idea Card should be self-contained: a reader unfamiliar with the incubation process
  should understand the idea from the card alone.
- The "Core Insight" field is the most important: it should be concise, non-trivial,
  and clearly differentiated from prior work.
- "Key Uncertainties" should focus on assumptions that, if false, would invalidate the approach.
  Do not list implementation-level uncertainties here.
