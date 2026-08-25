---
name: qualitative-research
description: Rigorous qualitative analysis across method families (reflexive thematic analysis, framework analysis, content analysis, grounded theory, IPA, discourse and narrative analysis, rapid analysis, integration with survey or usage data) applied to transcripts, interviews, focus groups, workshop and demo recordings, open-ended survey responses, meeting notes, and user feedback, producing an analytic framework plus an attributed quote bank. Use whenever the user has qualitative text and wants themes, codes, categories, patterns, findings, or a synthesis of what people said, including softer versions such as what came out of the workshop, pull the main points from these transcripts, synthesize this feedback, what are people struggling with, how many raised X, or compare what we heard this time versus last time, and for slide bullets, quotes, or an action backlog from qualitative sources. It picks the method when the user does not name one.
---

# Qualitative Research

Rigorous qualitative analysis across the main method families, with every claim traceable back to a specific thing a specific person said.

The failure mode to design against is fluent-sounding topic summaries dressed up as findings. That output reads well, gets into a deck, and then collapses when a scientist asks "who said that, and how many people actually raised it?" The second failure mode is method drift: announcing thematic analysis and delivering content analysis, or claiming saturation in a method where the concept does not apply. Both are avoidable, and both are what the structure below exists to prevent.

## Phase 0: Set scope and method with the user

Ask before analyzing, in a single turn, and keep it short. If a tool for tappable multiple-choice options is available (for example `ask_user_input_v0`), use it; otherwise ask as a compact numbered list. If the user already answered some of this in conversation, do not re-ask. Confirm the read in one line and move.

Ask these five:

1. **Method**. Offer a recommendation with a one-line reason using the selection guide below. Most users do not know the method names and should not be made to feel they should.
2. **Depth**. Full analysis, analysis only (findings plus evidence, no packaging), or packaging only (user already has findings)?
3. **Orientation**. Inductive (built from the data) or deductive (read against an existing framework, prior finding set, or predefined constructs)? Mixed is common and fine, but name it.
4. **Extra deliverables** beyond the two defaults: prioritized action or bug backlog, slide-ready bullets, cross-event or longitudinal comparison, executive summary.
5. **Attribution rules**. Real names, role labels only (for example "external researcher, imaging lab"), or pseudonymous IDs (P01, P02)? Also confirm whether facilitator and presenter speech counts as data.

Two outputs are always produced regardless of method: an **analytic framework with definitions** (themes, categories, a matrix, or a theory, depending on method) and a **quote bank with speaker attribution**. Those are the backbone; everything else derives from them.

## Choosing the method

Match the method to the question, never to the deadline. If the deadline rules out the right method, say so and offer rapid analysis labeled honestly rather than a thin version of something rigorous.

| Question the user actually has | Method | Reference |
|---|---|---|
| What patterns of meaning run through this data? | Reflexive thematic analysis | `references/reflexive-ta.md` |
| How do these cases compare across a fixed set of categories? Multiple analysts, policy or program decisions | Framework analysis (also codebook TA, template analysis) | `references/framework-analysis.md` |
| How often does X appear, and in what proportion? Large corpus, prevalence is the point | Content analysis | `references/content-analysis.md` |
| How does this process work, and what explains it? Theory needed, sampling still open | Grounded theory | `references/grounded-theory.md` |
| What is it like to live through this? Small homogeneous sample, experience is the object | Interpretative phenomenological analysis | `references/ipa.md` |
| How is this being said, and what does the language or story do? | Discourse or narrative analysis | `references/discourse-narrative.md` |
| Decision is in days, findings needed now | Rapid qualitative analysis | `references/rapid-qual.md` |
| Qualitative plus survey or usage data, needing one coherent account | Integration with quantitative data | `references/integration.md` |

Selection heuristics that resolve most real cases:

- **Applied program and product work** (workshop feedback, demo sessions, user interviews where the goal is decisions) defaults to reflexive TA, or framework analysis when several people are analyzing or when comparing sites, cohorts, or arms matters.
- **"How many people said X"** as the actual question means content analysis, not TA. Do not deliver counted codes and call them themes.
- **A large deductive category set handed to you** points to framework analysis or directed content analysis, not inductive TA.
- **Theory-building language** ("what drives adoption," "how does trust form") points to grounded theory, but grounded theory needs iterative data collection. Without that, say what you can do instead: a TA that gestures at process without claiming theory.
- **Never blend method vocabulary.** Kappa belongs to content analysis and coding-reliability TA. Saturation belongs to grounded theory. Central organizing concepts belong to reflexive TA. Borrowing terms across methods is the clearest signal that the analysis was not thought through.

If two methods genuinely fit, name both and pick one with a reason. If the user asks for a method that does not fit the question, say so once, plainly, then do what they asked.

## Method-agnostic core

Everything in this section applies whichever method you use. Read the method reference for the analytic procedure, then come back to these.

### Prepare the data

Run `scripts/prep_transcript.py` on each source first. It normalizes .vtt, .srt, .txt, .docx, .csv, and .md into speaker-labeled turns with stable IDs (T001, T002), writes a speaker roster with word counts, and flags likely transcription damage.

```bash
python3 scripts/prep_transcript.py <input-file> --outdir <workdir> [--source-label kickoff-2026-08-18] [--facilitators "Name A,Name B"]
```

Stable turn IDs matter more than they look. They are what makes every quote and every prevalence claim checkable, and they let you recount without re-reading the corpus.

