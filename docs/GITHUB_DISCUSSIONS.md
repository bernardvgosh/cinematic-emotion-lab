# GitHub Discussions — Topic Architecture
## Cinematic Emotion Lab

> This document defines the GitHub Discussions categories and seed topics for
> the Cinematic Emotion Lab repository. Discussions are structured to invite
> substantive engagement from AI/ML researchers, computational musicologists,
> film composers, and theorists - without creating a forum that requires
> disclosing embargoed findings.
>
> Each category has a defined purpose and a set of seed questions. Seed questions
> are written to generate intellectual traction. They are not prompts for
> sharing unpublished results.

---

## Discussion Categories

### Category 1 — Cinematic Emotion Modeling

**GitHub label:** `discussion:emotion-modeling`
**Audience:** AI/ML researchers, MIR practitioners, affective computing researchers
**Purpose:** Technical discussion of methodology, feature design, and modeling architecture

---

**Seed Topic A: On the annotation target problem in music emotion recognition**

Most music emotion recognition research establishes ground truth from listener perception.
This research uses compositional intent instead. The two are related but not equivalent:
a composer constructing grief and a listener reporting grief are responding to and
producing fundamentally different signals.

Questions worth discussing:
- What does a classification model actually learn when trained on listener-perception
  labels vs. compositional intent labels?
- Are there existing MER datasets that capture compositional intent, or is this
  primarily a listener-perception field?
- Is compositional intent a more or less stable annotation target than listener
  perception, and why?
- How should a model's performance be interpreted when the annotation target is
  one person's intent rather than an averaged crowd response?

---

**Seed Topic B: The 71-dimensional cinematic feature space — what's missing?**

The Cinematic Emotion Lab feature space covers: MFCCs (26), Chroma CQT (27),
Spectral features (6), RMS Energy (4), ZCR (2), Tempo (1), H/P Ratio (3).
Total: 71 dimensions.

The design prioritized acoustic domains known to carry emotional signal in music,
while remaining computable from standard MIR tools.

Questions:
- What acoustic features relevant to cinematic emotion are NOT covered by this space?
- Is there a case for including pitch contour or melodic shape features?
- How does this space compare to feature sets used in prior MER work?
- What would a principled dimensionality reduction strategy look like for a space
  like this, where the feature groups have different internal correlation structures?

---

**Seed Topic C: Evaluating emotion classification when the ground truth is unusual**

Standard MER evaluation uses accuracy, F1, and valence-arousal correlation against
crowd-averaged labels. When the ground truth is a single composer's stated intent,
standard metrics may not be the most informative frame.

Questions:
- What evaluation protocol would be most appropriate for a single-annotator
  compositional intent corpus?
- How should edge cases (deliberately ambiguous cues, low-confidence annotations)
  be handled in evaluation — included, excluded, or analyzed separately?
- Is there a meaningful way to compare models trained on compositional intent vs.
  listener perception labels on the same audio?

---

### Category 2 — AI vs. Composer Interpretation

**GitHub label:** `discussion:composer-gap`
**Audience:** Film composers, sound designers, affective computing researchers,
              AI interpretability researchers
**Purpose:** Conceptual and theoretical discussion of the Composer Gap

---

**Seed Topic A: What is the machine missing?**

The Composer Gap is the structured divergence between what an acoustic model predicts
and what a film composer says they constructed. Early annotation work has begun to
surface the shape of this gap.

One working hypothesis: the model performs well when composers follow conventional
acoustic-emotional mappings (fast tempo + minor mode = tension), and degrades
when composers deliberately violate those conventions as an expressive strategy.

Questions:
- From a compositional perspective: what are the most common ways you work against
  the "expected" acoustic signature of an emotion?
- Are there emotions in film scoring that you believe are structurally
  undetectable from acoustic features alone? If so, what additional signal
  would be required?
- The model hears amplitude, frequency, and time. What is it categorically unable
  to hear that matters to you as a composer?

---

**Seed Topic B: The problem of ambiguity as a compositional strategy**

