Pivot Language Optimization for Cross-Lingual Translation

This repository contains the code and experimental artifacts for my Honors Thesis, which investigates whether pivot (intermediary) languages can improve semantic preservation in multilingual translation pipelines—especially for under-represented languages.

The project builds on the goals of Project Symmetry, which focuses on improving cross-language consistency and accessibility of Wikipedia content through semantic alignment and human-in-the-loop translation tools.

Project Overview

Machine translation between low-resource or linguistically distant language pairs often suffers from semantic drift.
This thesis explores whether routing translations through a pivot language (e.g., English, Esperanto, Latin, Russian) can act as a semantic “bridge” and improve meaning preservation.

The project evaluates:

Direct translation (Source → Target)

Pivot-based translation (Source → Pivot → Target)

across multiple target languages using open-source multilingual models.

Target & Pivot Languages
Target Languages

French (high-resource baseline)

Swahili (under-represented)

Yoruba (under-represented)

Arabic

Hindi

Pivot Languages

English

Esperanto

Latin

Russian

Models Used

MarianNMT (Helsinki-NLP)

NLLB-200 (distilled)

These models were chosen for their open availability and strong multilingual coverage.

Evaluation Metrics

The following metrics are used:

BLEU – surface-level overlap

BERTScore – semantic similarity using contextual embeddings

Note on COMET
COMET was evaluated but excluded from the final pipeline due to dependency instability and limited sentence-level interpretability in Colab and local environments. BLEU and BERTScore provided more reliable and transparent evaluation aligned with a human-in-the-loop workflow.

Repository Structure
├── baseline_direct_pipeline.ipynb     # Main notebook (pipelines + dashboard)
├── testing_protocol.py
└── README.md

All translation outputs and metrics are saved as CSV files to ensure reproducibility and fast interaction without re-running models.

Interactive Dashboard

The notebook includes an interactive dashboard built with ipywidgets that allows users to:

Select a target language

Compare direct vs. pivot translations

Inspect translation text side-by-side

Visualize BLEU and BERTScore results

Important Note About GitHub Rendering

GitHub does not support rendering interactive ipywidgets.

To use the dashboard:

Run the notebook locally (Jupyter / VS Code)

Or open it in Google Colab

The notebook metadata has been stripped for GitHub compatibility, but all interactivity works when the notebook is executed.

How to Run
Option 1: Google Colab (Recommended)

Open the notebook in Colab

Run cells top-to-bottom

Use the dashboard at the bottom of the notebook

Option 2: Local (Jupyter / VS Code)

Clone the repository

Open baseline_direct_pipeline.ipynb

Run cells sequentially

Design Philosophy

Human-in-the-loop first: Metrics are paired with text-level inspection

Reproducible: All outputs persisted as CSV artifacts

Modular: Models, evaluation, and visualization are decoupled

Extensible: New target or pivot languages can be added with minimal changes

Relation to Project Symmetry

This work directly supports Project Symmetry’s mission to:

Improve multilingual knowledge parity

Enable comparison and summarization across languages

Support editors rather than replace them

The pivot-language analysis and dashboard can be integrated into broader semantic alignment workflows for Wikipedia content.

Author

Jameela Kauser
Honors Thesis — Arizona State University
