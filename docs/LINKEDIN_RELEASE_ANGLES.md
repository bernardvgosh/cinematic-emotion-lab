# LinkedIn Release Angles
## Cinematic Emotion Lab - Per-Release Announcement Framework

> This document contains the strategic framing angle, key message, and draft
> post language for each planned public milestone. Each release has one primary
> angle - a distinct conceptual entry point that does not repeat the previous post.
> Rotate audiences: AI/ML, film industry, and academic readers should each feel
> directly addressed at least once across the sequence.

---

## Release Angle Architecture

Each post is built around one question the audience will ask after reading:
**"What does this mean for my field?"**

The angle determines which field answers that question.

| Release | Primary Angle | Target Audience |
|---------|--------------|-----------------|
| v0.1 | The research problem is real | AI/ML + Film |
| v0.15 | The feature space is alive | AI/ML |
| v0.2 | The ground truth is principled | Academic/Research |
| v0.25 | The annotation methodology is novel | Academic/Research |
| v0.3 | The machine has an opinion | AI/ML + Film |
| v0.35 | Emotion moves through time | Film + AI/ML |
| v0.4 | The gap is the finding | Film + Academic |
| v0.5 | You can experience the research | Broad/General |
| v1.0 | The work is done | All |

---

## v0.1 - Foundation Layer

**Angle: The research problem is real**
The goal here is not to announce a model. It is to announce a question serious
enough to justify months of research. Lead with the problem, not the method.

---

**Post - Version A (Cinematic)**

Film music is the most emotionally precise communication system human beings have
built.

A composer writing for picture is not guessing. They are constructing a specific
emotional state - grief, not sadness; dread, not unease - at a specific timecode,
against a specific visual event. The precision is technical. The tools are harmonic,
rhythmic, and timbral. The results are measurable.

So: can that precision be computationally characterized?

That's the question I've been building toward. Today I'm making the research public.

Cinematic Emotion Lab is an active research program at the intersection of music
information retrieval, affective computing, and computational musicology. The system
extracts a 71-dimensional acoustic feature vector from cinematic audio and maps it
to composer-annotated emotional ground truth - not listener perception, the
composer's stated intent.

v0.1 is the foundation layer. The methodology is documented. The pipeline is live.
The findings are embargoed.

[Repository link]

---

**Post - Version B (Technical)**

I've been building a computational system for cinematic emotion recognition.

Today I'm releasing the research infrastructure publicly.

The technical core: a 71-dimensional acoustic feature space built on MFCCs (26),
Chroma CQT (27), Spectral features (6), RMS Energy (4), ZCR (2), Tempo (1),
and Harmonic/Percussive Ratio (3). Feature extraction is fully implemented in
librosa on a Python 3.12 stack.

The methodological distinction that makes this interesting: ground truth is
established from **compositional intent**, not listener perception. The annotation
target is what the composer said they were building - which turns out to be a
surprisingly different thing from what audiences report feeling.

This creates a novel research object: the Composer Gap - the structured divergence
between machine predictions and composer-annotated intent. EXP-004 is the study
I most want to publish.

v0.1 is methodology and infrastructure. Classification results are embargoed.

[Repository link]

---

## v0.15 - Visualization Intelligence

**Angle: The feature space is alive**
First visuals from the research. The goal is to show that there is structure
in the data - without revealing what the structure means. Let the images
create questions.

---

**Post Draft**

The Cinematic Emotion Lab feature space is starting to show its topology.

v0.15 releases the first generation of analytical visualizations from the research
pipeline: spectrogram galleries, MFCC heatmap comparisons, and chroma radar profiles
across annotated emotion categories.

These aren't illustrative figures. They're the outputs of a functioning acoustic
analysis system applied to a professionally annotated corpus of cinematic cues.
The patterns you're seeing are empirical.

What I can say: the feature space has structure. Annotated emotion categories do
not sit in a uniform cloud.

