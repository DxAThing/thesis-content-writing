# Literature Landscape Analysis Guide

## Purpose

Build a structured map of the research field that organizes related work by **technical route**,
enabling systematic identification of gaps and opportunities.

## Search Strategy

### Source Priority
1. **arXiv** — latest preprints, fastest signal
2. **Google Scholar** — broad coverage, citation metrics
3. **Semantic Scholar** — API-friendly, related paper recommendations
4. **DBLP** — verified venue/year data

### Search Procedure
1. Start with the user's keywords and any provided seed papers.
2. From seed papers, follow both citing and cited papers (2 hops max).
3. Search for recent surveys/tutorials in the topic (they provide ready-made taxonomy).
4. Filter to papers from the last 2-3 years unless a foundational older paper is essential.
5. Target 15-25 papers total, then select 3-5 per technical route.

### How to Group by Technical Route
- A "technical route" is a family of methods sharing the same core mechanism or representation.
- Examples: "NeRF-based methods", "diffusion-based methods", "GAN-based methods", "transformer-based methods".
- If a paper combines two routes, classify under the primary one and note the crossover.

## Output Template

```markdown
## Literature Landscape: [Topic Name]

> Search date: YYYY-MM-DD
> Total papers reviewed: N
> Grouped into K technical routes

### Tech Route A: [Route Name]

**Core idea**: [One-sentence description of the shared mechanism]

| Paper | Year | Venue | Core Contribution | Key Limitation | Citations |
|-------|------|-------|-------------------|----------------|-----------|
| [Short Name] (Author et al.) | 20XX | CVPR | ... | ... | ~NNN |
| ... | ... | ... | ... | ... | ... |

**Route trend**: [Is this route ascending/plateauing/declining? Why?]

### Tech Route B: [Route Name]
[Same structure]

### Emerging / Underexplored Directions
- **Direction X**: Only 1-2 papers explore this. Potentially high value because...
- **Direction Y**: ...
```

## Per-Paper Contribution Analysis

For each paper in the landscape, extract:

| Dimension | Description | How to Extract |
|-----------|-------------|----------------|
| **What** | Method/task/data contribution | Read abstract + contribution list |
| **Why works** | Core insight or mechanism | Read method section intro paragraph |
| **Limitation** | Remaining problems | Read limitations section, future work, or reviewer comments if available |
| **Relationship** | Connection to other papers in landscape | Check if it cites/builds-on/contrasts other papers in the table |

## Quality Criteria

A good landscape analysis should:
- Cover the major technical routes (no blind spots)
- Include the most-cited works AND the most recent works
- Identify at least one emerging/underexplored direction
- Note conflicting findings or open debates in the field

## Web Search for Papers

If exa or firecrawl MCPs are available, use the `deep-research` or `exa-search` skills to
execute the actual paper search. Use `category: "research paper"` when available.

Example query pattern:
```
web_search_exa(query: "[topic] survey arXiv 2024 2025", numResults: 10, category: "research paper")
```

This skill (`research-and-writing`) handles the analysis, structuring, and writing after
the papers are collected. The search execution is handled by `deep-research` / `exa-search`.
