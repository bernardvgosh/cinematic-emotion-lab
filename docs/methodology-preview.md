# Methodology Preview
## Cinematic Emotion Lab

> This document provides a structured public overview of the research methodology.
> Full methodological specification, code, and annotated data will be disclosed
> through the staged release schedule documented in ROADMAP.md and through
> formal publication channels. See STAGED_RELEASE_STRATEGY.md for the
> disclosure architecture governing what is public at each release stage.

---

## Foundational Premise

The methodology rests on a single contestable premise:

> **Emotional states in cinematic music are not subjective responses - they are
> structured acoustic events.**

If a composer can reliably produce grief, tension, or triumph through deliberate
musical construction, those emotional categories must leave measurable traces in
the audio signal. The acoustic tools of film scoring - harmonic mode selection,
rhythmic density, dynamic arc, spectral texture, orchestration weight - are
applied with technical precision. That precision is, in principle, recoverable.

Testing this premise - and characterizing precisely where it fails - is as
important to this research as confirming where it holds. The Composer Gap
study (EXP-004) exists specifically to investigate the failure modes.

---

## Research Phases

### Phase 1 - Signal Analysis

**Status: Complete. Methodology and code public (NB-EXP-001).**

Raw cinematic audio is ingested at 22050Hz, converted to mono float32, and
processed through a multi-domain acoustic feature extraction pipeline. Each cue
produces a 71-dimensional feature vector covering seven acoustic domains: timbral
identity (MFCCs), harmonic content (Chroma CQT), spectral shape, dynamic profile
(RMS energy), signal texture (zero crossing rate), rhythmic pacing (tempo), and
source structure (harmonic/percussive separation ratio).

The 71-dimensional representation is deliberately over-complete at this stage.
No manual feature selection is applied prior to modeling. Dimensionality reduction
and feature importance analysis are downstream operations performed within the
experimental pipeline, not at the extraction layer.

Feature extraction pipeline: [notebooks/experiments/NB-EXP-001](../notebooks/experiments/)

---

### Phase 2 - Composer Annotation

**Status: Complete. Schema public (datasets/annotations/schema.json). Labels embargoed.**

The primary researcher annotates each cinematic audio cue in the explicit role
of film composer - capturing compositional intent as the annotation target.
This is a first-person annotation process: the annotator is the composer of
the material being annotated.

**The annotation target is compositional intent, not listener perception.**

This distinction is the most methodologically significant design decision in the
research program. A model trained on listener-perception labels learns to predict
audience emotional response. A model trained on compositional intent labels learns
to predict compositional decision-making. These are different tasks. The theoretical
implications are examined in detail in EXP-004 and in [docs/COMPOSER_VS_AI.md](COMPOSER_VS_AI.md).

The annotation schema captures five primary dimensions per cue:

| Dimension | Type | Description |
|-----------|------|-------------|
| Primary emotion | Categorical (8) | The dominant emotional category being constructed |
| Emotional intensity | Ordinal (1-5) | Dramatic weight, calibrated to compositional density |
| Narrative position | Categorical (5) | Position within the dramatic arc of the scene |
| Harmonic mode | Categorical (4) | Tonal framework: major, minor, modal, atonal |
| Orchestration density | Ordinal (1-5) | Textural density of the ensemble writing |

Two extended fields - `narrative_function` and `tempo_category` - capture
compositional role and temporal character beyond the primary five dimensions.
A free-text `composer_notes` field documents edge cases, deliberate convention
violations, and inter-field tensions that resist clean categorical assignment.

Full schema specification: [datasets/annotations/schema.json](../datasets/annotations/schema.json)
Full protocol: [docs/METHODOLOGY.md](METHODOLOGY.md)

---

### Phase 3 - Supervised Learning

**Status: Active. Results embargoed pending publication.**

Classification and sequence modeling experiments are conducted against the
composer-annotated corpus. The experimental protocol follows a deliberate
progression: classical ML baselines are established before deep learning
approaches are applied, ensuring that benchmark performance is interpretable
and that architectural complexity is justified by measurable gain.

