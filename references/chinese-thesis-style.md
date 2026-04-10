# Chinese Thesis Style

## Goal

Write Chinese thesis prose that sounds like a careful human author, not a translated or AI-padded draft.

## Tone

- Be formal and precise.
- Prefer concrete claims over inflated significance language.
- Explain the point of each paragraph early.
- Keep terminology stable across nearby sections.

## Paragraphing

Use one paragraph for one main purpose:
- background
- method step
- result interpretation
- limitation
- transition

Avoid packing several unrelated ideas into the same paragraph.

## Common Problems to Remove

### 1. Empty importance claims

Cut or replace phrases that sound grand but say little.

Bad pattern:
- claims that something has "great theoretical and practical significance" without saying why
- generic statements about "laying a foundation for future work"

Better pattern:
- state what problem is addressed
- state what changed
- state what evidence supports the claim

### 2. Repetitive connectors

Do not rely on the same transitions in every paragraph.

Bad pattern:
- every paragraph starts with "first", "second", "in addition", "finally"

Better pattern:
- vary the sentence openings naturally
- let the logic of the paragraph do most of the transition work

### 3. Translation-like syntax

Avoid:
- long chains of modifiers before the head noun
- excessive passive voice
- mechanical list phrasing when a normal paragraph would read better

Prefer:
- shorter Chinese clauses
- explicit subjects when they improve clarity
- natural sentence flow over rigid translation structure
- define broad technical labels before using them; avoid umbrella expressions such as `强语义表征模型` unless the model family has been made explicit

### 4. Vague technical description

Avoid:
- "a series of operations"
- "related methods"
- "further optimization was conducted"

Prefer:
- name the input
- name the process
- name the output

### 5. Repeated sentence frames

Avoid overusing the same contrast or enumeration skeleton across nearby paragraphs.

Bad pattern:
- repeating "不是……而是……" many times in one section
- repeating "不仅……还……" or "首先……其次……再次……" in mechanically parallel form
- relying on "一方面……另一方面……" whenever two points need to be contrasted

Better pattern:
- mix direct statements, subordinate clauses, apposition, and contrastive clauses
- allow sentence length to vary naturally instead of keeping every sentence in the same range
- rewrite some contrast relations implicitly rather than announcing every logical turn

### 6. Over-packaged concepts

Avoid wrapping ordinary analytical labels in quotation marks again and again.

Bad pattern:
- repeatedly introducing terms like "X表征" or "Y问题" in quotes inside the same page
- giving every paragraph a newly packaged label without adding analytical value

Better pattern:
- define a term once if it is really needed
- then use it directly and consistently
- reserve quotation marks for true first mentions, contested expressions, or deliberate emphasis

### 7. Empty bridge sentences

Do not end every paragraph with a stock sentence that only signals transition.

Bad pattern:
- "this provides a foundation for the following section"
- "this offers a basis for subsequent analysis"
- "this lays the groundwork for later modeling"

Better pattern:
- add a concrete implication if one exists
- or end the paragraph on its substantive claim and move on

### 8. Verb choice

Prefer precise verbs when they improve readability.

Avoid overusing:
- "进行"
- "实现"
- "提供"
- "开展"

Prefer:
- verbs that directly name the action, relation, or effect
- wording that shows what the method actually does, not just that some process occurred

### 8.5 Abstract Catch-All Words

Do not lean on broad packaged words when they do not name a concrete mechanism.

Bad pattern:
- using words like "链路", "落点", "抓手" as general fillers
- writing "实际落点" when the sentence really means "真正解决的问题" or "评价目标"

Better pattern:
- keep "成像链路", "传播链路" and similar expressions when they are real technical objects
- otherwise replace them with the concrete process, target, or constraint being discussed

