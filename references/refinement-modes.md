# Refinement Modes

This file condenses the most useful prompt ideas from the external writing repository into reusable modes for this skill.

## 1. Conservative Polish

Use when the user wants a clean academic rewrite but does not want visible over-editing.

Rules:
- preserve the original structure unless it is clearly broken
- change only what improves clarity, grammar, logic, or tone
- if a sentence is already good, keep it
- do not replace words just to look "more advanced"
- preserve the author's technical framing
- if two nearby sections are making the same point, merge or delete instead of paraphrasing both
- if a list of "problems" is actually a cause-effect chain or a condition-amplification chain, rewrite it as an argument rather than preserving the fake parallel structure

Good for:
- chapter polishing
- advisor feedback cleanup
- final pass before copying into Word

Verification overlay:
- if the paragraph contains factual or literature-backed claims, check each sentence before finalizing
- preserve confirmed citations
- add missing citation markers instead of bluffing

## 2. Humanize / De-AI

Use when the user wants the text to feel less machine-generated.

Remove these patterns:
- empty emotional or grandiose wording
- generic significance claims without evidence
- translation-like long modifier chains
- repetitive list transitions
- forced symmetry and overly even sentence rhythm
- over-connected causal chains built from "通过", "从而", "进而", "于是", or similar connectives
- word swapping that changes tone but not meaning
- repeated fixed contrast frames such as "不是……而是……" and "不仅……还……"
- decorative contrast frames such as "不只是……更重要的是……" and "不再只是……也可以……" when they only wrap a direct statement
- overuse of quoted labels that package ordinary concepts as if they were new terms
- paragraph endings that only say "this lays a foundation" without adding information
- generic verb stacks built around words like "进行", "实现", and "提供"
- section-introduction paragraphs that merely announce what the heading already tells the reader
- pseudo-taxonomies created only to satisfy a tidy multi-point structure
- repeated restatement of the same core claim in both a concept section and a later method section
- false sharpening that relies on colloquial force rather than analytical precision
- generic motivation language that blurs training constraints, inference constraints, and deployment concerns
- abstract catch-all nouns such as "链路" or "落点" when they do not identify a concrete technical object
- translated capability labels such as "可检测", "可迁移", "可解释" when they are used as slogan-like packages rather than real analysis
- question-and-answer contrasts such as "能不能用" and "如何改造后再用" in thesis prose
- subject-predicate breaks created by commas, such as "X 的基本思想，是……" or "Y 的关键作用，是……"
- defensive workflow disclaimers that do not add real information after the process is already clear
- formulaic diagnostic openers such as "问题在于" when the sentence can begin directly from the actual claim
- undefined umbrella labels such as "强语义表征模型" when the reader is not told which class of models is being discussed

Preserve these:
- core technical terms
- notation
- discipline-specific vocabulary
- factual content

High-level rewrite rule:
- make the prose plainer, tighter, and more native
- never make it casual or chatty
- remove AI-style template phrasing without turning the text into spoken Chinese
- vary sentence length and structure enough to avoid mechanical repetition
- do not add emotional adverbs or conversational fillers merely to simulate human style
- when a passage is bloated, prefer deletion, merging, or reordering over sentence-by-sentence paraphrase
- if a claim needs to be stronger, sharpen the mechanism or evidence, not the slang level
- in related-work prose, do not stop after saying what a paper did; add a limitation, a condition, or an implication when the citation is representative
- do not preserve paragraph symmetry for its own sake; if one subtopic matters more, let it take more space and a different internal rhythm

Verification overlay:
- do not remove a citation just to make a sentence shorter
- if a strong claim has no support, soften it or mark it for verification

Writing-norm overlay:
- if a work has a clear method name, paper title, or established public name, prefer that at first mention over bare "Author et al."
- if an English term first appears, write its full name and Chinese explanation once, then shorten consistently

Examples:
- de-AI issue:
  - bad: `ViT 处理的不是整幅图像的像素网格，而是固定大小的 patch 序列。`
  - better: `ViT 将输入图像切分为固定大小的 patch 序列进行处理。`
- de-AI issue:
  - bad: `位置编码的作用不只是标记 patch 的位置，更重要的是恢复全局结构的组织关系。`
  - better: `位置编码用于补充 patch 的空间位置信息，也帮助模型恢复全局结构的组织关系。`
- de-AI issue:
  - bad: `这意味着视觉基础模型不再只是通用分类器，也可以成为来源识别的表征底座。`
  - better: `这意味着视觉基础模型已经具备支撑来源识别表征学习的潜力。`
- de-AI issue:
  - bad: `在视觉任务中，LoRA 的应用方式往往不是为了完全替代原始骨干，而是为了用较少参数调节模型关注什么。`
  - better: `在视觉任务中，LoRA 通常承担受控调节器的角色，用较少参数调整模型关注什么。`
- de-AI issue:
  - bad: `但就现有文献的实际落点而言……`
  - better: `但就现有文献的研究重心而言……`
