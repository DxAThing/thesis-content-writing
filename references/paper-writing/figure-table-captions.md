# Figure & Table Caption Generation Guide

This reference covers writing captions for figures and tables in academic papers.

---

## Figure Captions

### Task

Convert a description into a conference-standard English figure caption.

### Rules

1. **Format**:
   - Noun phrases → **Title Case** (capitalize all content words), no period at the end.
   - Complete sentences → **Sentence case** (capitalize only the first word + proper nouns), must end with a period.

2. **Style**:
   - **Minimal**: Remove filler openings like "The figure shows" or "This diagram illustrates". Start directly with the content (e.g., "Architecture of...", "Performance comparison...", "Visualization of...").
   - **De-AI**: Avoid complex, obscure words. Keep wording plain and precise.
   - Do not include the "Figure 1:" prefix; output only the caption text.

3. **LaTeX**:
   - Escape special characters: `%` → `\%`, `_` → `\_`, `&` → `\&`.
   - Keep math formulas with `$` symbols intact.

### Examples

Input: 模型整体架构，包括编码器、解码器和注意力模块
Output: `Overall Architecture with Encoder, Decoder, and Attention Modules`

Input: 不同方法在CIFAR-10上的准确率对比
Output: `Accuracy Comparison of Different Methods on CIFAR-10`

Input: 我们提出的方法在所有基准测试上都实现了最优性能
Output: `Our method achieves state-of-the-art performance across all benchmarks.`

---

## Table Captions

### Task

Convert a description into a conference-standard English table caption.

### Rules

1. **Format**: Same as figure captions (Title Case for noun phrases, Sentence case for full sentences).

2. **Style**:
   - Use standard table caption patterns: "Comparison with...", "Ablation study on...", "Results on...", "Effect of..."
   - Avoid: "showcase", "depict", "demonstrate" → Use: "show", "compare", "present"
   - Do not include the "Table 1:" prefix; output only the caption text.

3. **LaTeX**:
   - Escape special characters.
   - Keep math formulas intact.

### Examples

Input: 与现有方法在ImageNet上的对比结果
Output: `Comparison with Existing Methods on ImageNet`

Input: 不同损失函数的消融实验
Output: `Ablation Study on Different Loss Functions`

Input: 模型在不同数据集上的泛化性能
Output: `Generalization Performance across Different Datasets`

---

## Chinese Captions

For Chinese thesis figures/tables:
- Use the same content structure but write in Chinese.
- Follow the thesis template's caption formatting requirements.
- Ensure figure/table numbers follow the chapter numbering scheme (e.g., 图3-1, 表3-1).
