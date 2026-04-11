# 6-Pass Review-Refine Loop (审核-精修循环)

This file contains the detailed rules for the Chinese thesis 6-pass review loop.
It is extracted from the thesis-content-writing skill's review-refinement loop section.

## When to Use

Activate when:
- The user explicitly requests a review-refine cycle
- The user says "审核直到通过", "审核-精修", or similar

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
- Mechanical parallel structures ("首先……其次……再次……", "不是……而是……" repeated)
- Decorative contrast frames that repackage direct statements
- Over-connected causal chains ("通过……从而……进而……")
- Subject-predicate comma breaks ("X 的基本思想，是……")
- Generic verbs ("进行", "实现", "提供") used as fillers
- Abstract catch-all nouns ("链路", "落点") without concrete referent
- Paragraph-ending bridge sentences that add no information
- Section-introduction filler that merely restates the heading
- Pseudo-taxonomies where items are actually cause-effect

### Pass 3: Writing Convention Check (学术规范)

Check rules that are part of thesis 写作规范:
- First mention of an English term must give full English name + Chinese translation, then shorten consistently
- First mention of a published work should prefer its established method name or paper title
- Abbreviation and term consistency across nearby sections
- Citation format consistency: （Author, Year, DOI: xxx）

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
