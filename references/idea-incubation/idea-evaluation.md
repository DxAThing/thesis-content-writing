# Idea Evaluation — Three-Dimension Scoring Framework

## Purpose

Evaluate candidate research ideas along three dimensions before committing to a direction.
This framework adapts the PRD three-perspective diagnostic to academic research.

## Dimension 1: Academic Value

**Core question**: Will this solve a meaningful problem and produce publishable insights?

| Sub-criterion | Score 5 (Excellent) | Score 3 (Good) | Score 1 (Weak) |
|--------------|--------------------|----|---|
| **Problem significance** | Widely acknowledged challenge, high-impact failure cases | Valid problem with moderate community interest | Trivial or overly narrow problem |
| **Novelty of insight** | Genuinely non-obvious; changes how people think about the problem | Clear contribution but within expected design space | Predictable improvement; well-explored technique applied to standard setting |
| **Contribution type strength** | New task definition, or new fundamental mechanism | New module/pipeline with clear advantages | Parameter tuning or minor architectural variant |
| **Competition risk** | No visible concurrent work on this exact approach | Some related concurrent work, but differentiated | Highly crowded direction with strong competitors |

### Scoring Guide
- 5: Strong on all sub-criteria; would likely excite reviewers
- 4: Strong on most; one minor weakness
- 3: Solid overall but no standout strength
- 2: One significant weakness (e.g., low novelty or high competition)
- 1: Multiple weaknesses; likely reviewer pushback

## Dimension 2: Technical Feasibility

**Core question**: Can this actually be built and shown to work?

| Sub-criterion | Score 5 | Score 3 | Score 1 |
|--------------|---------|---------|---------|
| **Technical route clarity** | Clear step-by-step plan; each component has known prior art | Most components clear; 1-2 parts need exploration | No clear technical path; multiple unknowns |
| **Preliminary evidence** | Pilot experiment shows positive signal | Related evidence from similar settings | No evidence; purely hypothetical |
| **Baseline availability** | Strong recent baselines with public code; fair comparison is straightforward | Baselines available but may need re-implementation | No good baselines; hard to do fair comparison |
| **Expected delta** | Large, clearly measurable improvement expected | Moderate improvement, may need careful evaluation | Small or uncertain improvement |

### Scoring Guide
- 5: High confidence the approach works; clear path to strong results
- 4: Likely works with manageable risk
- 3: Feasible but requires significant exploration
- 2: Substantial risk of failure or unclear path
- 1: High chance of dead end

## Dimension 3: Resource Fit

**Core question**: Do we have what it takes to execute this?

| Sub-criterion | Score 5 | Score 3 | Score 1 |
|--------------|---------|---------|---------|
| **Compute requirements** | Manageable with available GPUs; training within days | Needs significant compute but obtainable | Requires large-scale compute beyond budget |
| **Data availability** | Public benchmarks available and sufficient | Data exists but needs processing or partial collection | Data must be created from scratch |
| **Timeline fit** | Achievable within target deadline with buffer | Tight but feasible if no major setbacks | Likely cannot finish on time |
| **Dependency risk** | Self-contained; no blocking external dependencies | 1-2 external dependencies, manageable | Critical dependency on unavailable resource/collaborator |

## Aggregation

Present all three dimensions in a comparison matrix.
Do NOT compute a weighted average — let the user make the trade-off decision.

Recommend the idea with the best balance, but flag specific risks:
- An idea with Academic Value 5 but Feasibility 2 → "High reward, high risk. Worth it if [condition]."
- An idea with all 3s → "Safe choice but may lack excitement."
- An idea with Feasibility 5 but Value 2 → "Easy to do but may not be publishable at top venue."
