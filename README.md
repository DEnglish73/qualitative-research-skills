# qualitative-research-skills
This is a skill.MD file for LLMs to perform qualitative research. 

A Claude skill for rigorous qualitative analysis across eight method families, built so that every claim in the output traces back to a specific thing a specific person said.

Written for applied program and product research: workshop transcripts, demo session recordings, participant interviews, open-ended survey responses, and roundtable notes, where findings feed decisions rather than publications. It works for academic use too, and it will tell you when it is being asked to do something its method cannot support.

Install

Save the .skill file to your Claude profile, or place the folder in your skills directory:

qualitative-research/
├── SKILL.md
├── README.md
├── references/
│   ├── reflexive-ta.md
│   ├── framework-analysis.md
│   ├── content-analysis.md
│   ├── grounded-theory.md
│   ├── ipa.md
│   ├── discourse-narrative.md
│   ├── rapid-qual.md
│   ├── integration.md
│   ├── deliverables.md
│   └── comparison.md
└── scripts/
    └── prep_transcript.py

No dependencies for most input formats. .docx input needs python-docx:

bash
pip install python-docx
Methods covered
Method	Use when	Reference
Reflexive thematic analysis	Patterns of meaning across a corpus; single immersed analyst	references/reflexive-ta.md
Framework analysis	Cross-case comparison, several analysts, program decisions. Also covers codebook TA and template analysis	references/framework-analysis.md
Content analysis	Prevalence is the actual question; large corpus	references/content-analysis.md
Grounded theory	Process and explanation; data collection still open	references/grounded-theory.md
Interpretative phenomenological analysis	Lived experience; small homogeneous sample	references/ipa.md
Discourse and narrative analysis	How something is said is the object of interest	references/discourse-narrative.md
Rapid qualitative analysis	Decision lands in days	references/rapid-qual.md
Integration with quantitative data	Qualitative sources plus survey or usage data	references/integration.md

The skill recommends a method with a one-line reason rather than handing over a menu of method names. You do not need to know the methods to use it.

How it runs

Phase 0. Five scope questions before any analysis: method, depth, orientation (inductive or deductive), extra deliverables, and attribution rules. Asked every time, skipped for anything you already answered in conversation.

Data prep. scripts/prep_transcript.py normalizes the sources and assigns stable turn IDs.

Method-agnostic core. Full-corpus read before coding, declared analytic stance, an audit trail of code assignments, prevalence counted by distinct speaker with the denominator stated, and uncertainty flagged inline.

Method procedure. The skill reads the relevant reference and follows that method's own steps.

Deliverables. Two always, plus whatever was requested at Phase 0.

Transcript prep script
bash
python3 scripts/prep_transcript.py INPUT \
  --outdir prepped \
  --source-label kickoff-2026-08-18 \
  --facilitators "Name A,Name B"

Accepts .vtt, .srt, .txt, .md, .docx, .csv. Writes four files:

Output	Contents
<label>_normalized.md	One block per turn, with turn ID, speaker, and timestamp
<label>_turns.jsonl	Machine-readable turns
<label>_roster.csv	Speakers with turn counts, word counts, and share of words
<label>_warnings.txt	Transcription damage, unidentified speakers, generic labels, air-time skew

It merges consecutive turns from one speaker, normalizes casing so DR. LIN and Dr. Lin collapse into one person, and avoids treating line labels like Note: as speakers.

Outputs

Produced on every run:

Analytic framework with definitions. Themes, categories, a matrix, or a theory, depending on method. Carries a method note stating the method, orientation, coding level, corpus, whose speech counted as data, attribution scheme, analyst positioning, and limitations.
Quote bank with speaker attribution. One row per quote with verbatim text, speaker, speaker class, source, turn ID, the finding it supports, and a usability note flagging anything that should not circulate.

Available on request:

Prioritized action or bug backlog with severity and evidence trail
Slide-ready bullets with prevalence and a paired quote
Cross-event or longitudinal comparison, including item-level tracking with elapsed days
Executive summary, 200 to 400 words
Design principles

Traceability over polish. Turn IDs run through codes, quotes, and prevalence counts, so any claim can be checked against the transcript in seconds.

Prevalence stated honestly. Distinct speakers over a stated denominator, split internal against external. Never mention counts as a proxy for importance, outside content analysis where counting is the method.

Method vocabulary stays fenced. Kappa belongs to content analysis and coding-reliability TA. Saturation belongs to grounded theory. Central organizing concepts belong to reflexive TA. Each reference states what does not belong in it, since borrowed terms are the clearest sign an analysis was not thought through.

Uncertainty surfaces rather than smoothing. Damaged audio, unidentified speakers, and single-source claims get flagged in the output, not tidied away.

Quotes stay verbatim. Elisions marked with […]. No silent grammar fixes, no reordering.

Some requests get declined with an alternative. IPA on group or workshop data, since group talk flattens the individual account IPA exists to preserve. Grounded theory on a closed corpus, since theoretical sampling is not available. Rapid analysis presented as thematic analysis. In each case the skill names what it can do instead.

What it does not do
Quantitative survey statistics, sentiment scoring, or plain transcript summarization with no analytic claim
Audio transcription. Bring text.
Multi-analyst coordination. It can support framework analysis for a team, but version control of the framework stays with a person.
Automatic method validation. It flags mismatches between question and method; the call remains yours.
Notes
Reference files load only when the method calls for them, so context stays lean.
references/deliverables.md and references/comparison.md are method-general. Where they say "finding," read your method's analytic unit.
Rapid analysis keeps turn IDs and templates, so a rapid pass can be extended into a full analysis without redoing prep.
