# Claim Extraction Rules

## What Counts as a Claim

A claim is any statement in the paper that asserts something verifiable about the method,
its performance, or its properties.

### Positive Indicators
- Contains keywords: "outperforms", "achieves", "enables", "improves", "is essential", "is robust"
- Makes a comparative statement: "better than", "more efficient than", "unlike previous methods"
- Contains quantitative assertions: "X% improvement", "real-time speed", "fewer parameters"
- Attributes a property to the method: "our method generalizes to...", "our module captures..."

### Not a Claim (Do Not Extract)
- Definitions: "We define X as..."
- Setup descriptions: "We use dataset Y for evaluation"
- Acknowledged limitations: "Our method does not handle..."
- Future work: "In the future, we plan to..."

## Extraction Procedure

### Step 1: Scan Priority Sections
1. **Abstract**: Every sentence is potentially a claim. Extract all assertions.
2. **Introduction**: Focus on contribution paragraphs and advantage descriptions.
3. **Conclusion**: Often restates Abstract claims; cross-reference for consistency.

### Step 2: Scan Supporting Sections
4. **Method**: Look for "this enables...", "this allows...", "the advantage is..."
5. **Experiments**: Look for "our method achieves...", "Table X shows..."

### Step 3: Classify Each Claim

| Type | Example |
|------|---------|
| **Performance** | "Our method outperforms SOTA on dataset X" |
| **Necessity** | "Module A is essential for handling Y" |
| **Generalization** | "Our method generalizes to unseen domains" |
| **Efficiency** | "Our method runs at real-time speed" |
| **Insight** | "We find that Z is more important than W for this task" |

### Step 4: Record Location
For each claim, note every location it appears (may be restated in multiple sections).
