# Naming Conventions — Cinematic Emotion Lab

Consistent naming across all assets enables reproducibility, searchability, and long-term scalability. Follow these conventions strictly.

---

## Datasets

### Raw Audio Files
```
[FILM-CODE]_[COMPOSER-INITIALS]_[SCENE-TYPE]_[EMOTION-LABEL]_[BPM]bpm.[ext]
```
**Examples:**
```
INC001_BG_opening-sequence_tension_72bpm.wav
DRK002_JW_climax_triumph_120bpm.flac
AMB003_HZ_transition_grief_56bpm.wav
```

**Scene Types:** `opening-sequence`, `climax`, `transition`, `resolution`, `action`, `dialogue`, `montage`
**Emotion Labels:** `tension`, `triumph`, `grief`, `suspense`, `joy`, `dread`, `longing`, `ambiguity`

---

### Annotation Files
```
[FILM-CODE]_annotations_v[VERSION]_[YYYY-MM-DD].csv
```
**Example:**
```
INC001_annotations_v1_2026-06-06.csv
```

---

### Processed Feature Files
```
[FILM-CODE]_features_[FEATURE-TYPE]_[YYYY-MM-DD].[ext]
```
**Feature Types:** `mfcc`, `chroma`, `spectral`, `tempo`, `combined`
**Example:**
```
INC001_features_mfcc_2026-06-06.npy
DRK002_features_combined_2026-06-15.csv
```

---

### Metadata Files
```
[FILM-CODE]_metadata.[ext]
```
**Example:**
```
INC001_metadata.json
```

---

## Notebooks

```
NB-[XXX]_[topic-slug]_[YYYY-MM-DD].ipynb
```

- `NB-XXX` — zero-padded three-digit sequence number
- `topic-slug` — lowercase, hyphen-separated description
- `YYYY-MM-DD` — creation date

**Examples:**
```
NB-001_eda-tempo-vs-emotion_2026-06-06.ipynb
NB-002_mfcc-baseline-classifier_2026-06-10.ipynb
NB-003_harmonic-tension-visualization_2026-06-15.ipynb
NB-004_composer-vs-model-comparison_2026-06-20.ipynb
```

**Sub-prefixes by type:**
| Prefix | Type |
|--------|------|
| `NB-EXP-XXX` | Formal experiment notebook |
| `NB-EDA-XXX` | Exploratory data analysis |
| `NB-VIZ-XXX` | Visualization-focused notebook |

---

## Experiments

```
EXP-[XXX]_[model-type]_[task]_[YYYY-MM-DD]
```

**Examples:**
```
EXP-001_svm_emotion-classification_2026-06-10
EXP-002_cnn_suspense-detection_2026-06-18
EXP-003_transformer_arousal-valence_2026-07-01
```

### Experiment Config Files (in `models/configs/`)
```
EXP-[XXX]_config.yaml
```

### Experiment Results Files (in `models/results/`)
```
EXP-[XXX]_results_[YYYY-MM-DD].json
EXP-[XXX]_confusion-matrix_[YYYY-MM-DD].png
```

---

## Visual Assets

### Plots & Figures
```
[PLOT-TYPE]_[subject]_[YYYY-MM-DD].[ext]
```

**Plot Types:** `spectrogram`, `waveform`, `scatter`, `heatmap`, `barplot`, `lineplot`, `umap`, `confusion-matrix`

**Examples:**
```
spectrogram_INC001-tension_2026-06-06.png
umap_emotion-clusters_2026-06-15.svg
heatmap_harmonic-tension-arc_2026-06-20.pdf
```

### Publication-Ready Exports (in `visualizations/exports/`)
```
FIG-[XX]_[description]_[YYYY-MM-DD].[ext]
```
**Example:**
```
FIG-01_tempo-vs-arousal-scatter_2026-06-20.pdf
FIG-02_spectral-density-suspense_2026-06-25.svg
```

---

## Scripts

```
[action]_[subject].[py]
```

**Examples:**
```
extract_mfcc_features.py
preprocess_audio_clips.py
evaluate_emotion_classifier.py
annotate_dataset_schema.py
```

---

## Research Logs

```
WEEK-[XX]_[YYYY-MM-DD]_research-log.md
```

**Example:**
```
WEEK-01_2026-06-06_research-log.md
WEEK-02_2026-06-13_research-log.md
```

---

## Branch Names (Git)

See [GIT_STANDARDS.md](GIT_STANDARDS.md) for branch naming conventions.

---

*Consistent naming = reproducible science.*
