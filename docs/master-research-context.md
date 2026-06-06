# Master Research Context
## Cinematic Emotion Lab - Complete Research Program Reference

> This document is the canonical single-source reference for the Cinematic Emotion Lab
> research program. It consolidates project overview, research objectives, methodology,
> positioning, disclosure rules, and operational standards into one authoritative document.
> All other documentation in this repository draws from or extends this source.

---

## 1. Project Overview

**Lab name:** Cinematic Emotion Lab

**Research domain:** Interdisciplinary AI research at the intersection of music information
retrieval (MIR), affective computing, computational musicology, and interpretive theory.

**Primary research problem:**
Film music is a precision emotional engineering system. A composer writing for picture
constructs specific emotional states - grief, tension, triumph, dread - at specific
timecodes, using technical acoustic tools: harmonic choice, rhythmic density, dynamic
arc, orchestral texture. This research asks: can that construction be computationally
characterized, and where does the machine's perception systematically diverge from the
composer's intent?

**Research form:** Active, ongoing research program. Substantially complete at the experimental
level. Results are embargoed pending publication. Public disclosure is staged and deliberate.

**Repository:** https://github.com/bernardvgosh/cinematic-emotion-lab

**Primary researcher:** Bernard G. - Film Composer, AI Architect, Computational Musicology Researcher.

**License:** MIT (code). Data and findings embargoed pending publication.

---

## 2. Research Objectives

The research program has four primary objectives, each tied to a numbered experiment
in the pipeline:

**Objective 1 - Feature space characterization (EXP-001)**
Build and validate a 71-dimensional acoustic feature representation of cinematic audio
that captures the multi-domain signal structure underlying emotional content in film music.

**Objective 2 - Emotion classification (EXP-002)**
Demonstrate that cinematic emotional categories are computationally separable within this
feature space, and characterize which acoustic domains carry the most discriminative signal.

**Objective 3 - Harmonic tension modeling (EXP-003)**
Develop a sequence model capable of predicting harmonic tension trajectory over time,
transitioning from static clip-level classification to dynamic emotional arc modeling.

**Objective 4 - Composer Gap characterization (EXP-004)**
Systematically characterize the divergence between machine predictions and
composer-annotated intent - the Composer Gap - and produce a structured taxonomy of
failure modes that illuminates the limits of acoustic emotion recognition in the
cinematic domain.

---

## 3. Research Questions

### Primary Questions

**RQ1:** What acoustic features reliably encode intended cinematic emotion, as defined
by the composer's stated compositional intent?

**RQ2:** Can harmonic tension be predicted as a temporal sequence rather than a static
label, and does that prediction align with composer-annotated narrative arc?

**RQ3:** Where and how does machine acoustic perception systematically diverge from
composer-annotated emotional intent - and what does that divergence reveal about the
limits of affective AI in creative domains?

### Secondary Questions

**RQ4:** Does narrative position (opening, rising, climax, falling, resolution) leave
measurable and predictive traces in the acoustic signal of a cinematic cue?

**RQ5:** Which of the eight emotion categories in this framework are most acoustically
distinctive, and which exhibit the greatest composer-machine divergence?

**RQ6:** Is harmonic mode (major, minor, modal, atonal) a primary or secondary predictor
of emotional category, relative to other acoustic domains in the feature space?

**RQ7:** Does the 71-dimensional feature space contain redundant dimensions that can be
reduced without loss of discriminative power, or does each domain contribute independently?

### Speculative Questions

**RQ8:** Is there a learnable compositional grammar underlying the emotional architecture
of film scoring - a set of structural rules that predict how emotion categories sequence
and transition within a film score?

**RQ9:** Can a model trained on composer-annotated intent transfer to listener-perception
labels, or do these two annotation targets produce fundamentally different learned
representations?

**RQ10:** What would it mean for a machine to "understand" a film score, and is that
understanding achievable through acoustic analysis alone?

---

## 4. Interdisciplinary Positioning

This research occupies a distinctive intersection:

**Music Information Retrieval (MIR)**
Foundation technology: librosa-based feature extraction, MFCC computation, Chroma CQT,
spectral analysis. Standard MIR methodology applied to a domain-specific corpus.

**Affective Computing**
Research area: computational modeling of emotion from signal data. This research extends
affective computing into the cinematic domain with a non-standard annotation methodology.

**Computational Musicology**
Research tradition: formal analysis of music structure through computational methods.
This research treats the emotional architecture of film scoring as a formal object of study.

**Interpretive Theory**
Novel contribution: the Composer Gap study treats the divergence between computational
and human interpretation as the primary research object, not a source of error to minimize.

