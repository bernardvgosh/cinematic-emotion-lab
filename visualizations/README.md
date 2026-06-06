# Visualizations
## Cinematic Emotion Lab

This directory contains all generated research figures and publication-ready exports.

## Structure

```
visualizations/
├── plots/     # Generated charts and figures (PNG)
├── exports/   # Publication-ready outputs (PDF, SVG, high-res PNG)
└── assets/    # Brand identity, diagrams, visual identity system
```

## Naming Convention

```
[PLOT-TYPE]_[subject]_[YYYY-MM-DD].[ext]
FIG-[XX]_[description]_[YYYY-MM-DD].[ext]   ← publication exports
```

## Visual Assets

| File | Description |
|------|-------------|
| `assets/CEL_banner_hero.png` | GitHub README hero banner |
| `assets/CEL_pipeline_intelligence.png` | 7-stage pipeline infographic |
| `assets/CEL_research_architecture.png` | Research architecture stats |
| `assets/CEL_emotion_heatmap_analysis.png` | Temporal emotion heatmap |
| `assets/CEL_color_palette.png` | Brand color system |
| `assets/CEL_thumbnail_linkedin.png` | LinkedIn/GitHub social card |

## Visualization Stack

- `matplotlib` + `seaborn` — static research figures
- `plotly` — interactive charts (saved as `.html`)
- `librosa.display` — spectrograms and audio plots
- `umap-learn` — feature space topology projections
