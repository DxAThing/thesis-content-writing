# Citation Verification

Use this reference when the user wants literature-backed writing, inline citations, or sentence-level fact checking.

## Core Rule

Treat citation work as verification work, not decoration.

Before finalizing a paragraph:
- inspect each sentence
- identify which sentences make factual or literature-backed claims
- verify those claims against known sources or user-provided references
- keep unsupported claims conservative
- for any sentence that draws a conclusion, identify its basis explicitly: literature, experiment, or theoretical analysis

## Required Inline Format

For literature-backed statements in Chinese thesis prose, use full-width parentheses:

```text
（Author, Year, DOI: xxx）
```

Examples:

```text
（Goodfellow et al., 2014, DOI: 10.48550/arXiv.1406.2661）
（He et al., 2016, DOI: 10.1109/CVPR.2016.90）
```

## Hard Constraints

- do not invent citations
- do not invent DOI values
- do not output an apparently complete citation if DOI is still unknown
- if the source is uncertain, use `[TO VERIFY CITATION]`
- if the sentence is too strong for the available evidence, rewrite it more cautiously

## Sentence-Level Verification Workflow

For each sentence, classify it quickly:

### 1. Pure connective sentence

Examples:
- transition sentence
- scope sentence
- section roadmap sentence

Usually does not need citation.

### 2. Method description based on the user's own work

Usually does not need outside citation unless the method directly derives from prior work and the user wants that connection stated.

### 3. General factual claim

Examples:
- a model was proposed in a certain year
- a known architecture has a specific property
- a benchmark is widely used for a task

Needs verification if presented as fact.

### 4. Comparative or evaluative claim

Examples:
- "widely recognized"
- "significantly better"
- "mainstream"
- "state of the art"

Needs especially careful support or a more cautious rewrite.

### 5. Conclusion sentence

Examples:
- a sentence that says "therefore", "this shows", "this means", "it can be seen that", or directly gives a judgmental takeaway
- a sentence that claims a method is suitable, effective, necessary, limited, or better in some respect

Needs a clear basis from one of:
- verified literature
- experiment or observation provided by the user
- explicit theoretical analysis already developed in the surrounding text

If the basis is missing, do not keep the sentence at full strength.

## Rewrite Strategy When Support Is Weak

Preferred order:
1. verify and cite
2. point the sentence back to experiment support or theoretical analysis if that is the real basis
3. narrow the claim
4. mark with `[TO VERIFY CITATION]`
5. remove the unsupported statement

## Examples

Too strong:

```text
This method is widely regarded as the most effective solution.
```

Safer:

```text
This method has been adopted in several representative studies （Author, Year, DOI: xxx）.
```

If not verified:

```text
This method has been adopted in several representative studies [TO VERIFY CITATION].
```