**Film Scoring Practice**
Domain authority: the primary researcher is a working film composer. Annotation is not
crowd-sourced - it is professional compositional judgment, applied with technical precision.

**Institutional register anchor:**
MIT Media Lab (interdisciplinary rigor) x OpenAI Research (methodological precision,
staged disclosure) x Hans Zimmer / cinematic scoring tradition (creative authority) x
Film Noir aesthetic (visual identity and tone).

---

## 5. Weekly Research Milestones

Research milestones are tracked at the weekly level in `research-logs/`. The following
table maps releases to approximate research week ranges:

| Release | Research Weeks | Target Date |
|---------|---------------|-------------|
| v0.1 Foundation | Weeks 01-04 (infrastructure) | June 2026 - Released |
| v0.15 Visualization | Weeks 01-04 (first outputs) | July 2026 |
| v0.2 Annotation Preview | Weeks 05-08 | August 2026 |
| v0.25 Annotation Framework | Weeks 05-08 (deep) | September 2026 |
| v0.3 Baseline Results | Weeks 09-14 | October 2026 |
| v0.35 Tension Modeling | Weeks 15-18 | November 2026 |
| v0.4 Composer Gap | Weeks 19-24 | December 2026 |
| v0.5 Interactive Platform | - | Q1 2027 |
| v1.0 Full Disclosure | - | 2027 (timed to publication) |

Weekly logs are committed to `research-logs/` using the template at
`research-notes/weekly-logs/RESEARCH_LOG_TEMPLATE.md`.

Log format: `[week-number]-[topic-slug].md`

---

## 6. Methodology Summary

The research methodology operates across four phases:

**Phase 1 - Signal Analysis**
Raw audio ingestion, normalization (22050Hz, float32, mono), and 71-dimensional
feature extraction via librosa. All clips processed through the same extraction
pipeline. No manual feature selection at this stage.

**Phase 2 - Annotation**
Composer-led emotional labeling. The primary researcher annotates each clip
in the role of film composer - capturing compositional intent as ground truth.
Annotation schema captures 5 dimensions: primary emotion, emotional intensity,
narrative position, harmonic mode, and orchestration density.

**Phase 3 - Machine Learning**
Classical ML baselines (scikit-learn) evaluated against composer annotations.
Sequence models for temporal tension prediction. Transformer architecture comparison
for EXP-003.

**Phase 4 - Interpretive Analysis**
EXP-004: systematic comparison of model predictions against composer annotations.
Divergence taxonomy construction. Feature-level tracing of prediction errors.

Full methodology: [docs/METHODOLOGY.md](METHODOLOGY.md)
Architecture specification: [docs/ARCHITECTURE.md](ARCHITECTURE.md)

---

## 7. Feature Extraction Framework

**Total feature dimensions:** 71 per clip

| Feature Group | Dimensions | Acoustic Domain | Emotional Relevance |
|---------------|------------|-----------------|---------------------|
| MFCCs (13 coeff × mean + std) | 26 | Timbre | Instrumental texture, tonal identity |
| Chroma CQT (12 classes × mean + std) | 27 | Harmony | Key, mode, harmonic color |
| Spectral (centroid, bandwidth, rolloff) | 6 | Spectral shape | Brightness, tension, spectral weight |
| RMS Energy (mean, std, max, dynamic range) | 4 | Dynamics | Loudness, dramatic weight |
| Zero Crossing Rate (mean, std) | 2 | Signal texture | Noisiness, percussive density |
| Tempo | 1 | Rhythm | Pacing, urgency |
| Harmonic/Percussive Ratio (mean, std, max) | 3 | Source structure | Orchestral balance |

**Implementation:** librosa, Python 3.12, numpy, scipy
**Note:** Python 3.12 required. Python 3.13 has arm64 numpy incompatibility on Apple Silicon.

**Extraction notebook:** `notebooks/experiments/NB-EXP-001_cinematic-feature-extraction_2026-06-06.ipynb`

---

## 8. Emotional Annotation Framework

**Emotion categories (8):**
`tension` · `triumph` · `grief` · `suspense` · `joy` · `dread` · `longing` · `ambiguity`

**Annotation dimensions (5):**

| Field | Type | Values |
|-------|------|--------|
| primary_emotion | categorical | 8 emotion categories (above) |
| emotional_intensity | ordinal | 1 (minimal) to 5 (maximal) |
| narrative_position | categorical | opening · rising · climax · falling · resolution |
| harmonic_mode | categorical | major · minor · modal · atonal |
| orchestration_density | ordinal | 1 (sparse) to 5 (dense) |

