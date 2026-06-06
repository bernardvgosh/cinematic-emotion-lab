# Public Positioning Framework
## Cinematic Emotion Lab - Language System and Framing Guide

> This document defines how the Cinematic Emotion Lab describes itself, its research,
> and its findings in all public-facing communication. It is a living standard, not
> a one-time document. Every public statement about this research should pass through
> this framework before release.

---

## Positioning Statement

**One sentence:**
> Cinematic Emotion Lab is an interdisciplinary AI research program developing
> computational systems for cinematic emotion recognition, harmonic tension
> modeling, and the formal analysis of composer-machine interpretive divergence
> in film music.

**One paragraph:**
> The Cinematic Emotion Lab investigates whether the emotional architecture
> of film music - the precision system by which a composer constructs grief,
> tension, or triumph at a specific timecode - can be computationally modeled
> and formally characterized. The research operates across music information
> retrieval, affective computing, computational musicology, and interpretive
> theory. Ground truth is established through composer annotation rather than
> listener perception, producing a methodologically distinctive dataset and a
> novel experimental framework for studying the gap between machine perception
> and compositional intent.

---

## Institutional Register

This research is communicated at the register of a frontier AI research program.
The following comparators are not claimed relationships - they are register anchors
that calibrate tone and seriousness.

**Tone calibrated to:**
- MIT Media Lab (interdisciplinary rigor, public research communication)
- OpenAI Research (methodological precision, staged disclosure, technical depth)
- A-list film scoring practice (creative authority, emotional stakes)

**What this means in practice:**
- Never minimize the research scope. It is not "a project" or "an experiment."
  It is a research program with a defined theoretical contribution.
- Never hedge unnecessarily. The methodology is sound. State it as such.
- Never oversell unverified claims. Results that are embargoed stay embargoed.
- Write as if the research will be cited.

---

## Vocabulary System

### Approved Terms

| Avoid | Use Instead |
|-------|------------|
| "project" | "research program" |
| "trying to figure out" | "investigating" / "under active study" |
| "clips" | "cinematic audio cues" / "annotated audio segments" |
| "labels" | "composer annotations" / "ground truth labels" |
| "I labeled them" | "annotated by the primary researcher" |
| "record 30 clips" | "curate a research corpus" |
| "labels redacted" | "labels withheld pending publication" |
| "I'm building a model" | "a classification system is under development" |
| "dataset" (casual) | "annotated corpus" / "research dataset" |
| "results" (premature) | "preliminary findings" / "embargoed results" |
| "my research" | "the research program" / "this research" |
| "I think" | "working hypothesis" / "current evidence suggests" |
| "demo" | "proof-of-concept implementation" / "research prototype" |
| "good results" | "statistically significant separability" |
| "the model is pretty accurate" | "baseline classification demonstrates task feasibility" |

### Core Terminology

**Cinematic emotion recognition** - The computational classification of emotional
content in film music based on acoustic feature analysis.

**Compositional intent** - The emotional target a composer constructs when writing
for picture, as distinct from audience emotional response. This is the primary
annotation target in this research.

**The Composer Gap** - The structured, measurable divergence between machine
predictions and composer-annotated emotional intent. The central theoretical
contribution of EXP-004.

**71-dimensional acoustic feature space** - The feature representation used in
this research: MFCCs (26), Chroma CQT (27), Spectral (6), RMS Energy (4),
Zero Crossing Rate (2), Tempo (1), Harmonic/Percussive Ratio (3).

**Staged disclosure** - The deliberate, sequenced release of research artifacts
to build a public research record aligned to publication, without prematurely
disclosing protected findings.

**Embargoed** - Results or materials withheld from public release pending
peer-reviewed publication. Not "hidden" or "secret" - embargoed. This is
a standard research term.

**Ground truth** - Composer annotations establishing the correct emotional label
for each audio cue. Derived from compositional intent, not listener perception.

---

## Framing the Research Problem

### The Central Stakes

Film music is not decoration. It is a precision emotional engineering system.
A composer writing for picture constructs specific emotional states at specific
timecodes, against specific visual events. This is not approximate - it is
intentional, technically executed, and repeatable.

This research asks a direct question: **can that construction be computationally
characterized?** And if not perfectly - where does the machine's perception
diverge from the composer's intent, and what does that divergence reveal about
the nature of musical emotion?

### What Makes This Research Novel

Three methodological distinctions separate this work from prior art:

1. **Ground truth from compositional intent** - Most music emotion recognition
   research uses listener perception as annotation. This research uses the
   composer's stated intent. The distinction is not minor: it changes what
   the model is learning to predict.

2. **Cinematic domain specificity** - Film music has structural properties
   (narrative position, picture-lock constraints, dramatic function) that
   general music emotion recognition does not account for. This research
   treats cinematic context as a first-class variable.

3. **The Composer Gap as primary finding** - Most MER research treats
   disagreement between prediction and annotation as error to minimize.
   This research treats that divergence as the primary object of study.

---

## Positioning Against Adjacent Fields

### vs. General Music Emotion Recognition (MER)
> "This research extends standard MER methodology into the cinematic domain,
> with the additional distinction that ground truth is established through
> compositional intent rather than listener perception. The Composer Gap study
> treats prediction-annotation divergence as a theoretical object rather than
> an error metric."

### vs. Affective Computing
> "The affective computing framing focuses on human response to audio stimuli.
> This research inverts that framing: it asks what the composer intended, not
> what the listener felt. The implication is that machine emotion recognition
> may be optimizing against the wrong target."

### vs. Music Information Retrieval (MIR)
> "This research employs standard MIR feature extraction methodology - librosa,
> MFCC, Chroma CQT - within a domain-specific application framework. The
> technical foundation is established; the novel contribution is the application
> domain and the annotation methodology."

---

## Publication Trajectory Language

When asked about publication plans:

> "The research is proceeding on a publication track. Staged public disclosure
> is designed to build a public research record aligned to formal submission.
> Significant findings are embargoed and will be disclosed through peer-reviewed
> publication channels."

When asked if the paper is written:

> "The research program is active. A publication is being developed in parallel
> with the experimental work."

When asked for results:

> "Preliminary findings demonstrate task feasibility and establish initial
> characterization of the feature space. Quantitative results are withheld
> pending peer review."

---

## What This Research Is Not

To prevent mischaracterization, be explicit about scope:

- This is not a music recommendation system
- This is not a mood detection tool for consumer applications
- This is not a generative AI for film music
- This is not a listener sentiment analysis project
- This is research into the structure of emotional communication in film scoring,
  with implications for both computational musicology and AI interpretability

---

*Cinematic Emotion Lab - Public Positioning Framework v1.0 - June 2026*
