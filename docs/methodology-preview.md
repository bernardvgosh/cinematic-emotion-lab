# Methodology Preview
## Cinematic Emotion Lab

> *This document provides a public-facing overview of the research methodology. Full methodological detail, code, and data will be released with publication.*

---

## Foundational Premise

The methodology rests on a single contestable premise: **emotional states in cinematic music are not subjective responses - they are structured acoustic events.** If a composer can reliably produce grief, tension, or triumph through deliberate musical construction, those emotional categories must leave measurable traces in the audio signal.

Testing this premise - and characterizing precisely where it breaks down - is as important as confirming it where it holds.

---

## Research Phases

### Phase 1 · Signal Analysis
Multi-domain acoustic feature extraction from raw cinematic audio clips. 71-dimensional feature vector per clip. Full extraction pipeline documented in `notebooks/experiments/NB-EXP-001`.

### Phase 2 · Semantic Annotation
Composer-led emotional labeling using a structured schema. Ground truth is compositional *intent*, not listener *perception* - a deliberate methodological choice with full theoretical justification.

### Phase 3 · Supervised Learning
Classification and regression models trained on the annotated feature matrix. Classical baselines established before deep learning approaches are applied.

### Phase 4 · Interpretive Analysis
Systematic comparison of model predictions against composer annotations. The Composer Gap - the structured divergence between computational perception and compositional intent - is the primary research output.

---

## Annotation Schema

```json
{
  "primary_emotion":       "tension | triumph | grief | suspense | joy | dread | longing | ambiguity",
  "secondary_emotion":     "string | null",
  "emotional_intensity":   "1 – 5",
  "narrative_position":    "opening | rising | climax | falling | resolution",
  "harmonic_mode":         "major | minor | modal | atonal",
  "orchestration_density": "1 – 5",
  "composer_notes":        "free text"
}
```

---

*Full methodology: [METHODOLOGY.md](METHODOLOGY.md)*