**Ground truth principle:**
Annotations capture the composer's stated intent - what was being constructed -
not listener emotional response. This is the primary methodological distinction
from prior work in music emotion recognition.

**Annotation schema:** `datasets/annotations/schema.json`
**Annotation protocol:** `docs/METHODOLOGY.md` (Phase 2)

---

## 9. Composer Interpretation Layer

The composer interpretation layer is the mechanism by which professional compositional
judgment enters the system as formal ground truth.

**Who annotates:** Bernard G., primary researcher, in the explicit role of film composer
and as the composer of the audio material in the corpus. This is first-person
compositional intent annotation.

**What is being captured:**
Not "what does this sound like to a listener" but "what was I building when I wrote this,
and why did I make these specific harmonic, rhythmic, and timbral choices."

**Why this matters:**
A model trained on listener perception labels is learning to predict audience response.
A model trained on compositional intent labels is learning to predict compositional
decision-making. These are different tasks with different theoretical implications.

**Annotation authority:**
The composer is the ground truth. Not the averaged crowd, not a panel of musicologists.
The person who made the creative decisions is the primary annotator. This is unusual.
It is also more precise.

**EXP-004 design note:**
The Composer Gap study compares model predictions against these intent annotations.
A gap between prediction and annotation is not error to minimize - it is a window
into what the acoustic signal does and does not communicate about compositional intent.

---

## 10. AI/ML Modeling Layer

**Experiment sequence:**

**EXP-001 - Feature extraction pipeline**
Status: Released (v0.1)
Output: 71-dimensional feature vectors per clip, cinematic visualizations, CSV export
Notebook: `NB-EXP-001_cinematic-feature-extraction_2026-06-06.ipynb`

**EXP-002 - Baseline emotion classification**
Status: Embargoed (target release: v0.3, October 2026)
Architecture: Classical ML baselines (Random Forest, SVM, Gradient Boosting) on the
71-dimensional feature space. Evaluated against composer annotations.
Output: Classification results (embargoed), feature importance rankings, UMAP visualization.

**EXP-003 - Harmonic tension sequence modeling**
Status: Embargoed (target release: v0.35, November 2026)
Architecture: LSTM and Transformer comparison for temporal tension prediction.
Input: Sequence of feature vectors across clip timepoints.
Output: Tension trajectory over time, aligned to narrative arc.

**EXP-004 - Composer Gap characterization**
Status: Embargoed (target release: v0.4, December 2026)
Design: Systematic comparison of EXP-002 predictions vs. composer annotations.
Output: Divergence taxonomy (4 named failure modes), interpretability framework,
        quantitative divergence metrics (full metrics embargoed).

**Technology stack:**
- Python 3.12
- librosa (feature extraction)
- numpy, scipy, pandas
- scikit-learn (classical ML)
- PyTorch (sequence models)
- Plotly, matplotlib (visualization)
- Jupyter (notebooks)

---

## 11. Narrative Modeling

The narrative modeling layer treats film music as a temporally structured emotional
system, not a collection of independent clips.

**Narrative position taxonomy:**
`opening` · `rising` · `climax` · `falling` · `resolution`

These positions are included in the annotation schema as a primary dimension.
Each clip is annotated with its position within the dramatic arc of the larger cue
or scene sequence.

**Research hypothesis:**
Narrative position leaves measurable traces in the acoustic signal. A rising
section has different spectral and dynamic properties from a climax, even when
both are annotated with the same primary emotion. Controlling for narrative
position should improve classification accuracy.

**Temporal extension:**
EXP-003 models emotional trajectory across time within a single cue. The output
is not a single label but a tension curve - a continuous function representing
how harmonic tension evolves from the first note to the last.

---

## 12. Visualization Systems

**Visualization categories:**

**Signal-level visualizations (NB-VIZ-001)**
- Spectrogram gallery across emotion categories
- Waveform with beat-grid overlay
- RMS dynamic envelope per narrative position

**Feature-level visualizations (NB-VIZ-002)**
- MFCC coefficient heatmap comparison suite
- Chroma radar profiles (12-axis, Plotly)
- Feature distribution histograms per emotion category

**Model-level visualizations (NB-VIZ-003)**
- UMAP feature space projection (cluster structure)
- Feature importance bar charts (relative rankings)
- Confusion matrix visualization (embargoed)

**Temporal visualizations (EXP-003 outputs)**
- Harmonic tension arc curves
- Narrative position overlay on tension trajectory
- Composer-predicted vs. model-predicted arc comparison (embargoed)

