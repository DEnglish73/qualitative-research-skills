# Content analysis

Read this when prevalence is the actual question, when the corpus is too large for close reading of every source, or when a stakeholder wants defensible numbers from text.

Content analysis is the one qualitative family where counting is the finding rather than a distraction. That also makes it the family most often misused, since counted codes look like hard evidence while resting on category definitions nobody inspects.

## Three variants (Hsieh and Shannon)

| Variant | Categories come from | Use when |
|---|---|---|
| **Conventional** | Derived inductively from the data | No existing theory; want a category system plus prevalence |
| **Directed** | An existing theory or framework, extended by the data | Testing or elaborating a known model |
| **Summative** | Keyword counts first, then interpretation of usage | Interested in how specific terms are used and by whom |

Name which one you are doing. They make different claims.

## Procedure

**1. Define the unit of analysis before coding.** This choice drives every number that follows and cannot be changed afterward without recounting. Options, roughly increasing in coarseness:

- Utterance or turn (one speaker's contribution, the default for transcripts)
- Sentence
- Meaning unit (a stretch expressing one idea, may cross sentence boundaries)
- Whole document or whole participant (presence or absence per person)

For interview and workshop data, **coding presence per participant** usually answers the real question better than counting utterances, since utterance counts reward whoever talked most.

**2. Build the category system.** Categories must be mutually exclusive and exhaustive within a dimension, each with a definition, inclusion rule, exclusion rule, and an example. Ambiguity here is the main source of unreliable counts. Where content genuinely belongs in two categories, that means two dimensions, not one messy category.

**3. Pilot on 10 to 15 percent of the corpus.** Revise definitions, then recode from the start with the revised system. Do not patch mid-corpus, since the earlier and later data end up coded to different rules.

**4. Code the full corpus** and record every assignment with turn IDs.

**5. Reliability, if claimed.** Two coders on a subset, then Cohen's kappa or Krippendorff's alpha. Report the coefficient, the subset size, and how disagreements were resolved. Values around 0.80 are conventionally acceptable, 0.61 to 0.80 substantial, below 0.60 weak enough that the category definitions need work rather than the coders. If only one analyst worked on it, say so and drop the reliability claim rather than inventing a proxy.

**6. Report counts with denominators, then interpret.** Numbers without interpretation are not analysis. Interpretation without the numbers is not content analysis.

## Output template

```markdown
# Content analysis: [source, date]

## Method note
[per SKILL.md template, naming the variant]
Unit of analysis: [turn / meaning unit / participant]
Category system origin: [inductive / from framework X]
Coders: [N]; reliability: [coefficient, subset, resolution process, or "single analyst, no reliability claim"]

## Category system
| Category | Definition | Include | Exclude | Example (turn ID) |

## Results
| Category | Participants (n/N) | Units coded | % of units | Notes |

## Interpretation
### [Claim]
[What the distribution means, what it does not establish, evidence with turn IDs]

## Limitations
[Corpus coverage, unit choice effects, uncoded residual]
```

## Traps

- **Counting without a denominator.** "SSO problems: 9" is meaningless. Nine of how many, out of how many people?
- **Utterance counts as importance.** One participant repeating a complaint six times produces six units and one person's opinion.
- **Category systems that overlap.** If a coder can defend two placements, the definitions are broken and the counts are noise.
- **Precision theater.** Percentages to one decimal on a corpus of 40 units imply a precision the data does not carry.
- **Calling it thematic analysis.** Counted categories are categories. If the deliverable says themes, the audience will read it as reflexive TA and the reliability language will look out of place.
