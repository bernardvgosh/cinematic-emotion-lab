# Cinematic Emotion Lab

> *Can AI understand why a film score creates suspense, grief, triumph, or emotional tension?*

**Cinematic Emotion Lab** is an interdisciplinary AI research initiative at the intersection of film composition, computational musicology, and machine learning. We study how cinematic music shapes human emotional perception — and whether machines can learn to feel it too.

---

## Research Mission

Film music is among the most emotionally precise art forms ever created. A single harmonic shift can pivot a scene from hope to dread. This lab exists to decode that precision using computational tools, composer intuition, and machine learning.

---

## Core Research Areas

| Area | Description |
|------|-------------|
| **Tempo & Emotional Intensity** | How rhythmic density and BPM correlate with perceived arousal |
| **Harmonic Tension Modeling** | Mapping harmonic movement to narrative emotional arcs |
| **Spectral Density & Suspense** | Using spectral features to predict suspense and unease |
| **AI Emotion Classification** | Training models to classify cinematic emotion from audio features |
| **Composer vs. Model Prediction** | Comparing human annotation with ML output |
| **Architectural Emotion Pacing** | Spatial design principles applied to musical emotional space |

---

## Repository Structure

```
cinematic-emotion-lab/
├── notebooks/
│   ├── exploratory/        # Initial data exploration and EDA
│   ├── experiments/        # Formal ML experiments, reproducible
│   └── visualizations/     # Standalone visual analysis notebooks
├── datasets/
│   ├── raw/                # Unmodified source audio and metadata
│   ├── processed/          # Cleaned, normalized, feature-extracted data
│   ├── annotations/        # Composer and human emotion annotations
│   └── metadata/           # Film context, scene descriptions, labels
├── visualizations/
│   ├── plots/              # Generated charts and graphs
│   ├── exports/            # Publication-ready figures (PNG, SVG, PDF)
│   └── assets/             # Branding, color palettes, design tokens
├── audio-samples/
│   ├── raw/                # Original audio clips (.wav, .mp3, .flac)
│   ├── processed/          # Resampled, trimmed, normalized clips
│   └── features/           # Extracted feature files (.npy, .csv, .json)
├── research-notes/
│   ├── weekly-logs/        # Weekly research journal entries
│   ├── references/         # Papers, citations, reading notes
│   └── experiments/        # Hypothesis logs and experiment records
├── models/
│   ├── checkpoints/        # Saved model weights and states
│   ├── configs/            # Model hyperparameter configs (YAML/JSON)
│   └── results/            # Evaluation metrics, confusion matrices
├── scripts/
│   ├── feature-extraction/ # Audio feature extraction pipelines
│   ├── preprocessing/      # Data cleaning and transformation scripts
│   └── evaluation/         # Model evaluation and benchmarking scripts
├── docs/
│   ├── figures/            # Diagrams, architecture visuals
│   ├── papers/             # Draft manuscripts and publications
│   └── presentations/      # Conference slides and posters
└── .github/
    └── ISSUE_TEMPLATE/     # Issue templates for research tracking
```

---

## Technology Stack

### Audio Analysis
- `librosa` — core audio feature extraction
- `essentia` — advanced MIR and tonal analysis
- `pyaudio` / `soundfile` — audio I/O
- `mir_eval` — evaluation metrics for MIR tasks

### Machine Learning
- `scikit-learn` — classical ML baselines
- `pytorch` / `torchaudio` — deep learning and audio modeling
- `transformers` — pretrained audio/music models (e.g. MusicGen, Jukebox)
- `optuna` — hyperparameter optimization

### Visualization
- `matplotlib` / `seaborn` — statistical plots
- `plotly` — interactive visualizations
- `librosa.display` — spectrograms and audio plots
- `umap-learn` — dimensionality reduction for feature space visualization

### Data & Annotation
- `pandas` / `numpy` — data manipulation
- `Label Studio` — annotation interface
- `pydantic` — data validation schemas

---

## Current Status

- [x] Repository initialized
- [x] Folder structure scaffolded
- [ ] Dataset construction underway
- [ ] Annotation framework in progress
- [ ] Baseline ML experiments beginning
- [ ] First research note published

---

## Naming Conventions

See [NAMING_CONVENTIONS.md](NAMING_CONVENTIONS.md) for full standards covering datasets, notebooks, experiments, and visual assets.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for research contribution guidelines.

---

## Git Standards

See [GIT_STANDARDS.md](GIT_STANDARDS.md) for commit message conventions and branch naming.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## Author

**Bernard G.**
Film Composer · AI Architect · Computational Musicology Researcher

> *"Music is the shorthand of emotion. This lab is learning to read it."*

---

*Cinematic Emotion Lab — Where film composition meets machine intelligence.*
