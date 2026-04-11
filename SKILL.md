---
name: thesis-content-writing
description: >
  Full-cycle research paper writing skill. Covers research idea incubation (literature landscape,
  GAP analysis, idea evaluation), research PRD planning, paper storyline design, experiment planning,
  section-by-section writing for both Chinese thesis and English conference/journal papers,
  claim-evidence alignment, and adversarial self-review.
  Use when the user asks about: research ideas, literature survey, gap analysis, paper planning,
  thesis/paper writing, drafting, polishing, de-AI, logic checks, figure briefs, experiment design,
  claim-evidence checks, self-review, or any academic writing task.
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
- Choice 1 → Use the **Chinese Thesis Writing** rules below (the core of this skill).
- Choice 2 → Use the **English Paper Writing** references in `references/paper-writing/`.

### Intent Routing Table

| User Intent | Route To |
|------------|----------|
| idea, 研究方向, 选题, brainstorm, 文献调研, gap, literature survey | `references/idea-incubation/` — see [Idea Incubation](#idea-incubation) |
| 研究规划, 研究PRD, 技术路线, research plan, 可行性 | `references/research-prd/` — see [Research PRD](#research-prd) |
| storyline, paper story, 逻辑骨架, 大纲, outline | `references/paper-storyline/` — see [Paper Storyline](#paper-storyline) |
| 实验设计, 实验规划, ablation, experiment plan | `references/experiment-planning/` — see [Experiment Planning](#experiment-planning) |
| 写论文, draft, rewrite, 润色, abstract, introduction, method | **Ask Language Mode** → Chinese: use modes below / English: `references/paper-writing/` |
| claim, evidence, 对齐, alignment | `references/claim-evidence/` — see [Claim-Evidence Alignment](#claim-evidence-alignment) |
| 审稿, review, 自查, 审核精修, defense, 去AI味 | **Ask Language Mode** → Chinese: Review-Pass mode below / English: `references/review/` |

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

### Output Convention

- Default output is paste-ready finished content, not verbose explanations.
- For edits, return full revised text unless the user asks for diff-style output.
- Never fabricate citations, experiment data, or author/DOI information.
- When information is insufficient, mark `[待补充]` instead of guessing.

### Sub-Skill Loading Rule

- Load only the references needed for the current task.
- Load examples on demand, not preloaded.

---

# Chinese Thesis Content Writing

## Overview

Use this section for a content-first Chinese thesis workflow:
- draft Chinese thesis sections for manual paste into Word
- refine existing text without over-editing
- humanize AI-sounding or translation-like prose
- run a high-threshold logic check
- prepare figure briefs, captions, and callout sentences
- output formulas as bare LaTeX without math delimiters

This skill assumes the user already has a template. Do not default to editing the `.docx` file itself.

## Core Rule

Optimize for paste-ready content, not fancy formatting.

Default outputs should be:
- plain text that can be copied into Word or saved as `.txt`
- concise figure guidance that helps the user insert or create a figure later
- formulas written as raw LaTeX only

Do not fabricate references, results, numbers, or citations.

## Verification and Citation Rule

Apply sentence-level checking before finalizing any thesis text.

For each sentence:
- identify whether it is factual, interpretive, methodological, or purely connective
- re-check factual and literature-backed statements before keeping them
- remove or soften claims that cannot be supported

For claims that are supported by literature, use inline citation format with full-width Chinese parentheses in Chinese thesis prose:

```text
（Author, Year, DOI: xxx）
```

Examples:

```text
（Vaswani et al., 2017, DOI: 10.48550/arXiv.1706.03762）
（He et al., 2016, DOI: 10.1109/CVPR.2016.90）
```

Hard rules:
- repeatedly verify all facts to avoid AI hallucinations and fabrications.
- do not invent author names, years, or DOI values
- **WHEN CITATIONS ARE MISSING OR INCOMPLETE:** proactively use runSubagent with the 'Explore' agent to search for and retrieve complete literature references (author names, years, DOI, publication venue). Do NOT leave placeholders like `[TO ADD CITATION]`.
- the agent MUST execute literature search automatically when it encounters:
  - incomplete citations (e.g., missing DOI or publication year)
  - sentences with strong factual claims but no source nearby
  - any reference mentioned without full details
- use search queries targeting publication databases (arXiv, Google Scholar, IEEE Xplore, conference proceedings) to retrieve verified DOIs and full citations
- if a DOI is not verified after search, do not output a fake complete citation
- if support is missing after thorough search, use a placeholder such as `[TO VERIFY CITATION]` only as a last resort.
- if a sentence makes a strong claim but no source is available, rewrite it conservatively or flag it for verification
- if a sentence draws a conclusion, the conclusion must be backed by one of the following: literature support, experiment support, or explicit theoretical analysis; literature-review summaries may rely on the cited literature itself, but should still avoid unsupported over-generalization
- this verification scope covers ALL thesis sections, not only literature-review chapters; problem-analysis sections, research-background sections, and method-motivation sections commonly contain factual claims (e.g., properties of a model, capabilities of a technique, or observed phenomena) that also require citation support or conservative softening

## Writing Convention Rule

Separate "de-AI" issues from "writing convention" issues.

Writing convention covers academic presentation rules such as:
- when a paper has a clear work name, paper title, or established method name, prefer that name at first mention instead of writing only "Author et al."
- when an English technical term first appears, give the full English name and a Chinese explanation or translation, then use the abbreviation or Chinese term consistently afterward
- keep technical names, abbreviations, and citation references stable across nearby sections
- do not insert spaces between Chinese characters and Western letters/numbers (including standalone abbreviations such as "ViT" or "LoRA"); write them adjacently, e.g., "ViT模型"、"LoRA微调"、"第3章"
- in Chinese prose, always use paired full-width quotation marks（“”和‘’）; do not use half-width straight quotes (" " or ' ')

Do not treat these as mere style preferences. They are part of thesis writing规范.

Quick classification examples:
- belongs to Humanize / De-AI:
  - bad: `在本文的问题设定中，AI生成图像检测、AI生成图像溯源、闭集设定以及后文的方法建模并非彼此孤立的概念。`
  - better: `本文讨论的 AI 生成图像检测、AI 生成图像溯源和闭集设定，本质上都围绕来源判别展开。`
- belongs to Humanize / De-AI:
  - bad: `视觉基础模型真正提出的问题不是“能不能用”，而是“如何改造后再用”。`
  - better: `视觉基础模型路线的核心挑战在于：如何在保留迁移能力的前提下，使其适配来源判别任务。`
- belongs to Humanize / De-AI:
  - bad: `现有研究已经证明“可检测”与“可迁移”，却还没有充分解决“可稳定区分来源”这一更细粒度的问题。`
  - better: `现有研究已经表明，相关方法可以完成真伪检测，也具备一定跨来源迁移能力，但在多来源设定下的细粒度来源判别稳定性仍未得到充分解决。`
- belongs to Humanize / De-AI:
  - bad: generic uses of `链路` or `实际落点`
  - better: use a concrete object such as `传播过程`, `成像过程`, `研究重心`, or `真正解决的问题`
- belongs to Humanize / De-AI:
  - bad: `局部扰动增强的基本思想，是不直接破坏图像中的全部判别信息。`
  - better: `局部扰动增强的基本思想是不直接破坏图像中的全部判别信息。`
- belongs to Humanize / De-AI:
  - bad: `原型学习的基本思想，是为每个类别学习一个具有代表性的中心表示。`
  - better: `原型学习的基本思想是为每个类别学习一个具有代表性的中心表示。`
- belongs to Humanize / De-AI:
  - bad: `后续用原型学习稳住来源边界的设计就缺乏根据。`
  - better: `后续围绕原型学习重组来源判别几何的设计就缺乏根据。`
- belongs to Humanize / De-AI:
  - bad: `空间域、频域以及局部纹理与全局语义的关系，正是把问题收束到“检测线索如何转化为溯源线索”的几个关键切面。`
  - better: `空间域、频域以及局部纹理与全局语义的关系，共同说明了检测线索如何进一步转化为可用于溯源的判别线索。`
- belongs to Humanize / De-AI:
  - bad: `问题在于，来源识别需要的往往不是这种高层语义一致性。`
  - better: `来源识别更关心生成过程中的来源差异，高层语义一致性本身不足以支撑这一任务。`
- belongs to Humanize / De-AI:
  - bad: `对强语义表征模型而言，语义线索往往更显著。`
  - better: `对以视觉基础模型为代表、擅长提取高层语义的表征模型而言，语义线索往往更显著。`
- belongs to Humanize / De-AI:
  - bad: `增强所依据的区域划分并不依赖 ViT 的切块设置。`
  - better: `该策略先在图像层面完成局部重排，再把增强后的完整图像送入视觉基础模型进行编码。`
- belongs to Verification / Citation:
  - bad: `原型学习在细粒度分类中的作用，主要体现在它能够降低局部噪声和偶然偏差对决策边界的干扰。`
  - better: `近年的细粒度分类研究已经开始显式利用类中心约束来压缩类内方差，并拉开细微的类间差异（Yao et al., 2024, DOI: 10.48550/arXiv.2407.04243）。从这个角度看，原型学习有助于围绕类别中心组织空间结构。`
- belongs to Logic / Review:
  - bad: `不过，对本文的闭集溯源任务而言，频域线索仍然只是来源信息的一部分。`
  - better: `本文后续方法并不单独围绕频域统计建模。这里讨论频域线索，主要是为了说明来源信息也可能体现在全局统计分布中。`
- belongs to Writing Convention:
  - bad: `Wang 等提出了……`
  - better: `Wang 等在《CNN-generated images are surprisingly easy to spot... for now》中……`
- belongs to Writing Convention:
  - bad: `本文采用 CLIP 与 LoRA。`
  - better: `本文采用 Contrastive Language-Image Pretraining（CLIP，对比语言-图像预训练）与 Low-Rank Adaptation（LoRA，低秩适配）。`

## Mode Selection

Choose the smallest mode that fits the request.

### 1. Draft Mode

Use when the user asks for a new chapter, section, subsection, abstract, conclusion, or method description.

Default behavior:
- write the prose in Chinese
- make it formal, specific, and thesis-appropriate
- prefer full paragraphs over outline fragments
- keep each paragraph focused on one main point
- add figure notes or formulas only if useful

### 2. Refine Mode

Use when the user already has a draft and wants it polished.

Default behavior:
- preserve meaning, structure, and author intent
- edit only where clarity, grammar, logic, or academic tone truly improves
- if the text is already solid, keep it close to the original

Do not rewrite aggressively just to create visible change.
However, if the draft contains clear redundancy, repeated claims across sections, pseudo-classification, or section-introduction filler, structural reduction is allowed and preferred over cosmetic polishing.

### 3. Humanize Mode

Use when the user asks for "renwei", "humanize", "de-AI", "qu AI wei", "runse", or wants the prose to feel less machine-written.

Default behavior:
- remove empty rhetoric and inflated significance claims
- reduce translation-like sentence structure
- avoid repetitive connectors and mechanical list phrasing
- remove AI-style template phrasing without turning the prose into spoken or conversational Chinese
- vary sentence rhythm and avoid repeated fixed templates such as "不是……而是……", "不仅……还……", and "首先……其次……再次……" when they appear too often
- keep contrastive sentence frames only when the contrast carries real argumentative weight; if a direct statement can express the same meaning, prefer the direct statement
- avoid decorative contrast frames such as "不只是……更重要的是……" and "不再只是……也可以……" when they merely repackage a normal declarative sentence
- weaken over-connected causal chains such as "通过……从而……进而……"; when the logic is already clear, prefer shorter clauses or direct juxtaposition
- avoid subject-predicate breaks created by commas in ordinary declarative sentences, such as "X 的基本思想，是……"
- avoid formulaic diagnostic openers such as "问题在于" when the sentence can begin directly from the actual claim
- define a technical term once, then use it directly instead of repeatedly wrapping concepts in quotation marks
- cut paragraph-ending bridge sentences that add no new information, such as stock lines about "providing a foundation" or "offering a basis" unless the sentence carries real content
- prefer specific verbs over empty safe verbs when possible; reduce overuse of generic verbs such as "进行", "实现", and "提供"
- preserve technical terms and domain meaning
- keep the result suitable for direct paste into Word
- keep the tone academically natural; do not inject colloquial fillers, exaggerated emotion, or chat-style phrasing just to look human
- if the machine-like feel comes from structure rather than wording, delete or merge redundant material instead of merely rephrasing it
- when strengthening a judgment, prefer mechanism-grounded academic wording such as "不再成立", "难以维持", or "其实证支撑减弱"; do not use colloquial emphatics like "直接崩了"
- describe method motivation truthfully; if a design choice is for training feasibility, compute budget, or annotation limits, say so directly instead of drifting into generic "deployment" or "landing" language
- remove abstract packaged nouns with weak information value, such as generic uses of "链路", "落点", or similar catch-all words, unless they refer to a real technical object like an imaging pipeline or propagation pipeline
- avoid question-and-answer style contrasts such as "能不能用" / "如何改造后再用" and sloganized paired labels such as "可检测" / "可迁移" when they make the prose sound translated or machine-compressed
- avoid defensive process clarifications that answer a question the reader has not yet asked; if the core workflow is already clear, state the process once and stop
- in related-work sections, do not stop at "谁做了什么"; after representative citations, prefer adding a limitation, a condition, or an implication
- do not force every surveyed subtopic into the same paragraph count or the same "intro-contribution-limit" rhythm; compress background and expand directly relevant methods
- do not use em dashes (——) anywhere in thesis prose; when removing an em dash, always rewrite the sentence to ensure it reads naturally with the replacement punctuation (colon, comma, "即", "例如", or restructured clause); paired em dashes used as parenthetical insertions must also be rewritten into comma-delimited appositions, parentheses, or restructured sentences

Humanize examples:
- bad: `在本文的问题设定中，AI生成图像检测、AI生成图像溯源、闭集设定以及后文的方法建模并非彼此孤立的概念。`
- better: `本文讨论的 AI 生成图像检测、AI 生成图像溯源和闭集设定，本质上都围绕来源判别展开。`
- bad: `视觉基础模型真正提出的问题不是“能不能用”，而是“如何改造后再用”。`
- better: `视觉基础模型路线的核心挑战在于：如何在保留迁移能力的前提下，使其适配来源判别任务。`
- bad: `ViT 处理的不是整幅图像的像素网格，而是固定大小的 patch 序列。`
- better: `ViT 将输入图像切分为固定大小的 patch 序列进行处理。`
- bad: `位置编码的作用不只是标记 patch 的位置，更重要的是恢复全局结构的组织关系。`
- better: `位置编码用于补充 patch 的空间位置信息，也帮助模型恢复全局结构的组织关系。`
- bad: `这意味着视觉基础模型不再只是通用分类器，也可以成为来源识别的表征底座。`
- better: `这意味着视觉基础模型已经具备支撑来源识别表征学习的潜力。`
- bad: `在视觉任务中，LoRA 的应用方式往往不是为了完全替代原始骨干，而是为了用较少参数调节模型关注什么。`
- better: `在视觉任务中，LoRA 通常承担受控调节器的角色，用较少参数调整模型关注什么。`
- bad: `原型学习的基本思想，是为每个类别学习一个具有代表性的中心表示。`
- better: `原型学习的基本思想是为每个类别学习一个具有代表性的中心表示。`
- bad: `后续用原型学习稳住来源边界的设计就缺乏根据。`
- better: `后续围绕原型学习重组来源判别几何的设计就缺乏根据。`
- bad: `空间域、频域以及局部纹理与全局语义的关系，正是把问题收束到……`
- better: `空间域、频域以及局部纹理与全局语义的关系，共同说明了……`
- bad: `问题在于，来源识别需要的往往不是这种高层语义一致性。`
- better: `来源识别更关心生成过程中的来源差异，高层语义一致性本身不足以支撑这一任务。`
- bad: `对强语义表征模型而言，语义线索往往更显著。`
- better: `对以视觉基础模型为代表、擅长提取高层语义的表征模型而言，语义线索往往更显著。`
- bad: `不过，对本文的闭集溯源任务而言，频域线索仍然只是来源信息的一部分。`
- better: `本文后续方法并不单独围绕频域统计建模。这里讨论频域线索，主要是为了说明来源信息也可能体现在全局统计分布中。`
- bad: `现有研究已经证明“可检测”与“可迁移”……`
- better: `现有研究已经表明，相关方法可以完成真伪检测，也具备一定跨来源迁移能力……`
- bad: `但就现有文献的实际落点而言……`
- better: `但就现有文献的研究重心而言……`
- bad: generic `链路`
- better: replace with `过程`, `环节`, `传播过程`, or delete the word if the verb already implies process
- belongs to Humanize / De-AI (em dash overuse):
  - bad: `这些伪影主要来源于GAN架构中普遍使用的上采样操作——转置卷积和最近邻上采样等操作会在频域引入规律性的能量分布异常。`
  - better: `这些伪影主要来源于GAN架构中普遍使用的上采样操作，例如转置卷积和最近邻上采样，它们会在频域引入规律性的能量分布异常。`
  - bad: `传统的"训练分类器区分真假"范式存在不对称学习的问题——分类器容易过度拟合训练集中特定生成模型的伪影模式。`
  - better: `传统的"训练分类器区分真假"范式存在不对称学习的问题：分类器容易过度拟合训练集中特定生成模型的伪影模式。`
  - bad (paired em dash): `上述四项研究内容——视觉基础模型选择与参数高效适配、输入端语义扰动、优化端原型学习——与统一来源分类框架共同构成了本文方法的完整技术方案。`
  - better: `上述四项研究内容（视觉基础模型选择与参数高效适配、输入端语义扰动、优化端原型学习）与统一来源分类框架共同构成了本文方法的完整技术方案。`

### 4. Logic-Check Mode

Use when the user asks for a logic check, consistency pass, or wants only real problems called out.

Default behavior:
- use a high threshold
- report only substantive issues
- ignore cosmetic style preferences

Focus on:
- contradictions
- undefined terms or symbols
- claim-evidence mismatch
- missing transitions that block understanding
- inconsistent naming of the same concept
- duplicated claims that appear in multiple sections
- pseudo-categories whose items are actually causes, effects, or scenario conditions of one another
- section-introduction or section-ending sentences that only restate the heading without adding content
- over-connected causal chains that make the logic softer rather than clearer
- literature review paragraphs that only summarize citations neutrally without extracting any limitation or implication
- conclusion-like sentences whose basis is missing, unclear, or weaker than the wording suggests

### 5. Review-Pass Mode

Use when the user wants a chapter or thesis section reviewed from an advisor, reviewer, or defense perspective.

Default behavior:
- summarize the section's claimed contribution or purpose
- separate major issues from minor improvements
- explain which issues are fixable by revision and which are structural
- keep the advice practical and chapter-specific

Hard review rule:
- every conclusion-like sentence must have an identifiable basis
- acceptable bases are:
  - literature support
  - experiment support
  - explicit theoretical analysis
- in literature-review sections, cited representative work may itself serve as the basis, but the reviewer should still flag overextended conclusions that go beyond the cited evidence
- if a conclusion sentence has no clear basis, flag it as a real review issue rather than a style preference

### 6. Figure-Brief Mode

Use when the user needs help inserting or designing a figure.

Default behavior:
- give a technical figure brief, not decorative art direction
- specify insertion point, purpose, elements, suggested caption, and one sentence that introduces the figure in the prose
- optionally give an English figure title if the user wants one

Prefer:
- workflow diagrams
- architecture diagrams
- module relationship diagrams
- experiment setup figures
- result explanation figures

### 7. Formula Mode

Use when the user asks for formulas or wants formulas inserted into a section.

Default behavior:
- output raw LaTeX only
- do not wrap with `$`, `$$`, `\(` `\)`, or `\[` `\]`
- keep notation consistent with the surrounding text
- add a short Chinese explanation when useful

## Output Rules

### Section Drafts

When drafting a section:
- write the section body in Chinese
- **CRITICAL: Do NOT insert empty blank lines between paragraphs.** Output contiguous text blocks to match standard Word indent formatting directly. Paragraphs should be separated only by natural paragraph breaks (when pasted into Word, indent formatting will handle spacing automatically). This rule applies to all output, including when saving to `.txt` files.
- avoid Markdown unless the user explicitly asks for it
- avoid bullet lists inside the final prose unless the genre truly requires them
- **CRITICAL: When any sentence needs a citation, AUTOMATICALLY search for and retrieve the complete reference (full author names, year, DOI, publication venue) before finalizing the text.** Do not use `[TO ADD CITATION]` or other placeholders for missing references. Use runSubagent to search academic databases if internal knowledge is incomplete.
- when a sentence depends on published work, attach the citation in `（Author, Year, DOI: xxx）` format
- run one final pass to check whether each factual sentence is either supported, softened, or marked for verification

### Refinement Passes

When refining existing text:
- return the revised full text unless the user asks for diff-style edits
- keep commentary short
- mention only the most important changes

### Figure Guidance

For each figure, provide:
- insertion point
- figure purpose
- key visual elements
- suggested caption
- prose callout sentence

If the figure does not exist yet, provide a concise creation brief rather than pretending the figure already exists.

### Formulas

Correct:

```text
L = \sum_{i=1}^{n}(y_i - \hat{y}_i)^2
```

Incorrect:

```text
$L = \sum_{i=1}^{n}(y_i - \hat{y}_i)^2$
```

## Review-Refinement Loop (审核-精修循环)

Use when the user asks for "审核-精修循环", "审稿-精修", or "review-refine loop". This is a composite workflow that runs multiple review passes, collects all issues, applies fixes in one batch, then re-reviews until no major issues remain.

### Trigger

Activate this loop when:
- the user explicitly requests a review-refine cycle
- the user says "审核直到通过" or similar

### Passes (run in order)

Each pass reads the CURRENT version of text (not the original draft). Collect all findings into a single issue list before making any edits.

#### Pass 1: Reader Test (读者测试)

Simulate a first-time reader of the chapter. Check:
- can the argument be followed without re-reading?
- are there undefined terms used before introduction?
- are cross-references (e.g., "如 1.4.3 节所述") pointing to real content?
- is the reading flow blocked by abrupt transitions or missing context?
- are there redundant paragraphs or duplicated claims across sections?

#### Pass 2: De-AI / Humanize Check (去 AI 味)

Scan for patterns listed in Humanize Mode (Mode 3) and `references/refinement-modes.md`. Focus on:
- mechanical parallel structures ("首先……其次……再次……", "不是……而是……" repeated)
- decorative contrast frames that repackage direct statements
- over-connected causal chains ("通过……从而……进而……")
- subject-predicate comma breaks ("X 的基本思想，是……")
- generic verbs ("进行", "实现", "提供") used as fillers
- abstract catch-all nouns ("链路", "落点") without concrete referent
- paragraph-ending bridge sentences that add no information
- section-introduction filler that merely restates the heading
- pseudo-taxonomies where items are actually cause-effect or condition-amplification

#### Pass 3: Writing Convention Check (学术规范)

Check rules that are part of thesis 写作规范, not mere style:
- first mention of an English term must give full English name + Chinese translation, then shorten consistently
- first mention of a published work should prefer its established method name or paper title, not bare "Author et al."
- abbreviation and term consistency across nearby sections
- citation format consistency: `（Author, Year, DOI: xxx）`

#### Pass 4: Citation and Fact Verification (引用与事实核查)

Apply rules from `references/citation-verification.md`:
- **scan every sentence and classify it as factual, conclusion-like, interpretive, or connective; every factual or conclusion-like sentence must be explicitly checked for citation support — this applies to ALL sections of the thesis, not only literature-review chapters**
- every factual claim has a citation or is softened
- no invented author names, years, or DOIs
- every conclusion-like sentence has an identifiable basis (literature, experiment, or theoretical analysis)
- strong comparative/evaluative claims ("widely recognized", "state of the art") have evidence or are weakened
- if a factual or conclusion-like sentence lacks a citation and the claim is non-trivial, use runSubagent to search for supporting literature before deciding whether to add a citation or soften the claim
- if incomplete citations are found, use runSubagent to search and fill them before flagging
- **mandatory re-verification after any citation is added or corrected:** immediately re-check that the author names, year, DOI string, and publication venue retrieved by runSubagent are internally consistent and the DOI resolves to the correct paper; do not treat a retrieved citation as verified unless this check passes explicitly

#### Pass 5: Logic Check (逻辑检查)

Apply high-threshold rules from Logic-Check Mode (Mode 4):
- contradictions between sections
- claim-evidence mismatch
- undefined terms or symbols
- inconsistent naming of the same concept
- conclusion sentences whose basis is missing or weaker than the wording

#### Pass 6: Reviewer Pass (审稿人视角)

Simulate a thesis defense reviewer. Apply rules from Review-Pass Mode (Mode 5):
- summarize the section's claimed contribution
- separate major issues from minor improvements
- flag unsupported conclusions as real issues, not style preferences
- check whether each contribution claim in 1.6 (创新点) is backed by method content in 1.5 and literature analysis in 1.3-1.4

### After All Passes: Issue Consolidation

- merge duplicates (same issue found in multiple passes)
- classify each issue as: **major** (must fix), **minor** (should fix), or **cosmetic** (optional)
- discard cosmetic issues unless the count is very low and they are easy to fix

### Fix Phase

- apply all major and minor fixes using `multi_replace_string_in_file` on the individual section `.txt` files
- re-concatenate the master draft via terminal command after fixes
- do NOT fix cosmetic-only issues unless explicitly asked

### Re-Review Phase

- re-read the fixed text
- **if any citations were added or modified during the Fix Phase, re-run Pass 4 in full (not compressed) before the general re-check:** confirm that each new or changed citation has correct author names, year, DOI, and that the DOI matches the paper being cited; any citation that fails this check must be flagged as a major issue
- run a compressed re-check (all 6 passes in one scan) on all other changes
- if new major issues are found, fix and re-check again
- if only minor or cosmetic issues remain, report them to the user and declare the loop passed

### Output Shape

```text
[审核结果 - 第 N 轮]

重大问题：
1. ...
2. ...

次要问题：
1. ...

已修复：
- ...
- ...

结论：审核通过 / 需要再修一轮
```

## File-Oriented Workflow

If the user wants files created, write the final content to `.txt` files directly without empty lines between paragraphs.

Suggested structure when none is provided:
- `thesis/chapters/ch01-introduction.txt`
- `thesis/chapters/ch02-related-work.txt`
- `thesis/chapters/ch03-method.txt`
- `thesis/chapters/ch04-experiments.txt`
- `thesis/figures/figure-notes.txt`

If the user wants finer granularity, split by section first (e.g., `1.1.txt`, `1.2.txt`), and finally synthesize/combine them into a single master draft file (e.g., `第一章_总稿.txt`) at the end.

### Concatenation Rule

When combining multiple section files into a master draft, use terminal commands (e.g., `Get-Content` in PowerShell or `cat` in bash) to concatenate the files instead of reading each file into the chat context and writing a new file via `create_file`. This avoids wasting context window on large verbatim copies and is faster and less error-prone. After concatenation, use `read_file` and `replace_string_in_file` to make any needed edits on the resulting file.

## Response Shapes

### Draft a Section

Use:
- main text
- optional figure brief
- optional formulas

### Refine a Section

Use:
- revised text
- short revision notes only if useful

### Logic Check

Use:
- "No substantive issues found" if the section is already solid
- otherwise a short list of real issues only

### Review Pass

Use:
- summary
- strengths
- major issues
- revision advice

## What to Borrow From Other Writing Workflows

This skill intentionally combines several reusable prompt patterns:
- conservative Chinese thesis polishing
- de-AI or humanization for Word-ready Chinese prose
- high-threshold logic review
- reviewer-style strategic feedback
- figure brief and title generation

Keep these as internal modes, not separate bloated outputs.

## References

Read [references/output-format.md](references/output-format.md) for exact output shapes.

Read [references/chinese-thesis-style.md](references/chinese-thesis-style.md) for tone, paragraphing, and anti-slop guidance.

Read [references/refinement-modes.md](references/refinement-modes.md) when the user explicitly asks for humanization, conservative polishing, logic checking, figure titles, or a reviewer-style pass.

Read [references/citation-verification.md](references/citation-verification.md) when the user wants literature-backed writing, inline citations, or sentence-level fact checking.

---

# English Paper Writing (ML/CV/NLP)

When the user selects **English paper mode**, load the references below.
These are adapted from the [Pengsida methodology](https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e).

## Section Writing Guides

Read these references for section-specific guidance:

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

## Core English Writing Principles

- One paragraph, one message.
- Reverse-outline verification: after writing, extract each paragraph's topic sentence; the sequence should form a coherent argument.
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

# English Paper Review (5-Dimension)

When the user selects English mode for review, load `references/review/`:

- [references/review/five-dimension-review.md](references/review/five-dimension-review.md) — 5-dimension adversarial review checklist
- [references/review/six-pass-review-loop.md](references/review/six-pass-review-loop.md) — 6-pass review-refine loop (also used for Chinese thesis)
- [references/review/review-output-template.md](references/review/review-output-template.md) — Review output format templates

### English 5-Dimension Review

1. **Contribution**: New knowledge? Non-obvious novelty?
2. **Writing Clarity**: Reproducible? Consistent terms? One paragraph, one message?
3. **Experimental Strength**: Meaningful improvements over strong baselines?
4. **Evaluation Completeness**: All key ablations? Strong baselines included?
5. **Method Design Soundness**: Realistic setting? Robust without per-case tuning?

---

# Shared Utilities

These cross-cutting references can be loaded by any module when needed:

- [references/cross-section-consistency.md](references/cross-section-consistency.md) — Cross-section terminology, notation, abbreviation, and cross-reference consistency checks
- [references/latex-engineering.md](references/latex-engineering.md) — LaTeX table/figure/formula formatting conventions and recommended packages
