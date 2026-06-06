# Contributing to Cinematic Emotion Lab

Thank you for your interest in contributing to this research initiative. This document outlines the standards and expectations for contributions.

---

## Who Can Contribute

This is an open research lab. Contributors may include:

- Computational musicologists
- ML/AI researchers
- Film composers and music theorists
- Data scientists and engineers
- Visualization designers
- Annotation volunteers

---

## Ways to Contribute

### Research Contributions
- Propose new research hypotheses via GitHub Issues
- Add annotated audio samples to the dataset
- Contribute composer interpretations and emotion labels
- Write research notes or literature reviews

### Technical Contributions
- Improve feature extraction scripts
- Build or improve ML experiments
- Add visualization utilities
- Write tests and improve code quality

### Documentation
- Improve or expand this README
- Translate research notes
- Create tutorial notebooks

---

## Getting Started

1. Fork the repository
2. Create a feature branch:
   ```
   git checkout -b feature/your-contribution-name
   ```
3. Follow the [Naming Conventions](NAMING_CONVENTIONS.md)
4. Follow the [Git Standards](GIT_STANDARDS.md)
5. Submit a pull request with a clear description

---

## Code Standards

- Python 3.10+
- Follow PEP 8 style guidelines
- Use type hints where possible
- All notebooks must be cleared of output before committing
- Scripts must include a `main()` entry point

---

## Notebook Standards

- One experiment per notebook
- Clear markdown cells explaining each section
- Use the naming convention: `NB-XXX_topic-name_YYYY-MM-DD.ipynb`
- Clear all outputs before committing

---

## Dataset Contributions

- Audio samples must be original, royalty-free, or properly licensed
- Include metadata: title, composer, film/context, year, BPM, key, mood
- Place raw files in `datasets/raw/` and annotated files in `datasets/annotations/`
- Use the annotation schema in `datasets/annotations/schema.json`

---

## Pull Request Guidelines

- Keep PRs focused — one contribution per PR
- Reference any related Issues
- Include a brief description of what was added and why
- Maintainer review is required before merging

---

## Research Ethics

- Do not commit copyrighted audio without proper licensing
- Cite all external references and papers
- Attribute composer annotations properly
- Be transparent about model limitations and dataset biases

---

## Questions?

Open a GitHub Issue with the label `question` or reach out via the repository contact.

---

*Cinematic Emotion Lab — Collaborative research at the intersection of art and intelligence.*
