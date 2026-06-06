# Methodology
## Cinematic Emotion Lab · Computational Framework

> *This document describes the methodological architecture of the research program. Specific results, trained model weights, and annotated datasets are withheld pending publication.*

---

## Foundational Premise

The methodology of this lab rests on a single contestable premise: **emotional states in cinematic music are not subjective responses - they are structured acoustic events.** If a film composer can reliably produce grief, tension, or triumph through deliberate musical construction, then those emotional categories must leave measurable traces in the audio signal.

This premise is falsifiable. Testing its limits - and characterizing where it breaks down - is as important as confirming it where it holds.

---

## Research Design Overview

The research is structured as a multi-stage experimental program, progressing from feature extraction through annotation-aligned supervised learning to interpretive analysis.

```
Phase 1: Signal Analysis
  ↓ acoustic feature extraction across multiple domains
Phase 2: Semantic Annotation
  ↓ composer-led emotional labeling with structured schema
Phase 3: Supervised Learning
  ↓ classification and regression models on annotated feature matrix
Phase 4: Interpretive Analysis
  ↓ composer vs. model divergence characterization
Phase 5: Theoretical Synthesis
  ↓ computational theory of cinematic emotional encoding
```

Each phase is independently documented. Results from each phase are held until the full pipeline reaches sufficient completeness for coherent publication.

---

## Phase 1 · Signal Analysis

### Audio Acquisition

Source audio is acquired under research licensing terms. All clips are verified for:
- Minimum 10 seconds duration
- Minimal non-musical content (silence, SFX, dialogue)
- Representativeness of a single dominant emotional state
- Attribution to a named composer with known stylistic context

### Preprocessing Pipeline

```python
# Standardization parameters
SAMPLE_RATE = 22050   # Hz  - standard MIR convention
N_FFT       = 2048    # FFT window size
HOP_LENGTH  = 512     # Frame hop - ~23ms at 22050Hz
DURATION    = None    # Full clip loaded
MONO        = True    # All clips converted to mono
```

Processing steps:
1. Load audio at 22050Hz, mono
2. Trim leading/trailing silence (top\_db=30)
3. Normalize amplitude to [-1, 1] peak range
4. Validate minimum duration threshold

### Feature Extraction Domains

**Timbral (MFCCs)**
Mel-frequency cepstral coefficients capture the timbral character of the audio - the spectral envelope that distinguishes string textures from brass, woodwinds from choir. 13 coefficients extracted per frame; summarized as mean and standard deviation across the clip.

**Harmonic (Chroma CQT)**
Constant-Q chroma features map energy onto the 12 pitch classes of Western tonality. Used to characterize key, mode, harmonic density, and tonal center stability. The dominant pitch class and overall chroma entropy are derived quantities.

**Spectral (Centroid · Bandwidth · Rolloff)**
Spectral centroid measures the "brightness" of the spectrum - the frequency-weighted center of mass. Higher centroid values correlate with perceived sharpness and tension. Bandwidth measures spectral spread; rolloff captures the frequency below which 85% of energy is concentrated.

**Dynamic (RMS Energy)**
Root mean square energy tracks loudness and dynamic range over time. The ratio of maximum to mean RMS encodes dramatic dynamic shape. Peak-normalized dynamic range in dB is computed as a single-value descriptor.

**Textural (Zero Crossing Rate)**
Zero crossing rate captures the rate at which the signal crosses zero amplitude - a proxy for noisiness, transient density, and percussive content. Higher ZCR correlates with timbral complexity and rhythmic activity.

**Rhythmic (Tempo · Beat Frames)**
Tempo estimated via librosa's beat tracker. Beat frame positions stored for temporal alignment with annotation events.

**Structural (Harmonic/Percussive Separation)**
HPSS (Harmonic Percussive Source Separation) decomposes the signal into harmonically stable components (strings, brass, choir) and percussive transients (percussion, plucked strings, staccato). The ratio of harmonic to total energy is a single-value orchestral texture descriptor.

### Feature Matrix Specification