Examples:
- bad: `但就现有文献的实际落点而言，一个突出事实是……`
- better: `但就现有文献的研究重心而言，一个突出事实是……`
- bad: `模型和传播链路一变，线索就可能减弱。`
- better: `模型和传播过程一变，线索就可能减弱。`
- bad: `后续用原型学习稳住来源边界的设计就缺乏根据。`
- better: `后续围绕原型学习重组来源判别几何的设计就缺乏根据。`
- bad: `空间域、频域以及局部纹理与全局语义的关系，正是把问题收束到……`
- better: `空间域、频域以及局部纹理与全局语义的关系，共同说明了……`

### 9. Section-introduction filler

Do not use a whole paragraph merely to announce what a section will cover if the heading already carries that information.

Bad pattern:
- "本节将从以下几个方面展开"
- "下面对相关内容进行概念梳理"
- "本章主要介绍……并为后文奠定基础"
- "本节先对任务边界作概念梳理，重点说明……的关系"
- "下面将从以下几个维度展开分析"

Better pattern:
- start directly from the first substantive claim
- if orientation is needed, compress it into half a sentence and attach it to real content
- trust the section heading to carry the structural preview

### 10. Pseudo-classification

Do not force parallel subheadings when the underlying logic is actually causal, layered, or conditional.

Bad pattern:
- listing cause, symptom, and scenario amplification as three equal "problems"
- splitting one central contradiction into several near-synonymous subpoints only to make the outline look complete
- writing "四个方面" where two items are symptoms, one item is the cause, and the last item is only the condition that amplifies the problem

Better pattern:
- identify the core contradiction first
- then explain its concrete manifestations
- then explain which settings amplify it

Example:
- bad: `本文面临四个困难：语义重叠导致混淆、语义差异导致离散、表征目标不一致、大规模场景放大困难。`
- better: `核心矛盾在于表征的语义主导倾向。其表现包括跨来源语义重叠导致的类间混淆，以及来源内部语义差异导致的类内离散；当来源规模扩大时，这两种效应会被同时放大。`

### 11. Productive deletion

Better writing sometimes requires removal, not refinement.

Delete or merge when:
- two paragraphs are making the same claim with different wording
- one section previews a point that a later section explains in full
- a summary sentence merely repeats the paragraph in safer words
- a subsection exists only because the outline expected another bullet

### 12. Sharp but Academic Judgment

Strong judgment is allowed in thesis writing, but it must stay inside academic register.

Avoid:
- colloquial emphasis such as "直接崩了", "卡住了", "撑不住"
- emotional intensifiers that replace mechanism with attitude

Prefer:
- "不再成立"
- "难以维持"
- "其实证支撑减弱"
- "在该设定下失效"

Back strong judgment with:
- a mechanism
- a condition
- or an observation that explains why the judgment holds

Avoid another nearby pattern:
- question-and-answer style contrasts such as "能不能用" and "如何改造后再用"
- quoted paired labels such as "可检测", "可迁移", "可解释" when they read like machine-translated summaries

Prefer:
- direct analytical statements
- concrete capability descriptions such as "能够完成真伪检测" or "具备一定跨来源迁移能力"

Examples:
- bad: `视觉基础模型真正提出的问题不是“能不能用”，而是“如何改造后再用”。`
- better: `视觉基础模型路线的核心挑战在于：如何在保留迁移能力的前提下，使其适配来源判别任务。`
- bad: `现有研究已经证明“可检测”与“可迁移”……`
- better: `现有研究已经表明，相关方法可以完成真伪检测，也具备一定跨来源迁移能力……`

### 13. Honest Technical Motivation

State the real reason for a design choice.

Avoid:
- defaulting to "便于部署", "更好落地", or other generic convenience language when the real issue is training cost or resource limits
- mixing training efficiency, inference efficiency, and deployment convenience as if they were the same thing

Prefer:
- training feasibility if the core issue is memory or compute budget
- inference cost if the core issue is test-time overhead
- deployment convenience only when the surrounding context truly concerns deployment

### 14. Work Names and English Terms

Treat these as writing conventions, not optional polishing.

Rules:
- if a cited work has a clear method name, paper title, or established public name, prefer that name at first mention instead of writing only "Author et al."
- when an English technical term first appears, provide the full English name and a Chinese explanation or translation once
- after first mention, use the abbreviation or Chinese term consistently