What I'm withholding: quantitative separability. That's for the paper.

Two new notebooks released: NB-VIZ-001 and NB-VIZ-002.
First four weeks of research logs now public.

[Repository link]

---

## v0.2 - Computational Annotation Preview

**Angle: The ground truth is principled**
Address the academic/research audience directly. The annotation methodology is
the most novel part of the work. Make the case for why it matters.

---

**Post Draft**

Most music emotion recognition research annotates from the listener's side -
how does this audio make you feel?

This research annotates from the composer's side - what were you building?

The distinction matters more than it might seem. A composer writing grief into
a film score is not hoping the audience feels sad. They are constructing a specific
emotional state with specific technical tools - harmonic mode, dynamic shape,
orchestral texture, rhythmic density. That construction is intentional, repeatable,
and documentable.

Today I'm releasing the annotation framework that encodes that intent as machine-
readable ground truth.

v0.2 includes the annotation schema, protocol documentation, a curated public
corpus subset, and NB-EDA-001 - feature distribution analysis across the public
subset. Full composer labels are withheld pending publication.

[Repository link]

---

## v0.25 - Annotation Intelligence Framework

**Angle: The annotation methodology is novel**
Go deeper on the academic contribution. This post establishes the theoretical
distinctiveness of the ground truth design.

---

**Post Draft**

The annotation target determines what the model learns.

In most affective computing research, the annotation target is emotional response -
what listeners feel when they hear a piece of music. In music emotion recognition
specifically, this typically means averaged crowd labels, Valence-Arousal ratings,
or categorical tags derived from listener surveys.

This research uses a different target: **compositional intent**.

The difference is not subtle. When a composer writes a cue designed to create
dread through sustained harmonic ambiguity and withheld resolution - and listeners
report feeling "unsettled" or "tense" - the crowd label captures a real response.
But the compositional annotation captures what was engineered. Those are different
things. A model trained on one will not behave the same as a model trained on the
other.

v0.25 releases the complete annotation intelligence framework: schema, decision
trees, edge case taxonomy, and sample entries with composer reasoning.

[Repository link]

---

## v0.3 - Baseline Intelligence Results

**Angle: The machine has an opinion**
First results post. Write with confidence but maintain embargo discipline.
Do not give numbers. Characterize the shape of the finding without quantifying it.

---

**Post Draft**

The machine has a working hypothesis.

v0.3 releases the first classification results from the Cinematic Emotion Lab
research pipeline. NB-EXP-002 is now public: architecture, training protocol,
and qualitative characterization of findings.

What the baseline experiment establishes: cinematic emotional categories exhibit
statistically significant separability within this acoustic feature space.
The system can distinguish tension from triumph, grief from joy, with
better-than-chance consistency. Feature importance analysis reveals which acoustic
domains carry the most signal - which is, in some ways, the most interesting
result at this stage.

Quantitative accuracy figures are embargoed pending publication.

Also released: NB-VIZ-003 - a UMAP projection of the emotion corpus. Cluster
structure is visible. Categorical labels are withheld.

[Repository link]

---

## v0.35 - Harmonic Tension Intelligence

**Angle: Emotion moves through time**
This is the post that speaks most directly to film composers and cinematographers.
Lead with the creative stakes. Explain why sequence modeling matters for this domain.

---

**Post Draft**

A film score cue is not a static emotional statement. It is a trajectory.

Grief in a 90-second cue is not the same note held for 90 seconds. It builds,
intensifies, breaks, resolves - or fails to resolve. The emotional architecture
is temporal. The tools are sequential: harmonic motion, dynamic arc, rhythmic
density over time.

Standard emotion classification treats each clip as a point in feature space.
This research treats each clip as a sequence.

v0.35 releases the temporal modeling layer: NB-EXP-003, the harmonic tension
sequence model. Architecture and training protocol are public. The first
tension trajectory visualizations - emotional arc curves for anonymized cinematic
cues - are now available.

