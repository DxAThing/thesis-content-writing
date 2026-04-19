# 6-Pass Review-Refine Loop (审核-精修循环)

This file contains the detailed rules for the 6-pass review loop.
It applies to both **Chinese thesis** and **English paper** writing, with language-specific notes where needed.

## When to Use

Activate when:
- The user explicitly requests a review-refine cycle
- The user says "审核直到通过", "审核-精修", "review-refine loop", or similar

## Pass Definitions

### Pass 1: Reader Test (读者测试)

Simulate a first-time reader of the chapter. Check:
- Can the argument be followed without re-reading?
- Are there undefined terms used before introduction?
- Are cross-references (e.g., "如 1.4.3 节所述") pointing to real content?
- Is the reading flow blocked by abrupt transitions or missing context?
- Are there redundant paragraphs or duplicated claims across sections?

### Pass 2: De-AI / Humanize Check (去 AI 味)

Scan for patterns listed in `thesis-content-writing/references/refinement-modes.md`. Focus on:

**Chinese-specific patterns:**
- Mechanical parallel structures ("首先……其次……再次……", "不是……而是……" repeated)
- Decorative contrast frames that repackage direct statements
- Over-connected causal chains ("通过……从而……进而……")
- Subject-predicate comma breaks ("X 的基本思想，是……")
- Generic verbs ("进行", "实现", "提供") used as fillers
- Abstract catch-all nouns ("链路", "落点") without concrete referent
- Paragraph-ending bridge sentences that add no information
- Section-introduction filler that merely restates the heading
- Pseudo-taxonomies where items are actually cause-effect

**English-specific patterns:**
- AI-overused words (leverage, delve, unveil, pivotal, etc.)
- Filler openers ("It is worth noting that", "First and foremost")
- Mechanical three-part lists in every paragraph
- Overclaiming without evidence ("groundbreaking", "revolutionary")
- Excessive em dash usage
- Generic concluding sentences that repeat what was already stated

See `references/refinement-modes.md` § 7 for the full English de-AI word list.

### Pass 3: Writing Convention Check (学术规范)

Check rules that are part of academic writing conventions:

**Shared (both languages):**
- First mention of an abbreviation must give full name, then shorten consistently
- First mention of a published work should prefer its established method name or paper title
- Abbreviation and term consistency across nearby sections

**Chinese-specific:**
- First English term → full English name + Chinese translation, then abbreviation
- Citation format: （Author, Year, DOI: xxx）
- No spaces between CJK and Western characters
- Full-width paired quotation marks

**English-specific:**
- No contractions
- No possessive forms for methods/models
- Citation format per venue style (\cite{} or Author et al.)
- Present tense for methods/findings, past tense for specific events

### Pass 4: Citation and Fact Verification (引用与事实核查)

- Scan every sentence and classify as factual, conclusion-like, interpretive, or connective
- Every factual or conclusion-like sentence must be checked for citation support (ALL sections)
- Every factual claim has a citation or is softened
- No invented author names, years, or DOIs
- Every conclusion-like sentence has an identifiable basis (literature, experiment, or theoretical analysis)
- If incomplete citations found, search and fill before flagging
- Mandatory re-verification after any citation is added or corrected

### Pass 5: Logic Check (逻辑检查)

Apply high-threshold rules:
- Contradictions between sections
- Claim-evidence mismatch
- Undefined terms or symbols
- Inconsistent naming of the same concept
- Conclusion sentences whose basis is missing or weaker than the wording

### Pass 6: Reviewer Pass (审稿人视角)

Simulate a thesis defense reviewer:
- Summarize the section's claimed contribution
- Separate major issues from minor improvements
- Flag unsupported conclusions as real issues, not style preferences

## Issue Consolidation

After all 6 passes:
1. Merge duplicates (same issue found in multiple passes)
2. Classify each issue as: **major** (must fix), **minor** (should fix), or **cosmetic** (optional)
3. Discard cosmetic issues unless count is very low and easy to fix

## Fix Phase

- Apply all major and minor fixes
- Do NOT fix cosmetic-only issues unless explicitly asked

## Re-Review Phase

- Re-read the fixed text
- If any citations were added/modified during Fix Phase, re-run Pass 4 in full
- Run a compressed re-check (all 6 passes in one scan) on other changes
- If new major issues found, fix and re-check again
- If only minor/cosmetic remain, report and declare loop passed