### Read the whole corpus first

Not skimmed, not chunk-summarized. Chunk-summarizing then aggregating the summaries produces topic lists in every method, every time, since the analytic detail is destroyed before analysis starts. Read the normalized transcripts end to end, then write a short familiarization note (10 to 20 lines) covering first impressions, surprises, and questions.

### Declare the analytic stance

Record before coding, and put it in the method note of the final output:

- **Semantic or latent**: coding what people said, or the assumptions underneath. Mixing is fine, labeling is not optional.
- **Whose speech is data**: facilitator prompts and demo narration are usually context, not data. Coding them inflates findings with your own team's framing. If in scope, mark them as a separate speaker class so they can be excluded from prevalence counts.
- **Positionality**: you are analyzing alongside a user with stakes in the result. Name the forces that could bend the analysis (wanting the tool to look good, wanting a known problem confirmed, wanting a tidy slide) in `reflexivity.md`, and revisit them before finalizing. This applies in every method, including the ones that never use the word reflexivity.

### Keep the audit trail

One row per code or category assignment, in `codes.csv` or `codes.jsonl`:

```
code_label | code_meaning | source | turn_id | speaker_id | extract (verbatim, trimmed)
```

Methods differ in what happens to these rows afterward. None of them work without the rows.

### Report prevalence honestly

Count **distinct speakers**, not mentions, and state the denominator: "raised by 4 of 11 external participants." A finding supported by one speaker can still matter (a single blocking bug does), but label it as such rather than implying consensus. Content analysis is the one method where counts are the finding, and even there report the unit of analysis and the denominator.

### Flag uncertainty rather than smoothing it

Where transcription is damaged, a claim rests on an ambiguous turn, or a speaker's role is unknown, say so inline. Confident prose over shaky evidence is what destroys trust in qualitative work, and it is unrecoverable once a stakeholder catches it.

### Quote handling

Quotes stay verbatim. Mark elisions with […]. Never fix grammar silently or reorder words. Altered quotes are how qualitative analysis loses credibility, and the fix costs nothing at the time.

## Deliverables

### Analytic framework (always)

Structure varies by method, so use the template in the method reference. Whatever the method, the output carries a method note at the top:

```markdown
## Method note
[Method name and citation], [inductive/deductive/mixed], [semantic/latent] level.
Corpus: [sources, total duration, N speakers, N external vs internal].
Data in scope: [participant speech only / includes facilitator].
Attribution: [names / role labels / pseudonymous IDs].
Analyst positionality and known forces on the analysis: [1 to 2 lines, pointer to reflexivity log].
Limitations: [what this corpus cannot tell you].
```

Writing the method note first is a useful discipline: if you cannot fill it in cleanly, the analysis has a problem worth fixing before it reaches a deck.

### Quote bank (always)

One row per quote, sortable, so anyone building a deck or report can pull evidence without re-reading transcripts:

```
quote_id | verbatim_quote | speaker_attribution | speaker_class (external/internal/facilitator) | source | turn_id | finding (theme/category/etc.) | subfinding | usability_note
```

`usability_note` records whether a quote is deck-ready as-is, needs light trimming, or should not circulate (identifying detail, criticism of a named person, damaged audio).

### Optional deliverables

Only if requested at Phase 0. Templates in `references/deliverables.md`: prioritized backlog, slide bullets, executive summary, attribution and consent handling.

For cross-event or longitudinal work, read `references/comparison.md` first. The strongest finding it produces is usually the item raised at the earlier event that is still present at the later one, which needs careful evidence handling rather than an impressionistic read.

## Failures common to every method

- **Chunk-summarizing instead of coding.** Produces topic lists regardless of which method you claim.
- **Counting as proof.** Outside content analysis, "mentioned 14 times" is not a finding. Distinct speakers and the nature of the claim are what matter.
- **Findings that match the brief.** If the output maps suspiciously well onto what the team already believed, re-read the data rather than treating the fit as validation.
- **Silent smoothing.** Cleaning a quote, dropping an inconvenient outlier, implying consensus from three speakers. Each looks small; together they produce analysis that cannot be defended.
- **Borrowed vocabulary.** Saturation, kappa, and central organizing concepts each belong to specific methods. Using them outside their method misrepresents what was done.
- **Method chosen by deadline.** Rapid analysis is respectable when labeled. A rushed six-phase analysis presented as complete is not.

## Reference index

Method procedures:
- `references/reflexive-ta.md` — Braun and Clarke reflexive TA, the six phases, themes vs topic summaries, defending single-analyst work
- `references/framework-analysis.md` — framework analysis, codebook TA, template analysis, matrix construction, multi-analyst work
- `references/content-analysis.md` — conventional, directed, and summative content analysis, category systems, coder agreement
- `references/grounded-theory.md` — constant comparison, memoing, theoretical sampling, when saturation is a legitimate claim
- `references/ipa.md` — interpretative phenomenological analysis, idiographic then cross-case
- `references/discourse-narrative.md` — discourse analysis and narrative analysis, when how it was said is the object
- `references/rapid-qual.md` — rapid analysis and RAP sheets, and what gets given up

Cross-cutting:
- `references/integration.md` — combining qualitative findings with survey or usage data
- `references/deliverables.md` — backlog, slide bullets, executive summary, attribution rules
- `references/comparison.md` — cross-event and longitudinal comparison
- `scripts/prep_transcript.py` — transcript normalization and speaker roster