One of the eight emotion categories in this research is `ambiguity`. Every cue
annotated as ambiguous was deliberately constructed that way - the ambiguity is
intentional, not annotation uncertainty.

This creates a direct challenge for a classification system: a cue designed to
resist categorical assignment is being asked to submit to one.

Questions:
- How should a classifier handle a category whose defining property is
  resistance to classification?
- Is `ambiguity` a legitimate emotion category in the same sense as `grief`
  or `triumph`, or is it a meta-category describing a compositional relationship
  to the other categories?
- What does the model's behavior on ambiguous cues reveal about what it is
  actually learning?

---

**Seed Topic C: Compositional intent vs. perception — a first-principles question**

If a composer writes a cue intending to produce grief, and an audience reports
feeling unsettled instead, which ground truth should a model learn to predict?
And what does it mean for a model to "understand" the music if it can predict
audience response but not compositional intent?

This is not primarily a technical question. It is a question about what
"emotion recognition in music" is actually trying to do.

Questions:
- What would it mean for a machine to understand a film score?
- Is computational emotion recognition fundamentally about audience modeling,
  compositional analysis, or something else?
- Does the distinction between intent and perception have implications beyond
  music — for other creative domains where there is a gap between what an
  artist intended and what an audience received?

---

### Category 3 — Computational Narrative Systems

**GitHub label:** `discussion:narrative-modeling`
**Audience:** Computational storytelling researchers, film theorists, NLP/sequence
              modeling researchers
**Purpose:** Discussion of narrative structure, temporal modeling, and the
              relationship between audio and dramatic arc

---

**Seed Topic A: Does music know where it is in the story?**

This research includes narrative position (opening, rising, climax, falling, resolution)
as a first-class annotation dimension. The hypothesis is that this position leaves
measurable acoustic traces — that a climax cue sounds statistically different from
a resolution cue even when both are annotated with the same primary emotion.

Questions:
- Is narrative position genuinely an acoustic phenomenon, or is it primarily
  a semantic/contextual one?
- If you remove the visual context, can a listener reliably identify where in
  a story arc a cue sits?
- How should narrative position be handled in a sequence model — as an input
  feature, a conditioning variable, or a target to predict?
- Are there acoustic features not in the current 71-dimensional space that would
  be specifically informative for narrative position detection?

---

**Seed Topic B: From static labels to tension trajectories**

One of the most significant transitions in this research program is from static
clip-level emotion classification to modeling harmonic tension as a continuous
trajectory over time. The output shifts from a categorical label to a temporal
curve.

Questions:
- What architectural choices make sense for modeling emotional trajectory in music?
- How should the training target for a tension trajectory model be defined?
  (Frame-level annotations? Interpolated from clip-level?) 
- What does "harmonic tension" mean computationally, and how well does it align
  with what a composer means when they use that term?
- Is tension a single scalar quantity or a multi-dimensional state?

---

**Seed Topic C: The grammar of film music emotion**

One speculative research question in this program asks whether there is a learnable
compositional grammar underlying the emotional architecture of film scoring — a set
of structural rules that predict how emotion categories sequence and transition.

Questions:
- Do film scores exhibit consistent macro-level emotional arc patterns across
  genres, composers, or eras?
- Is the emotional sequence of a film score predictable from narrative structure,
  or does it vary significantly across works?
- What would a "grammar" of cinematic emotion look like formally — as a transition
  matrix, a probabilistic grammar, a learned embedding?

---

### Category 4 — Emotional Architecture in Film Music

**GitHub label:** `discussion:film-music-theory`
**Audience:** Film composers, musicologists, film scholars, sound designers
**Purpose:** Domain-level theoretical discussion of emotional construction in film scoring

---

**Seed Topic A: The precision question — how deliberately do composers construct emotion?**

The foundational premise of this research is that film composers construct emotional
states with technical precision — that grief, tension, and triumph are not hoped-for
audience responses but engineered acoustic events.

This premise is testable. But it is also contestable.

