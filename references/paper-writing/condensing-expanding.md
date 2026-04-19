# Text Condensing & Expanding Guide

This reference covers micro-adjustments to text length without changing meaning.

---

## Condensing (缩写)

### Goal

Reduce text by approximately 5-15 words while preserving all core information.

### Rules

1. **Adjustment Scope**:
   - Target a small word count reduction (~5-15 words).
   - Strictly preserve all core information, technical details, and experiment parameters.
   - Never change the original meaning.

2. **Condensing Techniques**:
   - **Syntax compression**: Convert clauses to phrases, or passive to active voice (if more concise).
   - **Remove fillers**: Delete meaningless padding, e.g., "in order to" → "to", "it is important to note that" → remove.
   - **Merge redundancy**: Combine overlapping phrases or sentences.

3. **Visual & Style** (for LaTeX):
   - Keep LaTeX source clean; no bold, italic, or quotation marks.
   - Avoid em dashes (—).
   - No `\item` lists; maintain connected paragraphs.

4. **Output Format**:
   - **Part 1 [LaTeX]**: Condensed English LaTeX code only.
     * Escape special characters (`%`, `_`, `&`).
     * Keep math formulas intact.
   - **Part 2 [Translation]**: Chinese back-translation (to verify no core information was lost).
   - **Part 3 [Modification Log]**: Brief Chinese log of changes (e.g., "删除了冗余词 XXX，合并了 YYY 从句").

5. **Self-Check**:
   - Did you accidentally remove an experiment parameter or qualifier? (If yes, restore it.)
   - Did you over-condense? (Target micro-adjustment, not paragraph-to-sentence compression.)

---

## Expanding (扩写)

### Goal

Increase text by approximately 5-15 words by explicating implicit logic and enhancing connections.

### Rules

1. **Adjustment Scope**:
   - Target a small word count increase (~5-15 words).
   - Strictly no padding: do not add meaningless adjectives or repetitive filler.

2. **Expanding Techniques**:
   - **Depth mining**: Carefully read the original, identify and explicate implicit conclusions, premises, or causal relationships. Fill in what was left unstated.
   - **Logic enhancement**: Add necessary connectors (e.g., Furthermore, Notably) to clarify inter-sentence relationships.
   - **Expression upgrade**: Replace simple descriptions with more precise, descriptive academic expressions.

3. **Visual & Style** (for LaTeX):
   - Keep LaTeX source clean; no bold, italic, or quotation marks.
   - Avoid em dashes (—).
   - No `\item` lists; maintain connected paragraphs.

4. **Output Format**:
   - **Part 1 [LaTeX]**: Expanded English LaTeX code only.
     * Escape special characters (`%`, `_`, `&`).
     * Keep math formulas intact.
   - **Part 2 [Translation]**: Chinese back-translation (to verify new logic aligns with original intent).
   - **Part 3 [Modification Log]**: Brief Chinese log of changes (e.g., "补充了隐含结论 XXX，增加了连接词 YYY").

5. **Self-Check**:
   - Is the new content a reasonable inference from the original? (No hallucinations or fabricated data.)
   - Is the expanded text still concise? (Avoid turning it into padding.)

---

## Chinese Text Condensing/Expanding

The same principles apply to Chinese text, with these adjustments:
- Output plain text (no Markdown formatting) for Word compatibility.
- Use full-width Chinese punctuation.
- Part 2 becomes unnecessary (text is already in Chinese); replace with a brief summary of changes.
