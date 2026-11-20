# Moral-disagreement-embedding-geometry
Code for analyzing structural signatures of human disagreement in pretrained sentence-embedding spaces.

**When Moral Judgment Becomes Structurally Ambiguous: Human Disagreement Leaves a Signature in Sentence-Embedding Geometry**

This repository contains the code for studying whether **human disagreement is reflected in the structure of pretrained sentence-embedding spaces**.

The study examines moral and social judgment data using **Mapper-based structural analysis**, chance-corrected component purity, edge agreement, and local node impurity. The analysis is evaluated across multiple datasets and frozen sentence encoders, with kNN and HDBSCAN used as non-topological controls.

### Key idea

> **Can human disagreement be detected from the geometry of an embedding space, even before task-specific fine-tuning?**

The experiments show that items with stronger human disagreement tend to occupy **less label-coherent regions** of pretrained embedding spaces, while higher vote entropy is associated with greater local node impurity.

### What is included

- Mapper-based structural analysis
- Multiple sentence encoders
  - `all-MiniLM-L6-v2`
  - `all-mpnet-base-v2`
  - `bge-small-en-v1.5`
- Social Chemistry 101
- SCRUPLES
- Multi-annotator disagreement analysis
- Agreement-tier analysis
- Chance-corrected structural metrics
- Label-shuffled null models
- Seed-level replication
- Text-field ablation
- Mapper parameter sensitivity analysis
- kNN and HDBSCAN controls
- Bayesian follow-up analysis

### Main analysis pipeline

```text
Human judgments
      ↓
Text representations
      ↓
Frozen sentence embeddings
      ↓
Lens construction
      ↓
Mapper graph
      ↓
Structural metrics
      ↓
Label-shuffled null model
      ↓
Disagreement–structure analysis
```

The implementation separates the **embedding space**, the **Mapper lens**, and the **graph-based structural analysis**, allowing the observed pattern to be compared with simpler geometric and density-based methods.

### Main findings

Across two datasets and three frozen sentence encoders:

- Strongly disagreeing items show lower chance-corrected component purity than unanimous items.
- Vote entropy is positively associated with local node impurity.
- The direction of the structural effect is consistent across encoders and datasets.
- The same disagreement-related pattern is recovered by kNN and HDBSCAN controls.
- Therefore, the observed phenomenon is best interpreted as a **geometric signature of human disagreement**, with Mapper providing an interpretable structural view rather than being the only detector.

### Repository structure

```text
.
├── Mapper_Final_All_Hypotheses_Verdicts.ipynb
├── Mapper_Bayesian_BF10_FollowUp.ipynb
├── README.md
└── ...
```

### Getting started

The main notebook is designed to run in **Google Colab**.

Open:

`Mapper_Final_All_Hypotheses_Verdicts.ipynb`

and run:

```text
Runtime → Run all
```

The Bayesian follow-up is run separately after the main analysis and uses the generated final results.

### Reproducibility

The experiments use fixed analysis rules, multiple seeds, graph-specific label shuffling, and predefined decision criteria. The Bayesian follow-up treats the independent sampling seeds as the unit of analysis rather than treating graphs, lenses, or encoders as independent observations.

### Citation

If you use this code or analysis framework in your research, please cite the associated paper:

**Pedrami, M. & Saffari, Y.**  
*When Moral Judgment Becomes Structurally Ambiguous: Human Disagreement Leaves a Signature in Sentence-Embedding Geometry.*

### Authors

**Mohammad Pedrami** — University of Tehran  
**Yasaman Saffari** — University of Kashan

If you use the repository or build on the analysis, we would be happy to hear about your work.
