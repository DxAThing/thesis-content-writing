# Output Format

Use these output shapes for thesis work that will later be pasted into Word or saved as `.txt`.

## 1. Draft a New Section

```text
[Section Title]

[Main Text]
2-6 paragraphs of Chinese thesis prose that can be pasted directly into Word.

[Figure Brief]
Insertion point:
Purpose:
Elements:
Suggested caption:
Callout sentence:

[Formulas]
1. ...
2. ...
```

Only include the figure and formula blocks when they help.

When literature support is needed in Chinese thesis prose, cite inline inside the main text using full-width parentheses:

```text
（Author, Year, DOI: xxx）
```

Example:

```text
Transformer architecture first established full self-attention as the core sequence modeling mechanism （Vaswani et al., 2017, DOI: 10.48550/arXiv.1706.03762）.
```

## 2. Refine an Existing Section

```text
[Revised Text]
Full revised version.

[Revision Notes]
- Kept the original structure.
- Tightened vague claims.
- Smoothed one logic jump between paragraphs 2 and 3.
```

If the user wants pure paste-ready text, omit revision notes.

If the revised text includes literature-backed claims, keep or add the citation in `（Author，Year，DOI：xxx）` format.

## 3. Logic Check

If no real issue exists:

```text
No substantive issues found.
The section is logically coherent and does not need a forced rewrite.
```

If issues exist:

```text
1. The key term "X" is used before it is defined.
2. Paragraph 3 claims an improvement, but no supporting evidence is given in the section.
3. The section switches between "module A" and "feature extractor" as if they were different things.
```

Keep this terse.

If a sentence lacks support, explicitly say so instead of pretending it is established.

## 4. Review Pass

```text
[Summary]
One short paragraph on what the section is trying to do.

[Strengths]
- ...
- ...

[Major Issues]
- ...
- ...

[Revision Advice]
- ...
- ...
```

## 5. Figure Brief Only

```text
Figure number suggestion:
Insertion point:
Purpose:
Core visual elements:
Suggested caption:
Optional English title:
Callout sentence:
```

Prefer practical technical content over design language.

## 6. Formula Output

Use bare LaTeX only.

Correct:

```text
P(A\mid B) = \frac{P(B\mid A)P(A)}{P(B)}
```

Incorrect:

```text
$P(A\mid B) = \frac{P(B\mid A)P(A)}{P(B)}$
```

If needed, follow the formula with a short Chinese explanation in plain text.

## 7. Missing Information Markers

Use explicit placeholders instead of hallucinating:
- `[TO ADD CITATION]`
- `[TO VERIFY CITATION]`
- `[TO ADD DATA]`
- `[TO ADD FIGURE NUMBER]`
- `[TO ADD VARIABLE DEFINITION]`

Only use placeholders the user can realistically fill later.