**EXP-002 - Baseline emotion classification (target: v0.3, October 2026)**
Classical ML baselines (Random Forest, Support Vector Machine, Gradient
Boosting Classifier) trained on the 71-dimensional feature space. Evaluated
against composer annotations using stratified cross-validation. Feature
importance analysis identifies which acoustic domains carry the most
discriminative signal for cinematic emotion categorization.

**EXP-003 - Harmonic tension sequence modeling (target: v0.35, November 2026)**
Temporal sequence model treating each cinematic cue as an ordered sequence of
frame-level feature vectors rather than a single aggregated representation.
LSTM and Transformer architectures compared on the harmonic tension prediction
task. Output is a continuous tension trajectory rather than a static class label.

All quantitative results - per-class accuracy, F1 scores, confusion matrices,
and model evaluation artifacts - are embargoed pending peer-reviewed publication.

---

### Phase 4 - Interpretive Analysis

**Status: Active. EXP-004 design public. Results embargoed pending publication.**

The final experimental phase is the Composer Gap study: a systematic comparison
of machine predictions from EXP-002 against composer-annotated ground truth, with
the explicit objective of characterizing the structure of divergence rather than
minimizing it.

Where prior music emotion recognition research treats prediction-annotation
disagreement as an error metric, this research treats that disagreement as a
research object. The Composer Gap - the patterned, reproducible divergence
between acoustic prediction and compositional intent - is the primary theoretical
output of the program.

Early analysis has identified a structured taxonomy of divergence failure modes.
The qualitative architecture of this taxonomy will be disclosed with v0.4
(December 2026). Quantitative characterization is embargoed.

Theoretical framing: [docs/COMPOSER_VS_AI.md](COMPOSER_VS_AI.md)

---

## The Annotation Methodology in Depth

The choice to use compositional intent as annotation target - rather than the
listener-perception protocols standard in music emotion recognition - requires
explicit methodological justification.

**The standard approach and its limitations:**
Most music emotion recognition (MER) research establishes ground truth through
listener annotation: survey participants rate music on valence-arousal dimensions,
or apply categorical emotion labels from a standardized set. This produces
psychoacoustically grounded data that reflects real audience response. Its
limitation is that it measures response, not construction. The acoustic features
that predict audience emotional response are not necessarily the same features
that a composer deploys to construct emotional states.

**The compositional intent approach:**
This research establishes ground truth from the other side of the creative act.
The composer annotates each cue with what they were building, not what they expect
audiences to feel. This produces a dataset that maps acoustic decisions to
intentional emotional constructions - a different but equally valid research target,
with different downstream implications.

**Why this matters for the Composer Gap:**
A model trained on listener perception is optimal for predicting audience response.
A model trained on compositional intent is optimal for predicting compositional
decision-making. The Composer Gap - the gap between what the model predicts and
what the composer intended - is structurally different depending on which annotation
target was used for training. This research uses compositional intent throughout.
The implications of that choice will be examined in the publication.

---

## Methodological Commitments

**1. No post-hoc annotation.**
All annotations are derived from the composer's recall of original compositional
intent, supported by compositional notes and materials from the creation process.
No annotation is applied retrospectively based on acoustic analysis outputs.

**2. Edge cases are retained, not resolved.**
Cues that resist clean categorical assignment are retained in the corpus with
low-confidence flags and edge-case documentation. They are analyzed as a distinct
category in EXP-004. The model's behavior on edge cases is as theoretically
interesting as its behavior on canonical examples.

**3. The methodology is public; the results are not.**
This document, the annotation schema, and the feature extraction pipeline are
fully public. Per-clip labels, classification results, and quantitative findings
are embargoed. The research is designed to be reproducible from the public
methodology before the results are available.

---

*Full methodology documentation: [docs/METHODOLOGY.md](METHODOLOGY.md)*
*Architecture specification: [docs/ARCHITECTURE.md](ARCHITECTURE.md)*
*Annotation schema: [datasets/annotations/schema.json](../datasets/annotations/schema.json)*

---

*Cinematic Emotion Lab - Methodology Preview v2.0 - August 2026*
