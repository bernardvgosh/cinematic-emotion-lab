# Research Exposure Strategy
## Cinematic Emotion Lab · Staged Public Disclosure Plan

> This document is the internal strategic framework governing what is released, when, and why. It is committed publicly as a signal of methodological intentionality - the act of planning disclosure is itself a research practice.

---

## Core Strategic Principle

**Release architecture, not findings. Release methodology, not conclusions. Release questions, not answers.**

The goal is to establish intellectual presence, signal depth, and generate professional curiosity - without surrendering the competitive advantage of unpublished results. Every public release should make the unreleased material feel more valuable, not less necessary.

---

## Staged Disclosure Framework

### Stage 1 · Presence (Current)
*Establish that this research exists, is serious, and has institutional-grade structure.*

**Release now:**
- Repository structure and naming conventions
- README with research questions and methodology overview
- Visual identity system (banner, color palette, pipeline diagram)
- EXP-001 feature extraction notebook (methodology visible, findings not yet meaningful without dataset)
- CONTRIBUTING and LICENSE
- Research philosophy statement
- Architecture pipeline diagram (shows sophistication without revealing model internals)

**Effect:** Signals rigor, signals scale, signals that work is underway.

---

### Stage 2 · Credibility (Q3 2026)
*Demonstrate that the research is producing real data and real results.*

**Release:**
- Anonymized sample feature matrix (20–30 clips, labels redacted)
- Annotation schema with field definitions
- EDA notebook (NB-EDA-001) showing feature distributions - no emotion-labeled conclusions
- Waveform + spectrogram visualizations for selected clips
- Week 01–04 research logs (factual, no findings disclosed)
- Preliminary tempo–arousal scatter (described as "pattern observed, validation ongoing")

**Hold back:**
- Full dataset
- Annotation labels
- Any classification accuracy numbers
- Model weights

**Effect:** Signals that data collection is real and substantial. Creates desire to see the labeled version.

---

### Stage 3 · Results Preview (Q4 2026)
*Release enough to demonstrate the research works, without the paper.*

**Release:**
- EXP-002 notebook skeleton (methodology visible, key accuracy numbers redacted or described qualitatively)
- UMAP feature space visualization (colored by cluster, not by label)
- Partial findings language: "Initial classification experiments demonstrate statistically significant separability across emotion categories in the acoustic feature space..."
- Harmonic tension trajectory visualization (one or two anonymized clips)
- EXP-003 architecture diagram

**Hold back:**
- Per-class accuracy breakdown
- Confusion matrices
- Trained model weights
- Composer annotation data

**Effect:** Makes it impossible to doubt that the research is working. Creates urgency around publication.

---

### Stage 4 · Pre-Publication (2027)
*Full release timed to accompany paper submission or conference presentation.*

**Release:**
- Complete dataset (audio features + annotations)
- All trained models and checkpoints
- Full evaluation suite
- Composer vs. AI divergence analysis
- Paper preprint (arXiv or equivalent)
- Interactive visualization dashboard

---

## Files to Upload First

Priority order for maximum immediate impact:

1. `README.md` - primary impression surface
2. `visualizations/assets/CEL_banner_github.png` - visual credibility
3. `visualizations/assets/CEL_pipeline_diagram.png` - technical sophistication signal
4. `docs/METHODOLOGY.md` - depth signal
5. `docs/RESEARCH_QUESTIONS.md` - intellectual curiosity signal
6. `notebooks/experiments/NB-EXP-001_*.ipynb` - technical proof of work
7. `docs/ARCHITECTURE.md` - systems thinking signal
8. `docs/COMPOSER_VS_AI.md` - originality and intrigue signal
9. `RESEARCH_STRATEGY.md` (this file) - meta-credibility signal
10. `research-notes/weekly-logs/WEEK-01_*.md` - activity signal

---

## Files to Delay

Do not upload until Stage 3 or 4:

- Any file containing classification accuracy numbers
- `datasets/annotations/` - holds composer labels
- `models/checkpoints/` - trained weights
- `models/results/` with populated metrics
- Any notebook with filled "Results & Observations" sections
- Research logs mentioning specific finding magnitudes
- The Composer vs. AI quantitative comparison data

---

## Visual Assets Strategy

