# Upcoming Releases
## Cinematic Emotion Lab · Public Disclosure Schedule

> Releases are staged by research readiness, not by calendar pressure. Each release represents a coherent, self-contained contribution — not a partial dump of in-progress work.

---

## Release History

### v0.1 · Foundation ✓ Released 2026-06-06

**Scope:** Repository structure, visual identity, and foundational extraction pipeline.

**Includes:**
- Complete repository scaffold with naming conventions and documentation standards
- Visual identity system: banner, color palette, pipeline diagram, LinkedIn card
- `NB-EXP-001` — full feature extraction notebook (librosa pipeline, 71-feature matrix, cinematic visualizations)
- `METHODOLOGY.md`, `ARCHITECTURE.md`, `RESEARCH_QUESTIONS.md`
- `RESEARCH_STRATEGY.md` — staged disclosure framework
- `COMPOSER_VS_AI.md`, `RESEARCH_PHILOSOPHY.md`

**Research signal:** The pipeline is built. The methodology is serious. The research has begun.

---

## Planned Releases

### v0.2 · Dataset Preview
**Target:** Q3 2026
**Status:** Pending annotation completion

**Will include:**
- Anonymized sample feature matrix (30–50 clips)
- Annotation schema with field definitions and rationale
- `NB-EDA-001_feature-distributions.ipynb` — statistical overview of feature space
- `NB-VIZ-001_spectrogram-gallery.ipynb` — comparative spectrogram visualization
- Week 01–06 research logs
- Updated README status indicators

**Will not include:**
- Emotion labels on the sample matrix
- Full dataset
- Any classification accuracy numbers

**Research signal:** Real data exists. The scale of the dataset is visible. The annotation process is transparent.

---

### v0.3 · Baseline Results
**Target:** Q3–Q4 2026
**Status:** Pending EXP-002 completion

**Will include:**
- `NB-EXP-002_emotion-classification-baseline.ipynb` (partial — key accuracy cells redacted)
- Qualitative results description: "Initial classification experiments demonstrate statistically significant separability across emotion categories in the acoustic feature space"
- Feature importance analysis (which features matter most — without revealing the full results)
- `NB-VIZ-002_chroma-radar-profiles.ipynb` — interactive chroma visualization
- UMAP feature space projection (cluster structure visible, labels withheld)

**Research signal:** The research is working. Classification is possible. The interesting questions are now about *where* it works and *where* it doesn't.

---

### v0.4 · Visualization Suite
**Target:** Q4 2026
**Status:** In design

**Will include:**
- Full interactive visualization dashboard (plotly-based)
- Harmonic tension trajectory visualization for selected anonymized clips
- Tempo × emotional intensity scatter (data visible, regression withheld)
- MFCC coefficient comparison gallery across emotion categories
- Updated `NB-EXP-003` architecture design notebook

**Research signal:** The research has visual language. The feature space has structure. The results are forming.

---

### v0.5 · Sequence Modeling
**Target:** Q4 2026 – Q1 2027
**Status:** Architecture design phase

**Will include:**
- `NB-EXP-003_harmonic-tension-sequence-model.ipynb`
- LSTM/Transformer architecture documentation
- Temporal emotion arc visualization for selected clips
- Model configuration files (no weights)

**Research signal:** The research has moved beyond static classification into temporal modeling. The most interesting results are being computed.

---

### v1.0 · Full Release
**Target:** 2027 (timed to publication)
**Status:** Future

**Will include:**
- Complete annotated dataset (audio features + composer labels)
- All trained model weights and checkpoints
- Full evaluation suite with per-class results
- Composer vs. AI divergence analysis (EXP-004)
- Paper preprint (arXiv)
- Interactive research dashboard
- Full research log archive

**Research signal:** The work is done. The contribution is public.

---

## Release Principles

**Quality over calendar** — No release ships before it is ready to represent the research accurately.

**Methodology before results** — Architecture and methodology documents precede data and results in every release. Readers should understand *how* before they see *what*.

**Teasers are not leaks** — Every partial disclosure is deliberate. Nothing is published accidentally. The staged nature of the disclosure is itself a methodological choice.

**Results travel with context** — No number is released without the methodological context required to interpret it correctly.

---

*Release schedule subject to revision based on publication timeline and research progress.*
*Follow this repository for updates.*