Examples:
- bad: `Wang 等则系统比较了多个 CNN 生成器上的检测迁移效果……`
- better: `Wang 等在《CNN-generated images are surprisingly easy to spot... for now》中系统比较了多个 CNN 生成器上的检测迁移效果……`
- bad: `研究者开始把 CLIP、DINO 等大规模视觉基础模型视为新的表征底座。`
- better: `研究者开始把 Contrastive Language-Image Pretraining（CLIP，对比语言-图像预训练）和 self-distillation with no labels（DINO，自蒸馏无标签）等大规模视觉基础模型视为新的表征底座。`
- bad: `本文采用 LoRA。`
- better: `本文采用 Low-Rank Adaptation（LoRA，低秩适配）。`

### 15. Weaken Over-Connected Causality

Avoid long chains that announce every causal step with connectives such as "通过……从而……进而……".

Bad pattern:
- sentences that explicitly connect every small step with "通过", "从而", "进而", "于是", "因此"
- cause-effect chains whose logic is already obvious but is still narrated in full

Better pattern:
- shorten the clause chain
- juxtapose actions when the relation is already clear
- split the chain into two firmer sentences if the full chain becomes soft

Examples:
- bad: `通过多尺度打乱削弱语义，从而把注意力转向来源线索，进而提升判别稳定性。`
- better: `多尺度打乱削弱了语义主导，来源线索得以显露。`
- bad: `模型先因为语义相近而被拉近，于是容易发生混淆。`
- better: `语义相近的样本在特征空间中被错误聚合，来源边界随即模糊。`

### 16. Judge Citations in Related Work

In related-work or review sections, do not stop at neutral citation summaries.

Bad pattern:
- `Author et al. (2020) proposed Method A.`
- `Author et al. (2023) used CLIP features for detection.`

Better pattern:
- after a representative citation, add a condition, limitation, or implication
- explain what assumption the work relies on, what setting it fits, or why it matters for the current thesis

Examples:
- bad: `Author et al. (2020) 提出了方法 A，取得了较好效果。`
- better: `Author et al. (2020) 证明了 A 的有效性，但其结论建立在 GAN 主导的设定下。`
- bad: `Author et al. (2023) 利用 CLIP 特征进行检测。`
- better: `Author et al. (2023) 利用 CLIP 特征进行检测，其做法实质上默认了语义空间能够承接来源判别，这一点在溯源任务中需要重新审视。`

Scope note:
- this rule is strongest in related work, literature review, and reviewer-style critique
- it does not mean every factual citation in a definition or background paragraph must carry a forced judgment

### 17. Break Paragraph Symmetry

Do not give every surveyed subtopic the same number of paragraphs or the same internal rhythm.

Bad pattern:
- every subsection repeats the same three-part structure: intro, contribution, limitation
- every subsection receives similar length even when their relevance to the thesis differs

Better pattern:
- spend more space on methods directly tied to the thesis problem
- compress background routes that only serve as context
- allow one subsection to stop on a judgment without forcing a smooth transition to the next

Examples:
- bad: `1.3.1、1.3.2、1.3.3 都是三段：引入、贡献、局限。`
- better: `对直接相关的方法多写一段拆解，对过渡性的背景方法合并压缩，允许相邻小节在节奏上不对称。`

### 18. Avoid Subject-Predicate Breaks

Do not insert a pause between the subject and the predicate when the sentence is a normal declarative statement.

Bad pattern:
- `局部扰动增强的基本思想，是……`
- `原型学习的基本思想，是……`
- `某方法的关键作用，是……`

Better pattern:
- `局部扰动增强的基本思想是……`
- `原型学习的基本思想是……`
- `某方法的关键作用在于……`

Use the pause only when a true parenthetical insertion is needed, not as a default thesis rhythm.

### 19. Do Not Over-Defend Workflow Details

Do not repeatedly add defensive clarifications that answer a question the reader has not raised, especially when they do not change the method understanding.

