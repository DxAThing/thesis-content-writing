---
name: research-and-writing
description: >
  Full-cycle research and writing skill. Covers idea incubation, research PRD planning,
  paper storyline design, experiment planning, section-by-section writing (Chinese thesis
  and English paper), claim-evidence alignment, and adversarial self-review.
platform: github-copilot
---

# GitHub Copilot — Usage Guide & Notes

## Installation

Copy the entire `research-and-writing` directory into the user-level skills directory:

```
Windows:
  xcopy /E /I research-and-writing "%USERPROFILE%\.copilot\skills\research-and-writing"

macOS / Linux:
  cp -R research-and-writing "$HOME/.copilot/skills/"
```

Copilot detects the skill automatically via system instructions after installation. No extra configuration is needed.

---

## Trigger Mechanism

Copilot checks each request against registered skill descriptions and activates the matching skill automatically.
The following keywords (in either Chinese or English) trigger the corresponding modules:

| Keywords | Module |
|----------|--------|
| research direction, topic selection, gap, literature survey, 选题, 文献调研 | idea-incubation |
| research plan, technical roadmap, 研究规划, 技术路线 | research-prd |
| outline, storyline, 大纲, 故事线 | paper-storyline |
| experiment design, ablation, 实验设计, 消融实验 | experiment-planning |
| write paper, abstract, introduction, method, 写论文 | paper-writing |
| translate, 翻译, 中转英, 英转中 | translation |
| polish, refine, humanize, de-AI, 润色, 去AI味 | refinement-modes |
| claim, evidence, alignment, 对齐 | claim-evidence |
| review, self-check, 审稿, 自查 | review |

You do **not** need to explicitly say "use the research-and-writing skill" — just describe your task in natural language.

---

## Recommended Prompts

```
# Idea Incubation
Do a literature survey on "audio deepfake detection" and output a landscape map with GAP analysis.

# Writing
Write the Introduction for my paper targeting ICASSP. Prior methods are limited by X, and my contribution is Y.

# Refinement
Polish this Method paragraph — keep technical details, remove AI-sounding patterns: [paste text]

# Review
Review this Abstract as a CVPR reviewer. Point out fatal issues and fixable ones.

# Translation
Translate the following Chinese draft into English academic LaTeX: [paste text]
```

---

## Workflow Notes

### 1. Language Mode Must Be Confirmed Before Writing

When the request involves writing or review, Copilot will ask before proceeding:
- **Chinese thesis** (graduation / degree thesis)
- **English paper** (conference / journal submission)

Answer explicitly. The skill will not proceed without a confirmed mode. Once selected, the mode persists for the session.

### 2. Modules Are Loaded On Demand

Copilot loads only the sub-modules required by the current task (e.g., writing an Abstract will not preload Experiment references).
This is by design to keep context usage efficient. To switch tasks, simply state the new intent.

### 3. Human-in-the-Loop Checkpoints — Do Not Skip

Copilot will pause and wait for user confirmation at these critical decision points:

| Checkpoint | Reason |
|------------|--------|
| GAP analysis results | GAP identification requires user validation against real literature knowledge |
| Idea Card finalization | Sole input for subsequent PRD — errors here propagate downstream |
| Storyline outline | Structural changes are expensive; alignment must happen early |
| Unsupported-claim handling strategy | Involves decisions on running new experiments vs. softening claims |
| Major review issue fix proposals | Structural modifications require human judgment |

### 4. No Fabricated Citations

The skill strictly forbids generating fake references. When a citation is needed but the exact source is unknown, Copilot will mark it as `[TO VERIFY]` or `[待补充]`. The user should verify and fill in the real reference.

### 5. Web Search for Literature

Copilot has access to web-fetching tools and **must proactively use them** during literature-related tasks.
When performing literature surveys, GAP analysis, or verifying citations:
- Use web tools to search arXiv, Google Scholar, Semantic Scholar, and other academic sources.
- Do **not** assume you lack internet access.
- Do **not** ask the user to manually provide paper details when you can look them up.
- Verification priority: HuggingFace dataset pages → arXiv papers → GitHub repos → official docs.
- Always cross-check retrieved information before including it in outputs.

### 6. Context Length Management

When handling multiple large chapters in a single conversation:
- Start a separate conversation for each major chapter (Introduction, Method, Experiments).
- Paste the finalized version of completed chapters back in rather than relying on implicit memory.

### 7. Output Format

- **Chinese thesis**: Default output is plain text ready to paste into Word.
- **English paper**: Default output is LaTeX with no decorative formatting.

To switch (e.g., English output as plain text), state the preference explicitly in the request.

### 8. Diagram Output

| Diagram Type | Format |
|-------------|--------|
| Flowcharts, logic maps | Mermaid (embedded in Markdown, previewable in VS Code) |
| Precise architecture figures | DrawIO XML (open in draw.io) |
| Vector graphics | SVG |
| ❌ ASCII art | Never used |

---

## Known Limitations

- Experiment data analysis requires the user to provide real numerical results. Copilot will not fabricate data points.
- For documents exceeding ~5000 words, submit in sections to avoid exceeding the single-turn context window.
