# Backward-Forward Reasoning Guide

## Backward Reasoning: Answer First

Before writing any forward narrative, answer these:

### Question 1: What technical problem do we solve?
- State the problem as a concrete technical challenge, not a vague "improve X."
- Explain why there is no well-established solution.
- Example: "Existing NeRF methods cannot handle dynamic scenes because they assume static geometry, and methods that attempt dynamic modeling require per-frame optimization which is prohibitively slow."

### Question 2: What are our contributions?
Classify each contribution into a type:
| Type | Description |
|------|-------------|
| New task | We define a problem that has not been formally studied |
| New pipeline | We propose an end-to-end framework |
| New module | We design a specific component that improves existing pipelines |
| New design choice | We make a non-obvious architectural or training decision |
| New finding | We discover an empirical phenomenon |
| New insight | We provide a new understanding of why something works |

### Question 3: Why does our method work?
- The answer must be a genuine technical insight, not "because we used X."
- Good: "Our method works because local patch shuffling forces the encoder to attend to low-level generation artifacts instead of semantic content."
- Bad: "Our method works because we use a ViT backbone with LoRA."

### Question 4: How do prior methods lead to our challenge?
- Map out the logical chain: Method A tried X → limitation → Method B tried Y → remaining limitation → our challenge.
- This chain becomes the Introduction Part B structure.

## Forward Narrative: Write Second

After backward reasoning is complete, build the story in this order:

1. **Task introduction**: What is the problem, and why does it matter?
2. **Challenge exposition**: What have others tried, and where did they fall short?
3. **Our solution**: What do we propose, and what is the core novelty?
4. **Advantages and insight**: Why does our approach work, and what new understanding does it bring?
5. **Evidence preview**: What experiments validate our claims?

## Common Mistakes

1. **Writing forward without backward reasoning**: Results in unfocused narrative.
2. **Backward reasoning that says "our method is better" instead of "why"**: Not useful.
3. **Forward narrative that front-loads details**: Save method details for the Method section.
4. **Skipping the challenge → solution logical link**: The reader must feel the challenge before seeing the solution.