### Immediate (released)
- GitHub README banner
- Color palette system
- Research pipeline diagram
- LinkedIn/GitHub thumbnail

### Q3 2026
- Waveform + annotation overlay (selected clips, no labels visible)
- Mel spectrogram gallery (visually striking, no interpretive text)
- MFCC heatmap comparison grid

### Q4 2026
- UMAP feature space projection (unlabeled clusters shown)
- Harmonic tension arc visualization (anonymized clips)
- Tempo–arousal scatter (data points shown, regression line withheld)

### Pre-publication
- Full labeled UMAP
- Composer vs. model divergence heatmap
- Per-class spectrogram gallery
- Confusion matrix suite

---

## Suggested Diagrams to Create

| Diagram | Purpose | When |
|---------|---------|------|
| Feature extraction signal chain | Shows technical depth | Now |
| Emotion category taxonomy tree | Shows theoretical rigor | Now |
| Annotation schema flowchart | Shows human pipeline design | Q3 |
| Temporal emotion arc example | Shows research novelty | Q3 |
| Model architecture comparison | Shows ML sophistication | Q4 |
| Composer vs. model divergence map | Shows unique contribution | Pre-pub |
| Narrative position × emotion matrix | Shows interdisciplinary depth | Q4 |
| Acoustic feature correlation heatmap | Shows statistical rigor | Q3 |

---

## Suggested Charts to Create

| Chart | Type | When |
|-------|------|------|
| Feature distribution by emotion class | Violin plot | Q3 (no labels) |
| Spectral centroid over time | Line plot | Now (single clip) |
| Chroma radar per clip | Polar chart | Now |
| RMS energy envelope | Area chart | Now |
| Tempo distribution across dataset | Histogram | Q3 |
| MFCC coefficient means | Grouped bar | Now |
| Harmonic/percussive ratio balance | Stacked bar | Now |
| UMAP 2D projection | Scatter | Q4 (unlabeled) |

---

## Suggested Teaser Notebooks

These notebooks are safe to publish - they show methodology and code quality without exposing findings:

| Notebook | Content | Status |
|----------|---------|--------|
| `NB-EXP-001` | Feature extraction pipeline | Released |
| `NB-EDA-001_feature-distributions` | Statistical overview of feature space | Create for Q3 |
| `NB-VIZ-001_spectrogram-gallery` | Visual spectrogram comparison | Create for Q3 |
| `NB-VIZ-002_chroma-radar-profiles` | Interactive chroma profiles | Create for Q3 |
| `NB-EDA-002_tempo-arousal-scatter` | Tempo × annotation scatter (labels withheld) | Create for Q4 |
| `NB-EXP-002_skeleton` | Classification notebook, key cells redacted | Create for Q4 |

---

## Weekly GitHub Update Strategy

Consistency of activity is a credibility signal. The following cadence is recommended:

**Every week, commit at least one of:**
- A new or updated research log (`WEEK-XX`)
- A new visualization or plot
- A notebook update (even if minor)
- A docs update or new research note
- A new feature or script

**Monthly:**
- Update README status bars
- Add an entry to UPCOMING_RELEASES
- Post a research insight to the research-notes/experiments/ folder

**Quarterly:**
- Stage release (per the staged disclosure framework above)
- Update research questions with any refinements
- Archive completed research logs

---

## Public-Safe Methodology Language

Use these formulations to communicate progress without disclosing findings:

> "Initial experiments suggest that acoustic features demonstrate structured variation across annotated emotion categories. Validation is ongoing."

> "The feature extraction pipeline has been validated against a held-out test set. Classification results are withheld pending full annotation completion."

> "Preliminary harmonic analysis reveals patterns consistent with our working hypothesis. Quantitative results are embargoed pending publication."

> "The composer annotation process has surfaced interpretive tensions that are now being formalized as a secondary research question. Details to follow."

> "Early UMAP projections of the feature space suggest meaningful cluster structure. Label-colored versions are withheld pending peer review."

> "Tempo analysis across the current dataset reveals a distribution that does not conform to simple linear arousal models. A more nuanced model is under development."

> "The Composer Gap - the divergence between annotated intent and acoustic prediction - is measurable and structured. The characterization of this gap is the current central research focus."

---

*Cinematic Emotion Lab · Staged disclosure as research practice.*
