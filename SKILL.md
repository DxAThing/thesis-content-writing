---
name: research-and-writing
description: >
  Full-cycle research and writing skill for both Chinese thesis and English conference/journal papers.
  Covers: research idea incubation (literature landscape, GAP analysis, idea evaluation),
  research PRD planning, paper storyline design, experiment planning, section-by-section writing,
  translation, condensing/expanding, polishing, de-AI/humanization, architecture diagrams,
  experiment visualization, figure/table captions, experiment analysis, claim-evidence alignment,
  and adversarial self-review.
  Use when the user asks about: research ideas, literature survey, gap analysis, paper planning,
  thesis/paper writing, drafting, polishing, de-AI, logic checks, figure briefs, experiment design,
  claim-evidence checks, self-review, translation, condensing, expanding, architecture diagrams,
  experiment visualization, or any academic writing task.
---

# Research Paper Writing Skill

## Routing

This is the unified entry point for a complete research writing workflow.
Identify the user's intent and route to the right section or reference accordingly.

### Language Mode Selection (Mandatory for Writing & Review)

When the user's request involves writing or review, you **must** ask before proceeding:

> "你当前的写作目标是？
> 1. **中文学位论文**（毕业论文 / 学位论文）
> 2. **英文投稿论文**（会议 / 期刊投稿）
>
> 请告诉我你的选择。"

Rules:
- Never guess the language mode from the user's input language.
- Once selected, persist for the session unless the user explicitly switches.
- Choice 1 → Apply **Chinese Thesis** conventions from `references/chinese-thesis-style.md`.
- Choice 2 → Apply **English Paper** conventions from `references/english-paper-style.md`.

### Intent Routing Table

