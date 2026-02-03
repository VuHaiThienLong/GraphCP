# GraphCP: Conformal Prediction for Graph Link Prediction

This project implements **Mondrian Conformal Prediction** for link prediction on both **directed** and **undirected** graphs. The goal is to predict missing edges in graphs while providing statistical guarantees on prediction coverage.

## Key Features

- **Directed graph link prediction** using 6 features (degree + SVD-based similarity)
- **Undirected graph link prediction** using 3 features
- **Large-scale support** for OGB (Open Graph Benchmark) datasets
- **Uncertainty quantification** through prediction sets with coverage guarantees
- **Feature importance analysis** via GradientBoosting classifiers

## Main Notebooks

**Everything you need is in the 3 notebooks at the root level:**

| Notebook | Description |
|----------|-------------|
| [`directed_netset.ipynb`](directed_netset.ipynb) | Link prediction on directed graphs (WikiVitals, WikiSchools, WikiHumans, WikiVitals-FR, MathWorld) |
| [`undirected_netset.ipynb`](undirected_netset.ipynb) | Link prediction on undirected graphs (CiteSeer, OpenFlights) |
| [`ogbl-citation2.ipynb`](ogbl-citation2.ipynb) | Large-scale link prediction on OGB Citation2 dataset (2.9M nodes, 30M+ edges) |

All **implementation details**, **experimental results**, and **visualizations** can be found directly in these notebooks.

## Methodology

1. **SVD Embeddings**: Compute node embeddings from the adjacency matrix
2. **Feature Engineering**: Extract degree and similarity features for node pairs
3. **GradientBoosting Classifier**: Train on supervision edges
4. **Mondrian Conformal Prediction**: Calibrate thresholds for label-conditional coverage guarantees

## Results Summary

- **Directed graphs**: AUC 0.91-0.95, CP retention 84-97%
- **Undirected graphs**: AUC 0.76-0.96, CP retention 43-99%
- **Coverage**: Consistently meets target (1-α = 0.90)
