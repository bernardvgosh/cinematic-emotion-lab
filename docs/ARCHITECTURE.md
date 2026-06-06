# System Architecture
## Cinematic Emotion Lab · Computational Infrastructure

---

## Design Philosophy

The architecture of this system is built around a single principle: **each layer must be independently interrogable.** Any component — the feature extractor, the annotation schema, the classifier — should be replaceable without cascading failure through the pipeline. This modularity is not engineering convenience; it is a research requirement. As our understanding of cinematic emotion deepens, the system must be able to evolve.

---

## System Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    CINEMATIC EMOTION LAB                        │
│                     System Architecture v1.0                    │
└─────────────────────────────────────────────────────────────────┘

┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  AUDIO INPUT │───▶│PREPROCESSING │───▶│   FEATURE    │
│              │    │    LAYER     │    │  EXTRACTION  │
│ .wav .mp3    │    │              │    │    ENGINE    │
│ .flac .aif   │    │ normalize    │    │              │
│              │    │ trim         │    │ MFCCs        │
│ 22050Hz mono │    │ resample     │    │ Chroma CQT   │
└──────────────┘    └──────────────┘    │ Spectral     │
                                        │ RMS / ZCR    │
                                        │ HPSS         │
                                        │ Tempo        │
                                        └──────┬───────┘
                                               │
                                               ▼
                                    ┌──────────────────┐
                                    │   FEATURE MATRIX │
                                    │  N × 71 dims     │
                                    │  pandas DataFrame│
                                    │  CSV export      │
                                    └──────┬───────────┘
                                           │
                         ┌─────────────────┴──────────────────┐
                         │                                     │
                         ▼                                     ▼
               ┌──────────────────┐               ┌──────────────────┐
               │   ANNOTATION     │               │   VISUALIZATION  │
               │     LAYER        │               │     ENGINE       │
               │                  │               │                  │
               │ Emotion labels   │               │ Spectrograms     │
               │ Intensity 1–5    │               │ Waveforms        │
               │ Narrative pos.   │               │ MFCC heatmaps    │
               │ Harmonic mode    │               │ Chroma radar     │
               │ Composer notes   │               │ UMAP projections │
               └──────┬───────────┘               └──────────────────┘
                      │
                      ▼
           ┌──────────────────────┐
           │   MERGED DATASET     │
           │  features + labels   │
           │  N clips × 79 cols   │
           └──────┬───────────────┘
                  │
       ┌──────────┴────────────┐
       │                       │
       ▼                       ▼
┌─────────────┐       ┌──────────────────┐
│  CLASSICAL  │       │  DEEP LEARNING   │
│   BASELINE  │       │     MODELS       │
│             │       │                  │
│ SVM         │       │ 1D CNN           │
│ RF          │       │ LSTM             │
│ XGBoost     │       │ Transformer      │
└──────┬──────┘       └──────┬───────────┘
       │                     │
       └──────────┬──────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │     EVALUATION       │
       │                      │
       │ Stratified k-fold    │
       │ Macro-avg F1         │
       │ Confusion matrices   │
       │ Per-class analysis   │
       └──────┬───────────────┘
              │
              ▼
   ┌──────────────────────────┐
   │  COMPOSER GAP ANALYSIS   │
   │                          │
   │ Predicted vs. annotated  │
   │ Divergence clustering    │
   │ Failure mode taxonomy    │
   └──────────────────────────┘
```

---

## Layer Specifications

### Layer 0 · Audio Input

**Accepted formats:** `.wav` · `.mp3` · `.flac` · `.aif` · `.aiff`
**Target spec:** 22050Hz · mono · float32 · minimum 10 seconds
**Storage:** Not committed to repository — managed externally. Feature matrices and metadata only.

---

### Layer 1 · Preprocessing

**Module:** `scripts/preprocessing/preprocess_audio.py`

Operations:
- Format detection and conversion via `soundfile` / `librosa`
- Resampling to 22050Hz
- Mono conversion (average channels if stereo)
- Amplitude normalization to [-1.0, 1.0] peak
- Silence trimming (`top_db=30`, frame-length=2048)
- Duration validation (minimum 10s)
- Output: standardized `.wav` in `audio-samples/processed/`

---

### Layer 2 · Feature Extraction Engine

**Module:** `scripts/feature-extraction/extract_features.py`
**Notebook:** `notebooks/experiments/NB-EXP-001_cinematic-feature-extraction.ipynb`

Core parameters:
```
SAMPLE_RATE = 22050
N_FFT       = 2048
HOP_LENGTH  = 512
N_MFCC      = 13
```

Feature groups and output dimensionality: see [METHODOLOGY.md](METHODOLOGY.md)

Output: CSV feature matrix at `audio-samples/features/EXP-XXX_features_combined_YYYY-MM-DD.csv`

---

### Layer 3 · Annotation Layer

**Interface:** Label Studio (local deployment)
**Schema:** `datasets/annotations/schema.json`
**Output:** `datasets/annotations/EXP-XXX_annotations_vX_YYYY-MM-DD.csv`

The annotation layer is the only human-in-the-loop component of the pipeline. It is deliberately kept separate from the feature extraction layer to prevent annotator bias from acoustic properties.

---

### Layer 4 · Modeling Layer

**Classical baselines:** `scripts/evaluation/run_baseline_classifiers.py`
**Deep learning:** `notebooks/experiments/NB-EXP-002_*.ipynb` *(upcoming)*
**Config format:** YAML at `models/configs/EXP-XXX_config.yaml`
**Tracking:** MLflow at `mlruns/`
**Results:** `models/results/EXP-XXX_results_YYYY-MM-DD.json`

---

### Layer 5 · Visualization Engine

**Module:** `scripts/visualization/` *(in development)*
**Notebooks:** `notebooks/visualizations/NB-VIZ-XXX_*.ipynb`
**Output paths:** `visualizations/plots/` · `visualizations/exports/`

Visualization types: static (matplotlib/seaborn) + interactive (plotly). All publication-ready exports at 300dpi, PDF/SVG.

---

## Data Flow Specification

```
audio-samples/raw/          →  preprocessing  →  audio-samples/processed/
audio-samples/processed/    →  extraction     →  audio-samples/features/
audio-samples/features/     →  annotation     →  datasets/annotations/
datasets/annotations/       +  features/      →  datasets/processed/ (merged)
datasets/processed/         →  modeling       →  models/results/
models/results/             →  analysis       →  visualizations/
```

---

## Technology Versions

| Package | Version | Role |
|---------|---------|------|
| Python | 3.10+ | Runtime |
| librosa | 0.10.1+ | Audio analysis |
| numpy | 1.26+ | Numerical computation |
| pandas | 2.1+ | Data handling |
| scikit-learn | 1.3+ | Classical ML |
| torch | 2.1+ | Deep learning |
| torchaudio | 2.1+ | Audio deep learning |
| plotly | 5.17+ | Interactive visualization |
| matplotlib | 3.8+ | Static visualization |
| mlflow | 2.7+ | Experiment tracking |
| optuna | 3.4+ | Hyperparameter optimization |
| umap-learn | 0.5.4+ | Dimensionality reduction |

---

## Scalability Considerations

The current architecture is designed for a dataset of 200–500 clips. For larger scale deployment the following extensions are planned:
- Parallel feature extraction with `joblib`
- Dask-based feature matrix handling for >10k clips
- Vector database integration for semantic similarity search
- API layer for real-time feature extraction on new audio

---

*Architecture documentation version 1.0 · Active development*
*See also: [METHODOLOGY.md](METHODOLOGY.md)*
