# Crypto AML Network Analyzer

Individual project for **WIH3001 Data Science Project**, Universiti Malaya. Supervisor: Dr. Nor Liyana Mohd Shuib.

**Status: in progress.** The proposal and design are done. Experiments and the dashboard are being built, so there are no results yet.

## Problem

Compliance teams must screen a huge number of Bitcoin transactions for money laundering, and most alerts turn out to be false alarms. Analysts have no reliable way to rank alerts by risk, so review time is spent on the wrong cases while real illicit transactions can be missed.

Bitcoin payments are public, so the network of payments between transactions is visible. Researchers disagree on whether using this network actually helps detect illicit transactions, so this project tests it directly.

## Research questions

1. How well can a transaction's own features rank illicit transactions above the rest?
2. Does the payment network improve the ranking, and how does the number of alerts needed to catch the same illicit transactions change?
3. Do rankings stay reliable when conditions change, such as the dark-market shutdown at time step 43?
4. What should be shown next to a risk score so an analyst can judge it, and can test users complete prioritisation tasks with it?

## Objectives

1. Reproduce the benchmark from the published research.
2. Determine whether the payment network improves detection.
3. Measure how models behave after the step-43 market shutdown.
4. Build an analyst dashboard and test it with users.

## Dataset

[Elliptic Data Set](https://www.kaggle.com/datasets/ellipticco/elliptic-data-set): a Bitcoin transaction graph with illicit and licit labels across 49 time steps. The data is not included in this repository. Check the Kaggle page for its license terms.

Citation: Weber, M., Domeniconi, G., Chen, J., Weidele, D. K. I., Bellei, C., Robinson, T., Leiserson, C. E. (2019). *Anti-Money Laundering in Bitcoin: Experimenting with Graph Convolutional Networks for Financial Forensics.* KDD '19 Workshop on Anomaly Detection in Finance. arXiv:1908.02591.

## Methodology (CRISP-DM)

| Phase | Plan |
|---|---|
| Business understanding | Define the alert-prioritisation decision and agree the measures |
| Data understanding | Label coverage, illicit share per time step, and which features are local or neighbour summaries |
| Data preparation | Temporal split: train on time steps 1-34, test on 35-49 |
| Modelling | Random Forest, GCN, GraphSAGE and a hybrid model |
| Evaluation | Per-step results with sample counts, 5 runs per model |
| Deployment | Streamlit dashboard from precomputed scores, user manual and a usability test |

## Progress

- [x] Literature review and project proposal
- [ ] Data understanding and preparation
- [ ] Baseline: Random Forest on transaction features
- [ ] Graph models: GCN, GraphSAGE and hybrid
- [ ] Evaluation, including the step-43 shutdown
- [ ] Streamlit dashboard and usability test

## Results

Coming soon.

## Planned repository structure

```
.
├── README.md
├── requirements.txt
├── notebooks/
├── dashboard/
└── images/
```

## Tools

Python, pandas, scikit-learn, PyTorch, a graph neural network library, Streamlit.