Questions:
- When you score a scene, how precisely do you know what emotional state you are
  constructing? Is it always deliberate, or is some of it intuitive and only
  retrospectively legible?
- Are there emotional states in film scoring that feel impossible to construct
  "on purpose" — states that can only be arrived at obliquely?
- Does the answer to the computability question change depending on the composer
  or the compositional approach?

---

**Seed Topic B: What the audience hears vs. what the composer wrote**

Film music research traditionally studies what audiences perceive. This research
studies what composers intended. The gap between the two is real — composers
report constructing states that audiences do not reliably perceive, and audiences
report states that composers say they did not target.

Questions:
- Are there specific emotions in your practice where you have noticed a
  systematic gap between what you intended and what audiences report?
- Is the intent-perception gap consistent across audiences, or is it
  audience-dependent (cultural, musical training, age)?
- From a craft perspective, does the existence of the gap change how you think
  about what you are doing when you score?

---

**Seed Topic C: Can a machine ever hear what a film score is doing?**

This is the terminal question of the research program. Not "can a machine classify
film music emotion?" — the answer to that is demonstrably yes, at some level — but
"can a machine understand what a film score is doing?"

Understanding, in this context, might mean: predicting not just the emotional label
but the compositional decision that produced it, the narrative function it serves,
and the gap between acoustic signal and compositional intent.

Questions:
- What would constitute evidence that a machine "understands" film music at a level
  comparable to a trained human listener?
- Is there a form of musical knowledge that is permanently inaccessible to a system
  that operates only on acoustic features?
- If the Composer Gap is irreducible — if machine and composer will always diverge
  on some class of cues — what is the most theoretically significant interpretation
  of that irreducibility?

---

## Discussion Format Guidelines

**Opening a new discussion:**
Use a specific, arguable question as the title. Not "thoughts on emotion modeling?"
but "Is compositional intent a more stable annotation target than listener perception?"

**Response quality standard:**
Engage with specificity. References to prior work, compositional examples,
or specific technical counterarguments are valued over general agreement.

**Embargoed material:**
Research results, quantitative findings, and model performance data from this program
are not discussed in Issues or Discussions before publication. The research questions
are fair game. The answers are not yet public.

---

## Commit Messages for v0.2 Release

The following commit messages are approved for the v0.2 release sequence.
Use verbatim for traceability in the research record.

```
release(v0.2): annotation schema - formal ground truth specification public

Releases datasets/annotations/schema.json: complete field definitions,
ordinal scale specifications, edge case flag taxonomy, and annotation
protocol metadata for the Cinematic Emotion Lab corpus.
```

```
data(v0.2): public corpus subset - acoustic feature matrix released

Releases curated public subset of the Cinematic Emotion Lab corpus:
71-dimensional acoustic feature vectors with structural metadata.
Emotion labels withheld pending publication.
```

```
experiment(NB-EDA-001): feature distribution analysis - public subset

Releases NB-EDA-001: exploratory analysis of the acoustic feature space
across the public corpus subset. Variance profiles, correlation structure,
feature distributions by harmonic mode and narrative position. No emotion
labels or classification results.
```

```
docs(methodology): methodology-preview updated to v2.0

Expands public methodology documentation: complete phase descriptions,
annotation methodology depth, methodological commitments. Embargoed
sections clearly marked. Links updated for v0.2 release artifacts.
```

```
docs(research-log): 003-public-research-subset - v0.2 release record

Research log documenting v0.2 curation decisions, corpus statistics,
qualitative annotation observations, and open questions carried forward
to v0.25. Public-safe. No quantitative findings disclosed.
```

```
release(v0.2): release notes and GitHub discussions architecture

Adds release_notes/v0.2-public-research-subset.md and
docs/GITHUB_DISCUSSIONS.md. Release notes: complete artifact inventory,
disclosure status, next release preview. Discussions: 4 categories,
12 seed topics for community engagement.
```

---

*Cinematic Emotion Lab - GitHub Discussions Architecture v1.0 - August 2026*