**Color palette (cinematic dark):**
- Background: `#0a0a0a`
- Primary accent: `#c9a227` (gold)
- Secondary: `#8b1a1a` (deep red)
- Cool: `#1a3a5c` (deep blue)
- Text: `#e8e8e8`

**Visual identity assets (assets/):**
- `hero-banner.png` - Primary repository hero image
- `cinematic-emotion-pipeline.png` - 7-stage pipeline diagram
- `emotion-heatmap.png` - Temporal emotion heatmap
- `research-architecture.png` - Research architecture infographic
- `spectrogram-intelligence.png` - Spectrogram intelligence visual

---

## 13. Public Release Strategy

The research uses a staged disclosure architecture. Nine releases, each revealing one
deliberate layer of the research without compromising publication-track findings.

**Release philosophy:**
- Methodology before results
- Architecture before performance
- Framing before findings
- Presence before depth

**Release sequence:**

| Release | Theme | Target | Primary Signal |
|---------|-------|--------|----------------|
| v0.1 | Foundation Layer | June 2026 (Released) | The lab exists |
| v0.15 | Visualization Intelligence | July 2026 | The feature space has structure |
| v0.2 | Annotation Preview | August 2026 | The ground truth is real |
| v0.25 | Annotation Intelligence | September 2026 | The composer speaks |
| v0.3 | Baseline Results | October 2026 | The machine has an answer |
| v0.35 | Harmonic Tension | November 2026 | The machine learns trajectory |
| v0.4 | Composer Gap | December 2026 | The gap is the finding |
| v0.5 | Interactive Platform | Q1 2027 | The research becomes an interface |
| v1.0 | Full Disclosure | 2027 | The research is complete |

Full release documentation: [ROADMAP.md](../ROADMAP.md)
Release announcement language: [docs/RELEASE_NOTES.md](RELEASE_NOTES.md)

---

## 14. Staged Disclosure Rules

**What can be disclosed at any stage:**
- Research philosophy, experimental design documentation
- Feature extraction code and notebooks (not results)
- Annotation schema and protocol
- Visual identity and research communication assets
- Architecture diagrams and system documentation

**What requires framing before disclosure:**
- Qualitative characterizations of results
- Visualization outputs without quantitative interpretation
- Feature importance relative rankings (not absolute scores)

**What is embargoed until publication:**
- Per-class accuracy, F1 scores, confusion matrices
- Trained model weights and evaluation artifacts
- Full annotated corpus with composer labels
- Quantitative Composer Gap divergence metrics

**Language for embargoed results:**
> "Quantitative results are withheld pending peer-reviewed publication."
> "Initial experiments establish statistically significant separability. Per-class
> metrics are embargoed."
> "The architecture of this divergence is documented. Quantitative characterization
> is withheld pending publication."

**Never say:** "I can't share the results yet" or "the labels are hidden" or
"I'm still collecting data."

Full disclosure architecture: [STAGED_RELEASE_STRATEGY.md](../STAGED_RELEASE_STRATEGY.md)

---

## 15. GitHub Positioning

**Repository public description:**
> AI research program: cinematic emotion recognition, harmonic tension modeling,
> and computational analysis of composer-machine interpretive divergence in film music.

**Repository topics (GitHub tags):**
`music-information-retrieval` `affective-computing` `computational-musicology`
`film-music` `emotion-recognition` `machine-learning` `python` `librosa`
`jupyter-notebook` `research`

**README structure:**
15 sections, strictly ordered: hero banner - title - research problem - components -
architecture - emotion framework - signal analysis - composer interpretation - what's
public now - what's coming - research status - repository structure - how to follow -
author - license.

**Commit standards:**
Format: `type(scope): description`
Types: `release`, `feat`, `data`, `docs`, `experiment`, `viz`, `refactor`, `fix`
No attribution lines. No "Claude" references anywhere in the repository.

**Git standards:** `GIT_STANDARDS.md`
**Naming conventions:** `NAMING_CONVENTIONS.md`

---

## 16. LinkedIn Positioning

**Primary LinkedIn message:**
This research sits at the intersection of film composition and machine learning.
The question is not "can AI make music" but "can AI understand what music is doing
emotionally, and where does it fail, and what does that failure tell us."

**Audience segmentation:**

For AI/ML audience: Lead with methodology, feature space, embargoed results, publication track.
For film/music audience: Lead with the Composer Gap, compositional intent, the creative stakes.
For academic audience: Lead with the annotation methodology, theoretical novelty, research rigor.

**Post cadence:**
One post per release. No inter-release posts about the research itself.
Weekly research logs create GitHub activity; LinkedIn posts create audience peaks.