- de-AI issue:
  - bad: `现有研究已经证明“可检测”与“可迁移”……`
  - better: `现有研究已经表明，相关方法可以完成真伪检测，也具备一定跨来源迁移能力……`
- de-AI issue:
  - bad: `局部扰动增强的基本思想，是不直接破坏图像中的全部判别信息。`
  - better: `局部扰动增强的基本思想是不直接破坏图像中的全部判别信息。`
- de-AI issue:
  - bad: `后续用原型学习稳住来源边界的设计就缺乏根据。`
  - better: `后续围绕原型学习重组来源判别几何的设计就缺乏根据。`
- de-AI issue:
  - bad: `空间域、频域以及局部纹理与全局语义的关系，正是把问题收束到“检测线索如何转化为溯源线索”的几个关键切面。`
  - better: `空间域、频域以及局部纹理与全局语义的关系，共同说明了检测线索如何进一步转化为可用于溯源的判别线索。`
- de-AI issue:
  - bad: `问题在于，来源识别需要的往往不是这种高层语义一致性。`
  - better: `来源识别更关心生成过程中的来源差异，高层语义一致性本身不足以支撑这一任务。`
- de-AI issue:
  - bad: `对强语义表征模型而言，语义线索往往更显著。`
  - better: `对以视觉基础模型为代表、擅长提取高层语义的表征模型而言，语义线索往往更显著。`
- de-AI issue:
  - bad: `增强所依据的区域划分并不依赖 ViT 的切块设置。`
  - better: `该策略先在图像层面完成局部重排，再把增强后的完整图像送入视觉基础模型进行编码。`
- verification issue:
  - bad: `原型学习在细粒度分类中的作用，主要体现在它能够降低局部噪声和偶然偏差对决策边界的干扰。`
  - better: `近年的细粒度分类研究已经开始显式利用类中心约束来压缩类内方差，并拉开细微的类间差异（Yao et al., 2024, DOI: 10.48550/arXiv.2407.04243）。从这个角度看，原型学习有助于围绕类别中心组织空间结构。`
- logic issue:
  - bad: `不过，对本文的闭集溯源任务而言，频域线索仍然只是来源信息的一部分。`
  - better: `本文后续方法并不单独围绕频域统计建模。这里讨论频域线索，主要是为了说明来源信息也可能体现在全局统计分布中。`
- writing-convention issue:
  - bad: `Wang 等提出……`
  - better: `Wang 等在《CNN-generated images are surprisingly easy to spot... for now》中指出……`
- writing-convention issue:
  - bad: `本文采用 CLIP。`
  - better: `本文采用 Contrastive Language-Image Pretraining（CLIP，对比语言-图像预训练）。`

## 3. Logic Check

Use a high threshold.

Only flag:
- contradictions
- undefined terms, variables, or symbols
- claim-evidence mismatch
- missing bridge between paragraphs
- inconsistent naming
- duplicated argumentation across sections
- fake parallel categories that should be rewritten as a single causal argument
- background paragraphs that imply a later method component uses a certain clue, while the later method never models that clue explicitly

Do not flag:
- optional wording improvements
- style preferences
- changes that are only "maybe better"

Also check:
- whether a literature-backed sentence actually includes a verified citation
- whether citation formatting is consistent with `（Author, Year, DOI: xxx）`
- whether every conclusion-like sentence is backed by literature, experiment, or explicit theoretical analysis
- whether the wording of the conclusion overreaches the actual evidence

## 4. Review Pass

Use when the user wants a chapter reviewed from a tough but constructive perspective.

Structure:
- summary of the section's purpose
- strengths
- major issues
- revision advice

Separate:
- fixable presentation problems
- deeper structural or evidential problems

Hard review rule:
- treat unsupported conclusion sentences as substantive issues
- a conclusion sentence should point back to one of three bases:
  - literature support
  - experiment support
  - explicit theoretical analysis
- literature review sections may conclude from the cited body of work, but should not over-generalize beyond what the cited studies can carry

The goal is not to sound harsh. The goal is to be accurate and useful.

## 5. Figure Brief

Use when the user needs help preparing a thesis figure.

Provide:
- insertion point
- purpose
- components
- relation arrows or flow
- suggested caption
- callout sentence in the surrounding prose

Preferred style:
- clean technical diagram
- white background if a design direction is needed
- readable labels
- no poster aesthetics unless explicitly requested

## 6. Figure Title

If the user needs an English figure title:
- keep it short
- avoid filler like "This figure shows"
- use a noun phrase when possible
- use sentence case only if it is a full sentence

Examples:
- `System architecture of the proposed method`
- `Ablation results on the feature selection module`

## 7. Practical Invocation Patterns

Examples of requests that should trigger these modes:
- "Polish this section but keep my wording as much as possible."
- "Make this sound less AI-generated."
- "Only tell me real logic problems."
- "Review this section like an advisor."
- "Give me a figure brief and a caption for this subsection."
- "Check every sentence and keep only claims with verified support."
