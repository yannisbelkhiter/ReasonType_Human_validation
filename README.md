# ReasonType Annotation: Annotator Guide

Thank you for helping validate **ReasonType**, the reasoning-step taxonomy from the [TRACES paper](https://openreview.net/forum?id=n9iNwebw8Q).

You will label individual reasoning steps taken from DeepSeek-14B solutions to MATH500 problems. Each step has already been labelled by GPT-4o-mini. You will **not** see that label. Your independent judgements let us measure (1) how consistent human annotators are with each other and (2) how well GPT-4o-mini's labels match human judgement.

| | |
|---|---|
| **Items to annotate** | `52` steps |
| **Estimated time** | `30-45` minutes |

---

## 1. Before you start

You need:

- the annotation tool: `reasontype_annotation.html`
- your data file (`.json`, `.csv` or `.tsv`), sent to you by the organisers
- a recent desktop browser (Chrome, Firefox, Edge or Safari) **with an internet connection**, which is needed to display maths and fonts

Open `reasontype_annotation.html` by double-clicking it. Nothing is uploaded anywhere: your data stays in your browser until you download your results.

## 2. Step by step

1. **Enter your name or ID.** Use the same one every time you return, since your saved progress is tied to it.
2. **Choose your data file.** A message confirms how many steps were loaded. A message with a red border means the file could not be read; see [Troubleshooting](#7-troubleshooting).
3. Leave **Shuffle item order** ticked unless the organisers tell you otherwise.
4. Click **Start annotating**.
5. For each item:
   1. Read the **problem** and the **step to annotate**.
   2. Tick *"I've read the problem and this step carefully."*
   3. Answer **Task A** (step-type) and **Task B** (overall role).
   4. Optionally add a **note** if the step was ambiguous.
   5. Click **Next**. You can use **Previous** to revisit and change an earlier answer.
6. On the last item, click **Finish**, then **Download annotations (.json)**.
7. Send the downloaded file to `[contact]`.

**Next** stays greyed out until the checkbox is ticked and both tasks are answered.

## 3. What you see on each item

- **Problem**: the MATH500 problem the step belongs to.
- **Step to annotate**: the single reasoning step you are labelling (highlighted box). This is the same information GPT-4o-mini received. Earlier steps of the trace are not shown.
- **Task A** and **Task B**: described below.
- **Taxonomy reference** (top right): opens the definitions at any time.

## 4. The two tasks

The two tasks are answered **separately**. What you pick in one never limits the choices in the other.

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

- **Judge what the step does, not how it starts.** "Wait..." or "So..." at the start of a step doesn't decide the label; look at the step's main purpose.
- **If a step does several things, choose the one that is its main purpose.** Use your note field to mention the second one.
- **Use the definitions, not your own idea of the category.** When unsure, reopen *Taxonomy reference*.
- **Use "Other" for steps that genuinely fit nowhere**, not as a way to skip a hard decision.
- **Answer Task B from the role definitions**, on its own merits, rather than working it out from your Task A answer.
- **Flag ambiguity in the Notes box.** Notes on hard cases are valuable; they help us refine the taxonomy.
- **Don't rush, and don't overthink.** Your first careful reading is usually the label we want.

## 6. Saving, resuming and submitting

- **Autosave:** every time you click Next or Previous, your answers are saved in your browser's local storage on that computer.
- **Save progress file:** the *Save progress file* link (top right) downloads a backup at any time. Use it before closing the tab, and especially before clearing browser data.
- **Resume:** reopen the tool in the **same browser**, enter the **same name/ID**, load the **same data file**, then click **Resume saved session**. You continue at your first unanswered item.
- **Submit:** after the last item, click **Download annotations (.json)** and send it to `[contact]`. The file is named `traces_annotations_<your-id>.json`.

If you need to stop partway, you can send the `_progress.json` file, but please tell the organisers it is incomplete.

## 7. Troubleshooting

| Problem | What to do |
|---|---|
| **Start annotating** is greyed out | You need both a name/ID and a successfully loaded data file. |
| "Could not read data file" | The message names the problem (for example a row missing `step` or `category`). Check you chose the file the organisers sent, and contact `[contact]` if it persists. |
| **Next** is greyed out | Tick the "I've read..." box and answer both Task A and Task B. |
| Maths shows as raw `$...$` text | The maths library didn't load. Check your internet connection and reload. Then use **Resume saved session**. |
| **Resume saved session** doesn't appear | Progress is stored per browser and per name/ID. Use the same browser and exactly the same ID. |
| Lost progress after clearing browser data | Reload the tool and start again, or continue from your `_progress.json` backup by asking the organisers. |

## 8. Ground rules

- **Work independently.** Please don't discuss items with other annotators, since we are measuring agreement between people.
- **Stay blind.** Don't try to find or look up GPT-4o-mini's labels for these steps.
- **Use only what the tool shows you.** Don't run the steps or problems through other AI tools.
- **Privacy:** your name/ID appears in your exported file and is otherwise stored only in your browser.

Thank you again. Careful, independent labels are exactly what this validation needs.