**Per-release post angles:** [docs/LINKEDIN_RELEASE_ANGLES.md](LINKEDIN_RELEASE_ANGLES.md)

---

## 17. Terminology Standards

**Use consistently:**

| Term | Definition |
|------|-----------|
| Cinematic Emotion Lab | Full lab name. Never abbreviated to "CEL" in public-facing text. |
| research program | How to describe this work. Not "project" or "experiment." |
| compositional intent | What the composer designed. The annotation target. |
| composer annotations | The ground truth labels. Not "my labels" or "manual labels." |
| cinematic audio cues | The audio material. Not "clips" or "samples." |
| the Composer Gap | Named divergence phenomenon. Always capitalized. |
| embargoed | Results withheld pending publication. Not "hidden" or "unavailable." |
| staged disclosure | The release framework. Not "rolling release" or "gradual release." |
| 71-dimensional feature space | Always state the exact number. |
| EXP-001 through EXP-004 | Always use experiment codes in technical references. |
| NB-EXP, NB-EDA, NB-VIZ | Notebook type prefixes. Always use the coding system. |

**Do not use:**
"clips" (use "cinematic audio cues") · "labels redacted" (use "withheld pending publication") ·
"record 30 clips" (use "curate a research corpus") · "I'm building a model" (use "a classification
system is under development") · "good results" (use "statistically significant separability") ·
"my research" (use "this research program" or "the research").

Full vocabulary system: [docs/PUBLIC_POSITIONING.md](PUBLIC_POSITIONING.md)

---

## 18. Research Philosophy

The Cinematic Emotion Lab operates under three foundational commitments:

**Rigor Without Reductionism**
Computational analysis of emotion risks reducing a complex human phenomenon to a
number. This research resists that reduction by treating the Composer Gap - the
space between the number and the intent - as the primary object of study. The
goal is not to compress emotion into a vector. The goal is to understand where
that compression fails and what the failure reveals.

**Honesty About Limits**
This research will produce a model that does not fully understand film music.
That is not a failure condition - it is the expected outcome of any honest
investigation into a complex, culturally embedded human practice. The research
is designed to characterize those limits precisely, not to paper over them with
benchmark performance.

**Interdisciplinary Seriousness**
This research does not use film music as a convenient application domain for a
machine learning system. It treats cinematic composition as a first-class
intellectual subject with its own logic, history, and technical vocabulary.
The machine learning methods serve the research question - not the reverse.

Full philosophy: [docs/RESEARCH_PHILOSOPHY.md](RESEARCH_PHILOSOPHY.md)

---

## 19. Future Directions

The following research directions are not part of the current publication-track program
but represent credible extensions of this work:

**Cross-domain transfer**
Apply the cinematic emotion model to adjacent audio domains (game music, advertising music,
concert music) to test whether the learned representation generalizes or is domain-specific.

**Listener perception comparison study**
Collect listener emotion labels for the same corpus and formally compare listener-perception
ground truth against composer-intent ground truth. Quantify the gap between these two
annotation philosophies.

**Generative extension**
Use the learned feature-emotion mappings to condition a generative audio model toward
specified emotional targets. Test whether the model can produce cues that score high
on the classification system.

**Real-time emotional arc analysis**
Extend the tension modeling system to operate in real time, enabling emotion arc
visualization synchronized to live film playback.

**Expanded corpus**
Extend the corpus beyond the primary researcher's compositions to include a diverse
set of film composers, testing whether the classification system generalizes across
compositional styles.

---

## 20. What Is Intentionally Withheld

The following materials exist in the research program but are not part of any planned
public release before formal publication:

**Raw audio files**
The cinematic audio cues are original compositions. They are not committed to the
repository for IP protection reasons. Only processed acoustic features are released.

**Full composer annotation corpus**
Complete annotation labels are withheld. A curated subset (features only, labels withheld)
is released with v0.2.

**Quantitative classification results**
Per-class accuracy, F1 scores, and confusion matrices from EXP-002 are embargoed.
Qualitative characterization is released with v0.3.

**Trained model weights**
Model weights from EXP-002 and EXP-003 are withheld pending publication.
Released with v1.0.

**Quantitative Composer Gap metrics**
Divergence magnitude, per-failure-mode prevalence statistics, and gap quantification
from EXP-004 are embargoed. Qualitative taxonomy released with v0.4.

**Theoretical conclusions**
Final interpretive claims about what the Composer Gap reveals about affective AI
are withheld for the paper. Public releases establish context and stakes without
stating conclusions.

---

*Cinematic Emotion Lab - Master Research Context v1.0 - June 2026*
*Bernard G. - Film Composer · AI Architect · Computational Musicology Researcher*
