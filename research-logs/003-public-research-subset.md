# Research Log 003 - Public Research Subset Release
## Cinematic Emotion Lab

**Date:** 2026-08-01
**Release milestone:** v0.2 - Computational Annotation Preview
**Status:** Public release record

---

## What This Log Documents

This entry records the v0.2 public release of the Cinematic Emotion Lab research
program. The release constitutes the first disclosure of research data from the
active corpus: a curated public subset of acoustic feature vectors, the formal
annotation schema, and expanded methodology documentation.

This is a record of what was released, the rationale behind the curation decisions,
and what the public subset does and does not represent.

---

## The Public Subset

A curated subset of the Cinematic Emotion Lab research corpus has been prepared
for public release. The subset consists of acoustic feature matrices derived from
the cinematic audio cue corpus. It is representative of the corpus's emotional
and structural diversity without being exhaustive.

**What the public subset contains:**
- 71-dimensional acoustic feature vectors (one row per cinematic audio cue)
- Cue identifiers (anonymized: `CEL-2026-XXXX` format)
- Structural metadata: tempo category, harmonic mode, narrative position,
  narrative function (field values included)
- Corpus statistics: duration distribution, tempo range, harmonic mode breakdown

**What the public subset does not contain:**
- Primary emotion labels (`primary_emotion` field withheld)
- Emotional intensity scores (`emotional_intensity` field withheld)
- Orchestration density values (`orchestration_density` field withheld)
- Secondary emotion labels (`secondary_emotion` field withheld)
- Composer notes (`composer_notes` field withheld)
- Annotation confidence scores (`annotation_confidence` field withheld)
- Raw audio files (not committed - IP protection)

**Curation rationale:**
The public subset is sized to demonstrate the corpus's structure and enable
community engagement without exposing the full annotation ground truth that
underpins EXP-002 classification experiments. It is designed to answer the
question "is the dataset real and structured?" - not to enable independent
replication of the classification results before publication.

---

## Annotation Schema Release

The formal annotation schema (`datasets/annotations/schema.json`) is released
in full as part of v0.2. This includes:

- Complete field definitions for all annotation dimensions
- Ordinal scale specifications with per-level descriptions
- Edge case flag taxonomy
- Annotation protocol metadata
- Release history and citation guidance

The schema is public regardless of the data release schedule. A rigorous and
transparent annotation protocol is a prerequisite for any claim about ground
truth quality, and the research community should be able to evaluate the
methodology independently of the results.

---

## Corpus Statistics (Public)

The following aggregate statistics describe the full annotation corpus.
Per-clip values remain withheld.

**Harmonic mode distribution:**
The corpus spans all four harmonic mode categories: major, minor, modal, and atonal.
Modal and minor categories are more heavily represented, consistent with the
expressive priorities of the cinematic cues in the corpus.

**Narrative position coverage:**
All five narrative positions (opening, rising, climax, falling, resolution) are
represented. Climax and rising cues are the most common. Resolution cues are the
most compositionally constrained and exhibit the narrowest feature space range.

**Narrative function coverage:**
Underscore cues constitute the majority of the corpus. Stingers and theme
statements are represented in smaller but analytically significant numbers.

**Edge case prevalence:**
A non-trivial proportion of the corpus carries at least one edge case flag.
The most common flags are `intentional_expectation_violation` and
`deliberate_ambiguity`. This distribution is consistent with the research
hypothesis that compositional divergence from acoustic convention is a
systematic and recurring feature of film scoring practice.

Detailed statistics will be released with v0.25 (September 2026) alongside
the full annotation intelligence framework documentation.

---

## Observations on the Annotation Process

Several structural patterns emerged during the annotation pass that are worth
documenting at the public log level, without disclosing quantitative findings:

**Intensity is not loudness.**
The `emotional_intensity` scale consistently diverged from what a naive loudness
metric would predict. Several of the highest-intensity cues in the corpus are
written at pianissimo dynamic levels. The scale is measuring something the
amplitude envelope does not fully capture.

**Ambiguity is compositionally deliberate.**
Every cue annotated as `ambiguity` has a clear compositional rationale for that
designation. None of the ambiguous annotations reflect annotation uncertainty.
The composer knew exactly what they were building - they were building ambiguity.
This is theoretically significant: `ambiguity` as a stable, intentional category
is a challenge to any system that treats emotion classification as a disambiguation
task.

**Edge cases cluster around expectation violations.**
The `intentional_expectation_violation` flag was applied more frequently than
anticipated during schema design. Composers - or at least this composer - appear
to work against acoustic-emotional convention as a regular expressive strategy,
not an exceptional one. The model's behavior on flagged cues will be the focus
of the most theoretically interesting portions of EXP-004.

These observations are documented here as qualitative field notes. They will
be formally analyzed, quantified, and contextualized in the publication.

---

## Open Questions Carried Forward

- Should the public subset include feature vectors for edge-case-flagged cues,
  or does their inclusion without labels create misleading distributional signals?
  Current decision: include flagged cues without the flag field values.

- The `composer_notes` field contains entries that are compositionally revealing
  even without the label values. Selection criteria for the v0.25 sample release
  need tightening.

- Corpus expansion: the current corpus reflects a relatively homogeneous
  compositional voice. Whether the classification model generalizes beyond
  this voice is an open question, reserved for future work.

---

## Release Status

| Artifact | Status |
|----------|--------|
| `datasets/annotations/schema.json` | Released - v0.2 |
| `datasets/processed/public_subset_features.csv` | Released - v0.2 |
| `docs/methodology-preview.md` | Updated - v0.2 |
| `NB-EDA-001` | Released - v0.2 |
| Corpus statistics (aggregate) | Released - v0.2 |
| Per-clip emotion labels | Withheld |
| Full annotated corpus | Withheld pending publication |

---

*Log filed by Bernard G. - Cinematic Emotion Lab*
*v0.2 - Computational Annotation Preview*