| Group | Features | Dimensions |
|-------|----------|------------|
| Metadata | filename, duration | 2 |
| Tempo | bpm | 1 |
| Spectral | centroid, bandwidth, rolloff × mean+std | 6 |
| Chroma | 12 pitch classes × mean+std + dominant + overall | 27 |
| Energy | rms mean, std, max, dynamic range dB | 4 |
| ZCR | mean, std | 2 |
| MFCC | 13 coefficients × mean+std | 26 |
| H/P | harmonic ratio, percussive ratio, H/P balance | 3 |
| **Total** | | **71** |

---

## Phase 2 · Semantic Annotation

### Annotation Schema

Composer annotations capture the intended emotional character of each clip along multiple dimensions:

```json
{
  "filename": "string",
  "primary_emotion": "tension|triumph|grief|suspense|joy|dread|longing|ambiguity",
  "secondary_emotion": "string|null",
  "emotional_intensity": "1|2|3|4|5",
  "narrative_position": "opening|rising|climax|falling|resolution",
  "harmonic_mode": "major|minor|modal|atonal",
  "orchestration_density": "1|2|3|4|5",
  "composer_notes": "free text"
}
```

### Annotation Protocol

Annotations are provided by the primary researcher in the role of film composer - drawing on professional scoring experience rather than naive listener response. This is a deliberate methodological choice: the ground truth is **compositional intent**, not audience perception.

The distinction matters. A scene scored for dread may be perceived as suspense by some listeners. The annotation records what was *constructed*, not what was *received*. The gap between these is a secondary research problem addressed in EXP-004.

### Inter-Annotator Validity

A subset of clips will be re-annotated by additional film composers to establish inter-annotator agreement on emotional categories. Results and Krippendorff's alpha will be reported with publication.

---

## Phase 3 · Supervised Learning

### Classification Task Definition

Primary task: multi-class emotion classification
- Input: 71-dimensional feature vector per clip
- Output: primary emotion category (8 classes)
- Evaluation: stratified k-fold cross-validation, macro-averaged F1

Secondary tasks:
- Emotional intensity regression (1–5 scale)
- Narrative position classification (5 classes)
- Harmonic mode classification (4 classes)

### Model Hierarchy

```
Tier 1 - Classical Baselines
  SVM (RBF kernel)
  Random Forest
  Gradient Boosting (XGBoost)

Tier 2 - Deep Learning
  1D CNN on raw feature sequences
  LSTM on frame-level features

Tier 3 - Transformer
  Attention-based sequence model
  Pretrained audio model fine-tuning (evaluation pending)
```

### Evaluation Protocol

All models evaluated on held-out test set (20% stratified split). Baseline comparisons use:
- Random baseline (class-proportion weighted)
- Majority class baseline
- Human inter-annotator agreement as upper bound estimate

*Quantitative results are withheld pending full dataset completion and publication.*

---

## Phase 4 · Interpretive Analysis

### The Composer Gap Study (EXP-004)

The central interpretive research question: **where and how does the model's prediction diverge from the composer's annotation?**

Methodology:
1. Generate model predictions on the full annotated dataset
2. Compute per-clip divergence vectors (predicted class vs. annotated class)
3. Cluster divergence patterns by acoustic feature profile
4. Characterize systematic failure modes (e.g., "model conflates grief and longing in low-tempo minor-mode clips")
5. Trace each failure mode to specific acoustic feature combinations
6. Consult composer annotations to determine whether the divergence reflects acoustic ambiguity or model limitation

*Results are embargoed. The characterization of failure modes is the primary original contribution of this work.*

---

## Methodological Commitments

**Against premature reduction** - Dimensionality reduction is applied downstream of, not during, feature engineering. The full 71-dimensional feature space is preserved for interpretive analysis before PCA or UMAP is applied.

**Against naive ground truth** - Audience perception surveys are not used as primary annotation ground truth. Compositional intent is the target variable; audience perception is a secondary measurement.

**Against single-metric evaluation** - No single accuracy number will be reported as the headline result. The shape of model performance - which classes it gets right, which it confuses, and why - is the finding.

**For transparency about limits** - Every model result will include a discussion of what the feature representation cannot capture: performance nuance, orchestration space, temporal resolution, cultural encoding.

---

*Full methodological details, code, and data to be released with publication.*
*See also: [ARCHITECTURE.md](ARCHITECTURE.md) · [RESEARCH_QUESTIONS.md](RESEARCH_QUESTIONS.md)*
