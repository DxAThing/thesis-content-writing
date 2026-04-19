# English Paper Style Guide

## Goal

Write English conference/journal paper prose that is clear, precise, and natural.
Avoid both mechanical AI-sounding text and over-decorated academic purple prose.

## Tone

- Be precise and direct.
- State claims plainly; let data and logic provide the emphasis.
- Keep terminology stable across sections.
- Write in a voice that a native-English-speaking researcher would use.

## Tense Rules

- **Present tense** for: describing methods, architectures, general findings, and conclusions.
- **Past tense** for: describing specific historical events ("Vaswani et al. proposed Transformers in 2017") or specific experiment procedures ("We trained the model for 100 epochs").
- Do not mix tenses within the same paragraph unless the switch is justified.

## Word Choice

### Avoid Contractions

Use full forms in academic prose:
- "does not" instead of "doesn't"
- "it is" instead of "it's"
- "cannot" instead of "can't"

### Avoid Possessive Forms for Methods/Models

Bad: `METHOD's performance`, `our model's accuracy`
Better: `the performance of METHOD`, `the accuracy of our model`

### Prefer Simple, Common Words

Bad: leverage, delve, tapestry, underscore, unveil, elucidate, pivotal, paramount
Better: use, explore/examine, context, highlight/emphasize, reveal/show, explain/clarify, important/key, critical

### AI-Overused Words to Avoid or Minimize

The following words are frequently overused in AI-generated text. Replace them with simpler alternatives unless a specific technical meaning demands them:

| Overused | Better Alternative |
|----------|-------------------|
| Accentuate | Emphasize, highlight |
| Ameliorate | Improve |
| Bolster | Support, strengthen |
| Culminate | Result in, lead to |
| Delineate | Describe, outline |
| Delve / Delve into | Examine, explore, investigate |
| Elucidate | Explain, clarify |
| Endeavor | Attempt, effort |
| Foster | Encourage, promote |
| Harness | Use, apply |
| Intricate | Complex |
| Leverage | Use, apply, exploit |
| Manifest | Show, appear |
| Nuanced | Subtle, fine-grained |
| Pivotal | Key, important, critical |
| Profound | Significant, deep |
| Scrutinize | Examine, inspect |
| Substantiate | Support, confirm |
| Transcend | Go beyond, exceed |
| Underscore | Highlight, emphasize |
| Unveil | Introduce, present, reveal |

## Structure Rules

### One Paragraph, One Message

Each paragraph should convey one main idea. Start with a topic sentence and end with a takeaway or transition.

### No Lists in Prose

Do not convert paragraphs into `\item` lists. Academic papers use connected prose, not bullet points. Lists are only acceptable in supplementary material or appendices.

### Sentence Structure Variety

Vary sentence length and structure. Avoid:
- Starting every sentence with "We"
- Using the same transition word in consecutive sentences
- Mechanical parallel structures across paragraphs

## LaTeX Conventions

### Special Character Escaping

Always escape: `%` → `\%`, `_` → `\_`, `&` → `\&`
Keep math formulas with `$` symbols intact.

### Formatting Restrictions

- Do not use `\textbf{}` or `\emph{}` for emphasis in body text. Let sentence structure carry the emphasis.
- Preserve all existing LaTeX commands: `\cite{}`, `\ref{}`, `\eg`, `\ie`, etc.
- Do not expand common domain abbreviations (keep LLM, GAN, ViT as-is).
- Do not add formatting commands that were not in the original.

### Table Style

Use booktabs: `\toprule`, `\midrule`, `\bottomrule`. No vertical lines. Right-align numeric columns. Bold best results.

## De-AI Patterns (English-Specific)

### Mechanical Connectors to Remove or Reduce

- "First and foremost" → just start the sentence
- "It is worth noting that" → remove, state directly
- "In order to" → "To"
- "It should be noted that" → remove
- "plays a crucial/pivotal role" → be specific about what it does
- "A comprehensive/thorough analysis" → drop the adjective unless quantified

### Structural AI Patterns

- Three-part parallel lists ("First... Second... Third...") used mechanically in every paragraph
- Every paragraph beginning with a transition word
- Concluding sentences that add no information ("In summary, our method achieves superior performance")
- Overclaiming: "groundbreaking", "revolutionary", "state-of-the-art" without evidence

### Dash and Punctuation

- Minimize em dashes (—). Use commas, parentheses, or subordinate clauses instead.
- Avoid semicolons between short independent clauses; use periods.
- Do not stack multiple commas; restructure the sentence.

## Self-Check Protocol

Before finalizing English output:
1. Are there any untranslated Chinese characters?
2. Are all LaTeX special characters properly escaped?
3. Is the tense consistent throughout?
4. Are there any AI-overused words that should be replaced?
5. Does each paragraph have exactly one main point?
6. Is the prose free of `\textbf` emphasis and `\item` lists?
