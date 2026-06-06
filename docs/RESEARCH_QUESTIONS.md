# Research Questions
## Cinematic Emotion Lab · Theoretical Framework

> *Good research questions are not answered - they are dissolved. You stop asking them not because you found the answer, but because you found a better question.*

---

## Primary Research Questions

These questions define the core empirical program of the lab. Each maps to one or more planned experiments.

---

### RQ-01 · The Acoustic Encoding Hypothesis

**Question:** Do low-level acoustic features contain sufficient information to reliably classify the intended emotional category of cinematic music clips?

**Why it matters:** This is the foundational question. If acoustic features carry no reliable emotional signal, the entire computational approach fails. If they do - with what reliability, and for which emotional categories?

**Experimental mapping:** EXP-001 (feature extraction) → EXP-002 (classification)

**Theoretical background:** Decades of music psychology research suggest consistent acoustic correlates of broad emotional dimensions (Valence-Arousal space). This research asks whether those correlates hold at the specific resolution of cinematic emotion categories - a finer and more contextually situated taxonomy than standard music psychology models address.

**Status:** Feature extraction complete. Classification results withheld pending annotation completion.

---

### RQ-02 · The Tension Trajectory Problem

**Question:** Is harmonic tension in film music a learnable, predictable quantity - or is it irreducibly compositional?

**Why it matters:** Harmonic tension is arguably the most important structural mechanism in film scoring. A composer's ability to build, sustain, and release tension is the technical foundation of emotional manipulation in cinema. If it is learnable from acoustic features, we gain a powerful analytical tool. If it is not, we learn something profound about the limits of computational music analysis.

**Experimental mapping:** EXP-003 (sequence modeling)

**Key methodological challenge:** Tension is inherently temporal and relational - it depends on what came before and what is anticipated. Static clip-level features may be insufficient; sequential models over frame-level features are required. The research tests whether temporal context encoding changes the classification picture.

**Status:** Architecture design phase. Results embargoed.

---

### RQ-03 · The Composer Gap

**Question:** Where is the systematic boundary between what a machine can perceive from audio and what a film composer says they constructed?

**Why it matters:** This is the most intellectually consequential question in the research program. The gap between computational perception and compositional intent is not a failure condition - it is information. Characterizing this gap reveals what film music does that cannot yet be formalized.

**Experimental mapping:** EXP-004 (Composer vs. AI Study)

**Hypothesis:** The model will be most accurate for emotion categories with strong acoustic signatures (high-energy triumph, low-energy grief) and least accurate for categories that depend on harmonic context, negative space, and structural expectation (suspense, longing, ambiguity).

**Status:** Annotation framework in development. Quantitative results embargoed pending peer review.

---

## Secondary Research Questions

These questions emerge from the primary program and are being investigated in parallel.

---

### RQ-04 · Composer Idiolect vs. Universal Signature

**Question:** Do different composers encode the same emotional category through distinct acoustic strategies, or are there universal acoustic-emotional signatures that transcend individual style?

**Theoretical framing:** A Zimmer tension cue and a Herrmann tension cue may have radically different acoustic profiles while achieving the same emotional effect. If so, emotion classification must either operate above the stylistic level or be trained per-composer. If universal signatures exist, a single model may generalize.

**Approach:** Inter-composer feature distribution analysis within annotated emotion categories.

---

### RQ-05 · Narrative Position Inference

**Question:** Can the narrative position of a cue - opening, rising, climax, falling, resolution - be inferred from acoustic features alone?

**Theoretical framing:** Film music is structurally embedded in narrative time. A rising-tension cue and a climax cue may both be annotated as "tension," but their temporal position gives them entirely different dramatic functions. Whether acoustic features encode narrative position is an open question.

---

### RQ-06 · Spectral Density as Suspense Proxy

**Question:** Is spectral density a reliable, generalizable predictor of suspense in film music - and does this generalize across compositional styles and historical periods?

**Theoretical framing:** High spectral density (dense harmonic content, complex timbral layering) is a compositional hallmark of suspense scoring. This research tests whether this intuition has quantitative support across a diverse dataset.

---

### RQ-07 · Tempo as Arousal Proxy

**Question:** Does tempo function as a simple linear arousal scale in cinematic music, or are the dynamics more complex - with tempo interacting with harmonic mode, dynamic level, and orchestration density?

**Theoretical framing:** Basic arousal-valence models predict that higher tempo correlates with higher arousal. Film scoring practice suggests this relationship is highly nonlinear and heavily modulated by harmonic context. A slow tempo in a major key produces very different emotional output than a slow tempo in a minor key.

---

## Speculative Research Questions

These questions define the long-term theoretical horizon of the lab. They are not currently addressable with the existing methodology but guide the direction of the research program.

---

### RQ-S01 · Cross-Domain Emotional Transfer

**Question:** Can a model trained exclusively on cinematic film scores learn an emotional encoding that transfers to non-cinematic music - concert music, popular music, ambient music?

**Why it matters:** If emotional encoding in cinematic music is unique to the form (shaped by visual context, narrative convention, and genre expectation), transfer should fail. If it reveals universal acoustic-emotional principles, transfer may succeed. Either outcome is theoretically significant.

---

### RQ-S02 · Spatial Geometry of Musical Emotion

**Question:** Does musical emotional space have geometric properties analogous to physical architectural space - and can theories of spatial proportion, tension, and release from architecture inform how we model musical emotional trajectory?

**Theoretical framing:** This research thread draws from the researcher's background in architectural design. The hypothesis is that spatial concepts - compression, expansion, threshold, threshold crossing, proportion, negative space - map meaningfully onto the structure of cinematic emotional arcs. This is speculative but testable through dimensional analysis of feature space topology.

---

### RQ-S03 · The Computable Grammar of Cinematic Emotion

**Question:** Is there a finite, learnable grammar of cinematic emotional construction - a set of compositional rules with sufficient regularity to be formally specified?

**Theoretical framing:** Linguistics has syntax. Music theory has harmony. Does cinematic emotion have a grammar? This question sits at the intersection of computational creativity, cognitive science, and film theory. The answer - if it exists - would represent a fundamental contribution to understanding how art communicates.

---

## Question Genealogy

```
RQ-01 (Acoustic Encoding)
  └─▶ If yes: RQ-02, RQ-04, RQ-06, RQ-07
  └─▶ If partial: RQ-03 (The Composer Gap)
        └─▶ If gap is structured: RQ-S03 (Grammar)
  └─▶ RQ-05 (Narrative Position)
        └─▶ RQ-S01 (Cross-Domain Transfer)
              └─▶ RQ-S02 (Spatial Geometry)
```

The research questions form a dependency tree. The primary questions must be answered (at least partially) before the secondary and speculative questions become tractable. This structure guides the experimental roadmap.

---

*Research questions are living documents. They evolve as the research progresses.*
*Last updated: 2026-06-06*