Bad pattern:
- adding extra disclaimers such as `增强所依据的区域划分并不依赖 ViT 的切块设置`
- repeatedly explaining what the method is *not* doing after the core process is already clear

Better pattern:
- state the actual process once and stop
- `该策略先在图像层面完成局部重排，再把增强后的完整图像送入视觉基础模型进行编码。`
- if a background subsection mentions a clue that the later method does not model explicitly, say so honestly instead of implying a nonexistent downstream module

Only add boundary clarifications when they resolve a real ambiguity that would otherwise mislead the reader.

### 20. Do Not Leave Strong Generalizations Unsupported

If a sentence makes a strong methodological or literature-backed generalization, either support it with a verified citation or rewrite it conservatively.

Bad pattern:
- `原型学习在细粒度分类中的作用，主要体现在它能够降低局部噪声和偶然偏差对决策边界的干扰。`
- broad evaluative claims that sound plausible but are not tied to a paper, experiment, or established result

Better pattern:
- anchor the claim to a verified paper
- or narrow the wording so it becomes an interpretation rather than a factual literature summary

Examples:
- bad: `原型学习在细粒度分类中的作用，主要体现在它能够降低局部噪声和偶然偏差对决策边界的干扰。`
- better: `近年的细粒度分类研究已经开始显式利用类中心约束来压缩类内方差，并拉开细微的类间差异（Yao et al., 2024, DOI: 10.48550/arXiv.2407.04243）。从这个角度看，原型学习有助于围绕类别中心组织空间结构。`
- better: `从细粒度分类的几何建模视角看，原型学习有助于围绕类别中心组织空间结构。`

### 21. Do Not Manufacture Contrast

Do not use a contrastive sentence frame unless the contrast itself carries real argumentative value.

Bad pattern:
- `X 不是……而是……`
- `X 不再只是……也可以……`
- `X 不只是……更重要的是……`
- `X 不是为了……而是为了……`
- contrastive wording used only to make the prose sound "logical" or emphatic

Better pattern:
- state the point directly when no real opposition needs to be established
- keep contrast only when the sentence is genuinely distinguishing two positions, two tasks, or two mechanisms

Examples:
- bad: `ViT 处理的不是整幅图像的像素网格，而是固定大小的 patch 序列。`
- better: `ViT 将输入图像切分为固定大小的 patch 序列进行处理。`
- bad: `位置编码的作用不只是标记 patch 的位置，更重要的是恢复全局结构的组织关系。`
- better: `位置编码用于补充 patch 的空间位置信息，也帮助模型恢复全局结构的组织关系。`
- bad: `这意味着视觉基础模型不再只是通用分类器，也可以成为来源识别的表征底座。`
- better: `这意味着视觉基础模型已经具备支撑来源识别表征学习的潜力。`
- bad: `在视觉任务中，LoRA 的应用方式往往不是为了完全替代原始骨干，而是为了用较少参数调节模型关注什么。`
- better: `在视觉任务中，LoRA 通常承担受控调节器的角色，用较少参数调整模型关注什么。`
- bad: `问题在于，来源识别需要的往往不是这种高层语义一致性。`
- better: `来源识别更关心生成过程中的来源差异，高层语义一致性本身不足以支撑这一任务。`

## Humanize Without Losing Precision

When the user asks for more "human feel":
- simplify rhetorical overstatement
- remove decorative wording
- keep professional terms unchanged
- make the rhythm less mechanical
- keep the result thesis-appropriate, not casual
- do not turn the prose into spoken Chinese or conversational phrasing
- do not force "humanity" by adding chatty fillers, emotional adverbs, or deliberate slang

## Formula Integration

When formulas appear:
- introduce the purpose first
- keep the LaTeX clean
- explain the key symbols nearby if needed

## Figure Integration

Insert figures only when they improve comprehension:
- explain a pipeline
- compare components
- summarize a structure
- support result interpretation

Do not recommend a figure just to decorate the section.
