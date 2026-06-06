# Git Standards — Cinematic Emotion Lab

Clear, consistent git history is part of reproducible research. Every commit should tell a story.

---

## Commit Message Format

```
[TYPE] scope: short imperative summary (max 72 chars)

Optional body: what changed and why. Wrap at 72 chars.
Reference experiments, notebooks, or issues by ID.
```

---

## Commit Types

| Type | When to Use |
|------|-------------|
| `[DATA]` | Adding, modifying, or annotating dataset files |
| `[NB]` | Adding or updating a notebook |
| `[EXP]` | Adding or updating an experiment |
| `[FEAT]` | New script or feature in codebase |
| `[FIX]` | Bug fix in script or notebook |
| `[VIZ]` | Adding or updating visualizations |
| `[DOCS]` | README, notes, research logs, references |
| `[REFACTOR]` | Code restructuring without behavior change |
| `[CONFIG]` | Model configs, YAML files, environment setup |
| `[LOG]` | Weekly research log entries |

---

## Commit Examples

```
[DATA] datasets: add INC001 raw audio and metadata

Added 12 audio clips from Inception OST reference batch.
Includes BPM, key, and emotional label annotations.
Relates to EXP-001.

[NB] experiments: add NB-002 MFCC baseline classifier

Initial SVM classifier using MFCC features.
Accuracy: 67% on 3-class emotion task (tension/triumph/grief).
See EXP-001_results for full metrics.

[EXP] models: add EXP-002 CNN suspense detection config

Config for 1D CNN trained on spectral features.
Target: binary suspense classification.

[VIZ] visualizations: add tempo vs arousal scatter plot

FIG-01 generated from NB-001 EDA results.
Shows positive correlation r=0.71 across 48 samples.

[LOG] research-notes: add Week 01 research log

Initial dataset construction and annotation setup.

[DOCS] readme: update status and folder structure table
```

---

## Branch Naming

```
[type]/[short-description]
```

| Prefix | Purpose |
|--------|---------|
| `experiment/` | A new ML experiment branch |
| `notebook/` | New or updated analysis notebook |
| `data/` | Dataset ingestion or annotation work |
| `feature/` | New script or pipeline feature |
| `viz/` | Visualization work |
| `docs/` | Documentation only |
| `fix/` | Bug fixes |

**Examples:**
```
experiment/exp-002-cnn-suspense
notebook/nb-003-harmonic-tension-viz
data/inc001-annotation-pass-1
feature/mfcc-extraction-pipeline
viz/umap-emotion-clusters
docs/week-02-research-log
```

---

## Branch Workflow

```
main              ← stable, publication-ready state
└── experiment/   ← active experiments (merge when complete)
└── notebook/     ← analysis notebooks (merge after review)
└── data/         ← dataset work (merge after validation)
└── docs/         ← merge freely
```

- Never commit directly to `main`
- Use pull requests for experiment and data branches
- `docs/` and `[LOG]` commits may be pushed directly to `main`

---

## Tag Standards

Use semantic tags for research milestones:

```
v0.1.0 — initial dataset and annotation schema
v0.2.0 — first baseline ML results
v1.0.0 — first complete experiment suite (conference-ready)
```

---

## What NOT to Commit

- Raw audio files > 50MB (use Git LFS or external storage)
- Model checkpoints (gitignored by default)
- Notebook outputs (clear before committing)
- API keys, credentials, `.env` files
- Processed datasets (document pipeline instead)

---

*Cinematic Emotion Lab — Every commit is a research decision.*
