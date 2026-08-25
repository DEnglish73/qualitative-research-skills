# Integrating qualitative findings with quantitative data

Read this when the evidence base includes both qualitative sources and survey responses, usage metrics, or trial data, and the deliverable has to be one coherent account rather than two sections stapled together.

## Decide the integration design first

| Design | Sequence | What integration means |
|---|---|---|
| **Explanatory sequential** | Quant first, then qual | Qualitative data explains an unexpected or unexplained quantitative result |
| **Exploratory sequential** | Qual first, then quant | Qualitative findings build the instrument or hypotheses that quant then tests |
| **Convergent** | Both roughly in parallel | Findings compared for agreement, partial agreement, and dissonance |

Most applied program work is convergent by circumstance rather than design: a survey and a workshop happened, both are on the table. Say that plainly in the method note. Retrofitting a design label onto data that arrived opportunistically overstates the study.

## Analyze separately, integrate deliberately

Complete the qualitative analysis on its own terms before looking at the quantitative results, and vice versa where possible. Reading qualitative data with the survey percentages already in mind produces confirmation of the survey almost every time, and it is nearly impossible to detect after the fact.

Integration then happens at one or more of three points:

- **Findings level**: comparing conclusions from each strand.
- **Data level**: transforming one strand (for example, coding open-text survey responses, or counting participants with a qualitative attribute) so it can sit alongside the other. Label transformed data clearly.
- **Interpretation level**: a joint narrative built from both.

## Joint displays

The main practical tool. Rows are findings or constructs, columns are strands, plus a column for the integrated read:

```
finding | qualitative evidence (turn IDs) | quantitative result (n, %, statistic) | fit | integrated interpretation
```

`fit` takes one of three values, and the third is the most valuable:

- **Confirmation**: both strands point the same way. Adds confidence, adds little insight.
- **Complementarity**: strands address different facets and together give a fuller account.
- **Dissonance**: strands disagree.

Dissonance is a finding, not an error to be resolved. Report it and work through the candidate explanations: different populations or response rates, question wording that measured something adjacent, social desirability in one mode, a genuine split between what people report and what they do, or timing differences. Suppressing dissonance to produce a tidy narrative is the main integrity risk in mixed work.

## Weighting and language

- **Do not let percentages outrank qualitative findings by default.** A survey with 300 responses and a 12 percent response rate is not automatically stronger evidence than nine detailed interviews. State each strand's denominator and known limits, and let the reader weigh them.
- **Do not quantify qualitative data to make it look sturdier.** "73 percent of participants mentioned" from an 11-person workshop reads as precision the design cannot support. Report distinct speakers over the denominator.
- **Keep the strands distinguishable in the write-up.** A reader should always be able to see which claim rests on which evidence.

## Output template

```markdown
# Integrated findings: [sources, dates]

## Method note
Qualitative: [method, corpus, N]
Quantitative: [instrument or data source, N, response rate, analysis]
Design: [explanatory / exploratory / convergent, or "opportunistic convergent"]
Integration points: [findings / data / interpretation]
Sequence safeguard: [whether strands were analyzed independently]

## Joint display
| Finding | Qual evidence | Quant result | Fit | Integrated interpretation |

## Where the strands disagree
[Each instance, candidate explanations, what would settle it]

## Integrated account
[Narrative, 300 to 600 words, strands attributed throughout]

## Limitations of the combination
[Population overlap, timing, what the combination still cannot answer]
```

## Traps

- **Two sections, no integration.** A qualitative chapter followed by a quantitative chapter is not mixed methods.
- **Qual as decoration.** Quotes used to illustrate survey results, with the qualitative analysis never actually done.
- **Sequence contamination.** Analyzing qual with the quant results in hand, then reporting convergence.
- **Resolving dissonance by dropping a strand.** If one strand is dropped, say which and why, in the method note.
- **Population mismatch left unstated.** Survey respondents and workshop attendees are usually different groups, which alone can explain apparent disagreement.
