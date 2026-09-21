# ReasonType Annotation: Annotator Guide

Thank you for helping validate **ReasonType**, the reasoning-step taxonomy from the [TRACES paper](https://openreview.net/forum?id=n9iNwebw8Q).

You will label individual reasoning steps taken from DeepSeek-14B solutions to MATH500 problems. Each step has already been labelled by GPT-4o-mini. You will **not** see that label. Your independent judgements let us measure (1) how consistent human annotators are with each other and (2) how well GPT-4o-mini's labels match human judgement.

| | |
|---|---|
| **Items to annotate** | `52` steps |
| **Estimated time** | `30-45` minutes |

---

## 1. Before you start

You need to:

- Download the file to annotate (`data/TO_UPLOAD.json`)
- Connect to the website to make the annotation easier (`https://yannisbelkhiter.github.io/ReasonType_Human_validation/reasontype_annotation.html`)

## 2. Step by step

1. **Enter your name or ID.** name + surname + job (for statistics about the annotators)
2. **Choose your data file.** Upload the file that you downloaded.
3. Leave **Shuffle item order** ticked unless the organisers tell you otherwise.
4. Click **Start annotating**.
5. For each item:
   1. Read the **problem** and the **step to annotate**.
   2. Tick *"I've read the problem and this step carefully."*
   3. Answer **Task A** (step-type) and **Task B** (overall role).
   4. Optionally add a **note** if the step was ambiguous.
   5. Click **Next**. 
6. On the last item, click **Finish**, then **Download annotations (.json)**.
7. Upload the downloaded file to the `results_annotation/` folder.

## 3. What you see on each item

- **Problem**: the MATH500 problem the step belongs to.
- **Step to annotate**: the single reasoning step you are labelling (highlighted box). This is the same information GPT-4o-mini received. Earlier steps of the trace are not shown.
- **Task A** and **Task B**: described below.
- **Taxonomy reference** (top right): opens the definitions at any time.

## 4. The two tasks

### Task A: Step-type (choose 1 of 4)

Pick the option that best describes what the step is doing. Exactly one of the four options is the label GPT-4o-mini gave; the other three are drawn at random from the rest of the 14 classes, so there is no pattern to read into which distractors appear.

**Early reasoning (Setup)**

| Step-type | What it is |
|---|---|
| Problem Re-statement / Setup | Restates or rephrases the problem/question without adding new content. |
| Context Repetition / Paraphrasing | Repeats given information or prior results without transforming them. |
| Definition Recall | Recalls a definition, theorem, or known fact relevant to the problem. |

**Mid-reasoning (Calculus and problem solving)**

| Step-type | What it is |
|---|---|
| Formula Substitution / Plugging In | Substitutes values into a formula or expression. |
| Symbolic Transformation / Rewriting Sums | Algebraically rewrites or simplifies an expression. |
| Quadrant/Edge Case Consideration | Considers a specific case, region, sign, or edge condition. |
| Pattern Recognition / Symmetry | Notices a pattern, regularity, or symmetry that guides the solution. |

**Late-reasoning (Analysis and reflection)**

| Step-type | What it is |
|---|---|
| Verification / Sanity Check | Checks a prior result for correctness or consistency. |
| Heuristics / Intuition | Uses an informal heuristic or intuition to pick an approach. |
| Alternative Approach Exploration | Tries a different method or explores another path to the solution. |
| Numerical Approximation / Interpretation | Approximates a quantity numerically, or interprets what a computed result means in context. |
| Meta-Cognition / Self-Talk | Reflects on its own reasoning process ("wait", "let me reconsider"). |

**End-reasoning (Conclusion)**

| Step-type | What it is |
|---|---|
| Final Conclusion / Boxed Answer | States the final answer. |
| Other | Doesn't fit any other category. |

The phase headings only describe where a step-type *typically* occurs. They are a reading aid, not a rule: a step can be any type at any point in the solution.

### Task B: Overall role (choose 1 of 3)

Say what role the step plays in the solution as a whole.

| Role | Definition | Made up of |
|---|---|---|
| **Constructive** | Grounds the reasoning in the given problem by restating the setup or recalling a definition. Involves **no** computation and **no** self-reflection. | Problem Re-statement / Setup, Definition Recall |
| **Evaluative** | Assesses the validity of a previous step or of the overall approach, or states the final answer. | Verification / Sanity Check, Final Conclusion / Boxed Answer |
| **Other** | Does not fit Constructive or Evaluative, for example computing, rewriting, case analysis, exploring alternatives, or self-talk. | The remaining 10 step-types |

## 5. Tips for consistent labels

These are suggestions to keep annotators aligned, not extra rules.

- **Judge what the step does, and how it starts.** Look at the step's main purpose. "Wait..." or "So..." at the start of a step can also help to decisde.
- **If a step does several things, choose the one that is its main purpose.** Use your note field to mention the second one.
- **Flag ambiguity in the Notes box.** Notes on hard cases are valuable; they help us refine the taxonomy.