| User Intent | Route To |
|------------|----------|
| idea, 研究方向, 选题, brainstorm, 文献调研, gap, literature survey | `references/idea-incubation/` — see [Idea Incubation](#idea-incubation) |
| 研究规划, 研究PRD, 技术路线, research plan, 可行性 | `references/research-prd/` — see [Research PRD](#research-prd) |
| storyline, paper story, 逻辑骨架, 大纲, outline | `references/paper-storyline/` — see [Paper Storyline](#paper-storyline) |
| 实验设计, 实验规划, ablation, experiment plan | `references/experiment-planning/` — see [Experiment Planning](#experiment-planning) |
| 翻译, translate, 中转英, 英转中 | Writing Mode: Translation → `references/paper-writing/translation.md` |
| 缩写, 扩写, condense, expand, shorten, lengthen | Writing Mode: Condensing/Expanding → `references/paper-writing/condensing-expanding.md` |
| 写论文, draft, rewrite, abstract, introduction, method, experiments, related work, conclusion | **Ask Language Mode** → Section guides in `references/paper-writing/` |
| 润色, polish, refine | **Ask Language Mode** → Writing Mode: Refine |
| 去AI味, humanize, de-AI, renwei | Writing Mode: Humanize → `references/refinement-modes.md` |
| 逻辑检查, logic check, consistency | Writing Mode: Logic Check |
| 架构图, architecture diagram, framework figure | `references/paper-writing/architecture-diagrams.md` |
| 实验绘图, visualization, chart recommendation | `references/paper-writing/experiment-visualization.md` |
| 图标题, 表标题, caption, figure title, table title | `references/paper-writing/figure-table-captions.md` |
| 实验分析, experiment analysis, data analysis | `references/paper-writing/experiment-analysis.md` |
| claim, evidence, 对齐, alignment | `references/claim-evidence/` — see [Claim-Evidence Alignment](#claim-evidence-alignment) |
| 审稿, review, 自查, 审核精修, defense, reviewer simulation | **Ask Language Mode** → `references/review/` |

### Global Drawing Convention

| Scenario | Tool | Format |
|----------|------|--------|
| Flowcharts, architecture diagrams, logic maps | **Mermaid** | Embedded in Markdown |
| Precise technical figures, pipeline diagrams | **DrawIO** | `.drawio` file |
| Vector graphics requiring fine control | **SVG** | `.svg` file |
| ❌ Forbidden | ASCII art / character drawings | Never use |

### Human-in-the-Loop Checkpoints

Pause and request user confirmation at these decision points:
- Idea incubation: GAP analysis results, Idea evaluation matrix, Idea Card finalization
- Research PRD: v1 concept doc confirmed before entering v2
- Paper storyline: Outline finalization
- Writing: Language mode selection
- Claim-evidence: Handling strategy for unsupported claims
- Review: Major issue fix proposals

### Core Output Convention

- Default output is paste-ready finished content, not verbose explanations.
- For edits, return full revised text unless the user asks for diff-style output.
- Never fabricate citations, experiment data, or author/DOI information.
- When information is insufficient, mark `[待补充]` / `[TO VERIFY]` instead of guessing.
- Load only the references needed for the current task.
- Load examples on demand, not preloaded.

---

# Writing Modes

Choose the smallest mode that fits the request. All modes apply to both Chinese and English unless noted.

## 1. Draft Mode

Use when the user asks for a new chapter, section, subsection, abstract, conclusion, or method description.

Rules:
- Write in the selected language mode (Chinese or English)
- Prefer full paragraphs over outline fragments
- Keep each paragraph focused on one main point
- Add figure notes or formulas only if useful
- Chinese: formal, specific, thesis-appropriate; load `references/chinese-thesis-style.md`
- English: clear, precise, conference/journal quality; load `references/english-paper-style.md`

## 2. Refine Mode

Use when the user already has a draft and wants it polished.

Rules:
- Preserve meaning, structure, and author intent
- Edit only where clarity, grammar, logic, or academic tone truly improves
- If the text is already solid, keep it close to the original
- Do not rewrite aggressively just to create visible change
- If the draft contains clear redundancy, repeated claims, pseudo-classification, or filler, structural reduction is preferred over cosmetic polishing

Load `references/refinement-modes.md` § Conservative Polish for detailed rules.

## 3. Humanize / De-AI Mode

Use when the user asks for "humanize", "de-AI", "去AI味", "renwei", or wants less machine-like prose.

Rules:
- Remove empty rhetoric and inflated significance claims
- Reduce mechanical patterns (repetitive connectors, forced symmetry, template phrasing)
- Preserve technical terms and domain meaning
- Never make the prose casual or chatty
- If machine feel comes from structure, delete or merge redundant material instead of rephrasing
- Em dashes: remove and rewrite naturally (applies to both languages)

Load `references/refinement-modes.md` § Humanize for full pattern list and examples.

Chinese-specific patterns: load `references/chinese-thesis-style.md`
English-specific patterns: load `references/english-paper-style.md`

## 4. Translation Mode

Use when the user wants to translate between Chinese and English.

Load `references/paper-writing/translation.md` for:
- 中→英 (Chinese draft → English LaTeX): academic rewrite, proper escaping, tense rules
- 英→中 (English LaTeX → Chinese text): faithful direct translation for comprehension
- 中→中 (Chinese draft → formal Chinese): academic rewrite for Word
- Quality self-check protocols

## 5. Condensing / Expanding Mode

Use when the user wants to adjust text length without changing meaning.

Load `references/paper-writing/condensing-expanding.md` for:
- Condensing: reduce ~5-15 words by compressing syntax and removing fillers
- Expanding: add ~5-15 words by explicating implicit logic and enhancing connections

## 6. Logic-Check Mode

Use when the user asks for a logic check, consistency pass, or wants only real problems called out.

Rules:
- Use a high threshold; default assume the text has been through multiple rounds of editing
- Report only substantive issues
- Ignore cosmetic style preferences

Focus on:
- Contradictions
- Undefined terms or symbols
- Claim-evidence mismatch
- Missing transitions that block understanding
- Inconsistent naming of the same concept
- Duplicated claims across sections
- Pseudo-categories whose items are actually causes, effects, or conditions of one another
- Section-intro or section-ending sentences that only restate the heading
- Over-connected causal chains that weaken rather than strengthen the logic
- Literature review paragraphs that only summarize without extracting limitations
- Conclusion sentences whose basis is missing or weaker than the wording

## 7. Review-Pass Mode

Use when the user wants a chapter reviewed from an advisor, reviewer, or defense perspective.

Rules:
- Summarize the section's claimed contribution or purpose
- Separate major issues from minor improvements
- Explain which issues are fixable by revision and which are structural
- Keep the advice practical and chapter-specific
- Every conclusion sentence must have a basis: literature, experiment, or theoretical analysis

For full review-refine loop: load `references/review/six-pass-review-loop.md`
For review output format: load `references/review/review-output-template.md`

## 8. Reviewer Simulation Mode

Use when the user wants the paper reviewed from a conference/journal reviewer perspective.

Rules:
- Read as a critical but fair reviewer for the target venue
- Assess: contribution significance, writing clarity, experimental strength, evaluation completeness, method design soundness
- Output: Summary, Strengths, Weaknesses (with specific evidence), Rating, Strategic advice
- Distinguish "fatal issues" from "fixable-in-revision issues"
- Score must reflect actual contribution level; do not default to harsh preset

Load `references/review/five-dimension-review.md` for the 5-dimension checklist.

## 9. Figure-Brief Mode

Use when the user needs help inserting or designing a figure.

Output:
- Insertion point
- Figure purpose
- Key visual elements
- Suggested caption
- Prose callout sentence
- Optional English figure title

For architecture diagram generation: load `references/paper-writing/architecture-diagrams.md`
For experiment chart recommendations: load `references/paper-writing/experiment-visualization.md`
For caption formatting: load `references/paper-writing/figure-table-captions.md`

## 10. Experiment Analysis Mode

Use when the user wants experiment results analyzed and written up.

Load `references/paper-writing/experiment-analysis.md` for:
- Data-driven analysis writing
- LaTeX `\paragraph{}` structure for experiment sections
- Truthfulness rules: all conclusions must come from data
- Output format with analysis paragraphs and Chinese back-translation

## 11. Formula Mode

Use when the user asks for formulas or wants formulas inserted into a section.

Output raw LaTeX only. No `$`, `$$`, `\(`, `\)`, `\[`, `\]` delimiters.
Keep notation consistent with the surrounding text.
Add a short explanation in the user's language when useful.

---

# Verification and Citation Rules

Apply sentence-level checking before finalizing any text (both Chinese and English).

For each sentence:
- Classify as factual, interpretive, methodological, or connective
- Re-check factual and literature-backed statements before keeping them
- Remove or soften claims that cannot be supported

Citation format:
- Chinese thesis: `（Author, Year, DOI: xxx）` (full-width parentheses)
- English paper: `\cite{key}` or `(Author et al., Year)` per venue style

Hard rules:
- Never invent author names, years, or DOI values
- **When citations are missing or incomplete:** proactively use runSubagent to search for and retrieve complete references (author names, years, DOI, publication venue). Do NOT leave placeholders like `[TO ADD CITATION]`.
- The agent MUST execute literature search automatically when it encounters:
  - incomplete citations (missing DOI or publication year)
  - sentences with strong factual claims but no source nearby
  - any reference mentioned without full details
- Use search queries targeting arXiv, Google Scholar, IEEE Xplore, conference proceedings
- If a DOI is not verified after search, do not output a fake citation
- If support is missing after thorough search, use `[待补充]` / `[TO VERIFY CITATION]` as last resort
- If a sentence makes a strong claim but no source is available, rewrite conservatively or flag for verification
- Conclusion sentences must be backed by: literature, experiment, or explicit theoretical analysis
- This verification covers ALL sections, not only literature review

Load `references/citation-verification.md` for the full workflow.

---

# Writing Convention Rules

Separate "de-AI" issues from "writing convention" issues. Convention rules are not mere style preferences.

## Shared Conventions (Both Languages)

- First mention of an abbreviation → give full name, then abbreviate consistently
- Published works → prefer method name or paper title at first mention, not just "Author et al."
- Keep technical terms, abbreviations, and citation references stable across sections
- Do not treat convention rules as optional style suggestions

## Chinese-Specific Conventions

- No spaces between CJK and Western letters/numbers: "ViT模型"、"LoRA微调"、"第3章"
- Use paired full-width quotation marks: ""和''
- Full-width Chinese punctuation: ，。；：
- First English term → full English name + Chinese translation, then abbreviation
- Do not use em dashes (——) in thesis prose; rewrite with colons, commas, or restructured clauses

Load `references/chinese-thesis-style.md` for the complete style guide.

## English-Specific Conventions

- No contractions in academic prose (use "does not", not "doesn't")
- Avoid possessive forms for method/model names (use "the performance of X", not "X's performance")
- Present tense for methods and findings; past tense only for specific historical events
- Avoid AI-overused vocabulary: leverage, delve, tapestry, etc.
- No `\textbf{}` or `\emph{}` for emphasis in body text; use sentence structure
- Do not expand common domain abbreviations (keep LLM, not Large Language Models)
- Preserve existing LaTeX commands (`\cite{}`, `\ref{}`, `\eg`, `\ie`)

Load `references/english-paper-style.md` for the complete style guide.

---

# Output Rules

## Section Drafts

When drafting a section:
- Chinese: contiguous paragraphs, **no empty blank lines between paragraphs**, no Markdown formatting, suitable for direct paste into Word
- English: LaTeX-ready content with proper escaping (`%`, `_`, `&`)
- **When any sentence needs a citation, AUTOMATICALLY search and retrieve the complete reference before finalizing.** Use runSubagent if internal knowledge is incomplete.
- Run one final pass to check whether each factual sentence is supported, softened, or marked for verification

## Refinement Passes

When refining existing text:
- Return the revised full text unless the user asks for diff-style edits
- Keep commentary short; mention only the most important changes

## Figure Guidance

For each figure, provide:
- Insertion point, figure purpose, key visual elements, suggested caption, prose callout sentence
- If the figure does not exist yet, provide a creation brief

## Formulas

Correct: `L = \sum_{i=1}^{n}(y_i - \hat{y}_i)^2`
Incorrect: `$L = \sum_{i=1}^{n}(y_i - \hat{y}_i)^2$`

---

# Review-Refinement Loop (审核-精修循环)

Use when the user asks for "审核-精修循环", "审稿-精修", "review-refine loop", or "审核直到通过".

This is a composite workflow that runs 6 review passes, collects all issues, applies fixes, then re-reviews until no major issues remain. Works for both Chinese thesis and English papers.

Load `references/review/six-pass-review-loop.md` for the full 6-pass protocol.

### Pass Summary

1. **Reader Test**: reading flow, undefined terms, cross-references, redundancy
2. **De-AI / Humanize**: mechanical patterns, template phrasing (load `references/refinement-modes.md`)
3. **Writing Convention**: terminology, abbreviation, citation format consistency
4. **Citation & Fact Verification**: sentence classification, citation support (load `references/citation-verification.md`)
5. **Logic Check**: contradictions, claim-evidence mismatch, naming consistency
6. **Reviewer Pass**: contribution claims, evidence backing, structural issues

### Output Shape

```text
[审核结果 - 第 N 轮] / [Review Result - Round N]

重大问题 / Major Issues:
1. ...

次要问题 / Minor Issues:
1. ...

已修复 / Fixed:
- ...

结论：审核通过 / 需要再修一轮
Conclusion: Passed / Needs another round
```

---

# File-Oriented Workflow

If the user wants files created, write the final content to `.txt` files directly.

Suggested structure when none is provided:
- `thesis/chapters/ch01-introduction.txt`
- `thesis/chapters/ch02-related-work.txt`
- `thesis/chapters/ch03-method.txt`
- `thesis/chapters/ch04-experiments.txt`
- `thesis/figures/figure-notes.txt`

For finer granularity, split by section (e.g., `1.1.txt`, `1.2.txt`), then concatenate into a master draft (e.g., `第一章_总稿.txt`).

### Concatenation Rule

Use terminal commands (`Get-Content` in PowerShell or `cat` in bash) to concatenate files instead of reading each into context. After concatenation, use `read_file` and `replace_string_in_file` for edits.

---

# Section Writing Guides

These references provide section-specific guidance. They apply to both Chinese and English papers.
The section structure, logic flow, and argumentation principles are language-agnostic;
apply the language-specific style conventions from `references/chinese-thesis-style.md` or `references/english-paper-style.md` to the final prose.

- [references/paper-writing/abstract.md](references/paper-writing/abstract.md) — Abstract: 3 templates (Challenge→Contribution/Insight)
- [references/paper-writing/introduction.md](references/paper-writing/introduction.md) — Introduction: backward reasoning + 4+3+4 template system
- [references/paper-writing/related-work.md](references/paper-writing/related-work.md) — Related Work: organization strategies
- [references/paper-writing/method.md](references/paper-writing/method.md) — Method: three-element module structure (Motivation→Design→Advantage)
- [references/paper-writing/experiments.md](references/paper-writing/experiments.md) — Experiments: 3 core questions + table rules
- [references/paper-writing/conclusion.md](references/paper-writing/conclusion.md) — Conclusion
- [references/paper-writing/does-my-writing-flow-source.md](references/paper-writing/does-my-writing-flow-source.md) — Paragraph clarity checker
- [references/paper-writing/paper-review.md](references/paper-writing/paper-review.md) — Self-review checklist

## Examples Library

Read [references/paper-writing/examples/index.md](references/paper-writing/examples/index.md) for the full example catalog.
Load specific examples on demand:

- `references/paper-writing/examples/abstract/` — 3 abstract template examples
- `references/paper-writing/examples/introduction/` — 13 introduction examples (task intro + challenge + pipeline)
- `references/paper-writing/examples/method/` — 9 method examples (three-element structure, module design)

## Core Principles (Both Languages)

- One paragraph, one message.
- Reverse-outline verification: extract each paragraph's topic sentence; the sequence should form a coherent argument.
- Module description follows the triad: **Motivation → Design → Technical Advantage**.
- Tables use booktabs style (no vertical lines, minimal horizontal lines).
- Every major claim must be supported by experimental evidence (see claim-evidence alignment).

---

# Idea Incubation

When the user asks about research ideas, topic selection, literature survey, or gap analysis,
load and follow the references in `references/idea-incubation/`:

- [references/idea-incubation/literature-landscape.md](references/idea-incubation/literature-landscape.md) — Literature landscape search strategy and output template
- [references/idea-incubation/gap-analysis.md](references/idea-incubation/gap-analysis.md) — GAP identification methods and scoring rubric
- [references/idea-incubation/idea-evaluation.md](references/idea-incubation/idea-evaluation.md) — Three-dimension evaluation framework (academic value / feasibility / resource fit)
- [references/idea-incubation/idea-card-template.md](references/idea-incubation/idea-card-template.md) — Final Idea Card output template

### Idea Incubation Workflow

1. **Anchor direction**: Ask the user to describe their research interest
2. **Literature landscape**: Search and classify core papers by technical route
3. **Contribution enumeration**: Extract what/why-works/limitation per paper
4. **GAP analysis**: Identify unresolved challenges across routes
5. **Idea seed generation**: Propose 2-3 candidate ideas from GAPs
6. **Idea evaluation**: Score with three-dimension matrix
7. **Human-in-the-loop**: User reviews → feedback → iterate until confirmed
8. **Idea Card finalization**: Output structured Idea Card

---

# Research PRD

When the user asks about research planning, technical roadmap, or feasibility,
load and follow the references in `references/research-prd/`:

- [references/research-prd/concept-doc-template.md](references/research-prd/concept-doc-template.md) — v1 research concept document template
- [references/research-prd/landing-doc-template.md](references/research-prd/landing-doc-template.md) — v2 research landing document template
- [references/research-prd/three-perspective.md](references/research-prd/three-perspective.md) — Three-dimension diagnostic detailed guide

### Research PRD Workflow

1. **Three-dimension diagnostic**: Academic value → Technical feasibility → Resource constraints
2. **v1 concept document**: Direction alignment (user must confirm before v2)
3. **v2 landing document**: Executable technical plan + experiment design + timeline

---

# Paper Storyline

When the user asks about paper story, outline, or logic skeleton,
load and follow the references in `references/paper-storyline/`:

- [references/paper-storyline/backward-forward-reasoning.md](references/paper-storyline/backward-forward-reasoning.md) — Backward reasoning + forward narrative guide
- [references/paper-storyline/introduction-logic-map.md](references/paper-storyline/introduction-logic-map.md) — Introduction template catalog (Part A/B/C with multiple versions)
- [references/paper-storyline/storyline-templates.md](references/paper-storyline/storyline-templates.md) — 5 common paper type storyline skeletons

### Paper Storyline Workflow

1. **Backward reasoning**: Answer 4 key questions about contributions
2. **Forward narrative**: Build the story arc (Task→Challenge→Solution→Advantage)
3. **Introduction logic map**: Select template combination (A-VX + B-VX + C-VX)
4. **Full-paper outline**: Each section's core message + paragraph roles
5. **Claim-evidence pre-mapping**: Map each claim to its evidence source

---

# Experiment Planning

When the user asks about experiment design, ablation planning, or experiment logs,
load and follow the references in `references/experiment-planning/`:

- [references/experiment-planning/experiment-design-matrix.md](references/experiment-planning/experiment-design-matrix.md) — Claim-Experiment mapping matrix template
- [references/experiment-planning/ablation-checklist.md](references/experiment-planning/ablation-checklist.md) — Ablation derivation rules and template
- [references/experiment-planning/experiment-log-template.md](references/experiment-planning/experiment-log-template.md) — Structured experiment recording template

### Experiment Planning Workflow

1. **Extract claims** from storyline/outline
2. **Design experiments**: Map each claim to a validation experiment
3. **Generate ablation checklist** from pipeline modules
4. **Prepare experiment log** templates for structured recording
5. **Track and update** as a living document throughout research

---

# Claim-Evidence Alignment

When the user asks about claim-evidence checks or alignment,
load and follow the references in `references/claim-evidence/`:

- [references/claim-evidence/claim-extraction.md](references/claim-evidence/claim-extraction.md) — Rules for identifying claims in paper text
- [references/claim-evidence/evidence-mapping.md](references/claim-evidence/evidence-mapping.md) — Criteria for evidence sufficiency and consistency
- [references/claim-evidence/alignment-report-template.md](references/claim-evidence/alignment-report-template.md) — Output report template

### Three Modes

- **Build**: Extract all claims from Abstract + Introduction, build mapping table
- **Verify**: Check each claim for sufficient evidence from experiments
- **Fix**: Soften unsupported claims or flag experiments to add

---

# Review (5-Dimension + 6-Pass Loop)

When the user selects review mode, load `references/review/`:

- [references/review/five-dimension-review.md](references/review/five-dimension-review.md) — 5-dimension adversarial review checklist
- [references/review/six-pass-review-loop.md](references/review/six-pass-review-loop.md) — 6-pass review-refine loop (works for both Chinese thesis and English paper)
- [references/review/review-output-template.md](references/review/review-output-template.md) — Review output format templates (both languages)

### 5-Dimension Review (for conference/journal papers)

1. **Contribution**: New knowledge? Non-obvious novelty?
2. **Writing Clarity**: Reproducible? Consistent terms? One paragraph, one message?
3. **Experimental Strength**: Meaningful improvements over strong baselines?
4. **Evaluation Completeness**: All key ablations? Strong baselines included?
5. **Method Design Soundness**: Realistic setting? Robust without per-case tuning?

### 6-Pass Review Loop (for both Chinese thesis and English paper)

See [Review-Refinement Loop](#review-refinement-loop-审核-精修循环) above.

---

# Shared Utilities

These cross-cutting references can be loaded by any module when needed:

- [references/cross-section-consistency.md](references/cross-section-consistency.md) — Cross-section terminology, notation, abbreviation, and cross-reference consistency checks
- [references/latex-engineering.md](references/latex-engineering.md) — LaTeX table/figure/formula formatting conventions and recommended packages
- [references/output-format.md](references/output-format.md) — Exact output shapes for all modes
- [references/refinement-modes.md](references/refinement-modes.md) — Conservative polish, humanize/de-AI, logic check, and review pass detailed rules
- [references/chinese-thesis-style.md](references/chinese-thesis-style.md) — Chinese thesis tone, paragraphing, and anti-slop guidance
- [references/english-paper-style.md](references/english-paper-style.md) — English paper tone, word choice, de-AI patterns, and LaTeX conventions
- [references/citation-verification.md](references/citation-verification.md) — Citation workflow and sentence-level fact checking
