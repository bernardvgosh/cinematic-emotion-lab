# Research Log 002 · Emotion Mapping Framework
## Cinematic Emotion Lab

**Date:** 2026-06-06
**Status:** In Development

---

## Framework Design

The emotion mapping framework moves beyond flat emotion labels toward a multi-axis annotation schema:

- **Primary emotion** - 8 categories tuned to cinematic narrative function
- **Emotional intensity** - 1–5 scale, calibrated to dramatic weight not loudness
- **Narrative position** - where in the story arc does the cue sit?
- **Harmonic mode** - the tonal foundation of the cue
- **Orchestration density** - sparse to dense, as a texture proxy

## Design Decisions

**Why composer intent, not listener perception?**
Listener perception introduces response variability that obscures the signal we are trying to study. Compositional intent is stable, documented (through the annotation process), and directly mappable to acoustic decisions. The gap between intent and perception is itself a separate research question.

**Why 8 emotion categories?**
The 8 categories (`tension · triumph · grief · suspense · joy · dread · longing · ambiguity`) are chosen for their distinctness in cinematic practice and their expected separability in acoustic feature space. Overlap cases (tension/suspense, grief/longing) are treated as edge cases to be documented, not collapsed.

**Why include ambiguity as a category?**
Because composers deliberately score ambiguity. A cue that refuses to commit to a single emotional reading is not an annotation failure - it is a compositional strategy. The model's behavior on ambiguous cues is one of the most theoretically interesting outputs of the study.

## Open Questions

- Does orchestration density require a finer scale for high-density symphonic textures?
- Should rubato passages be flagged as requiring manual BPM annotation?
- How to handle multi-section cues where emotional category shifts mid-clip?