Early trajectories suggest that harmonic motion in film music follows learnable
arc patterns that align to narrative structure. Rising, climax, falling, resolution -
the model is beginning to hear what editors cut to.

[Repository link]

---

## v0.4 - Interpretability and Divergence

**Angle: The gap is the finding**
This is the most intellectually important post in the sequence. The Composer Gap
is the central theoretical contribution. Lead with the inversion: the divergence
is not error, it is data.

---

**Post Draft**

The place where the model fails is more interesting than where it succeeds.

v0.4 releases the Composer Gap study design - EXP-004, the interpretive core of
the Cinematic Emotion Lab research.

The Composer Gap is the structured, measurable divergence between what an acoustic
model predicts and what a film composer says they constructed. It is not a failure
condition. It is a research object.

Early analysis has produced a taxonomy of four divergence failure modes - named,
characterized, and documentable. The most consistent pattern: the model performs
well when tempo and harmonic mode co-occur in expected directions, and degrades
systematically when a composer deliberately inverts that expectation. Which is
precisely when the music is most interesting.

The implication - and this is what I want to put to peer review - is that
computational emotion recognition may be optimizing against a target that
does not capture what composers actually build.

NB-EXP-004 architecture is public. Divergence metrics are embargoed.

[Repository link]

---

## v0.5 - Interactive Research Platform

**Angle: You can experience the research**
Broaden the audience. This post invites people who haven't followed the technical
releases to engage with the work through the interface.

---

**Post Draft**

The Cinematic Emotion Lab is now explorable.

v0.5 deploys the research visualization platform: an interactive interface for
navigating the cinematic emotion feature space, playing harmonic tension arcs,
and browsing the public annotation corpus.

This is what the last year of research looks like as an experience rather than
a paper.

You can see how annotated emotion categories cluster in the feature space.
You can play a tension arc and watch emotional intensity move through a
cinematic cue in real time. You can browse the public corpus subset and
understand what a 71-dimensional acoustic representation of film music
actually captures.

Full dataset and quantitative results release with v1.0, timed to publication.

[Repository link]

---

## v1.0 - Full Research Disclosure

**Angle: The work is done**
This post speaks to all three audiences simultaneously. It is the publication
announcement, the dataset release, and the research retrospective in one.
Write with finality.

---

**Post Draft**

The Cinematic Emotion Lab research program is complete.

v1.0 releases the full research output: annotated dataset, trained model weights,
quantitative results from all four experiments, and the paper.

The findings are precise, the methodology is defensible, and the Composer Gap
is real - measurable, structured, and larger than the baseline models can account for.

The central finding - that computational emotion recognition performs well when
composers follow conventional acoustic emotion signals, and fails systematically
when they deliberately subvert those conventions - has implications beyond film music.
It speaks to what affective AI systems are actually learning versus what we think
they're learning.

The full annotated corpus, complete with composer-intent labels across eight
emotion categories, is now publicly available for the research community.

Details in the repository and paper.

[Paper link] [Repository link]

---

## Posting Strategy

**Timing:**
- Release posts go live same day as GitHub release, or within 24 hours.
- Do not pre-announce with a teaser post. The release is the announcement.
- Engage with comments for 48 hours post-release.

**Format:**
- No images in the post body unless a visualization is being released.
- When releasing visualizations, attach one figure maximum.
- Link to the specific notebook or document being released, not just the repo root.

**Cross-posting:**
- LinkedIn: primary platform for all releases.
- GitHub: release tag with the GitHub release title from docs/RELEASE_NOTES.md.
- No Twitter/X requirement until v0.3 results release.

**Hashtags (use sparingly, 3-4 maximum):**
`#MachineLearning` `#ComputationalMusicology` `#FilmMusic` `#MusicInformationRetrieval`
`#AIResearch` `#AffectiveComputing`

---

*Cinematic Emotion Lab - LinkedIn Release Angles v1.0 - June 2026*
