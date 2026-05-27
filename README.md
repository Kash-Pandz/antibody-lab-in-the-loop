# antibody-lab-in-the-loop

A from-scratch implementation of active learning for antibody binding affinity optimisation. Uses the AbBiBench dataset as a restrospective oracle: a generative proposer suggests antibody variants, an uncertainty-aware suurogate predicts their binding scores, and an acquisition function selects informative batches to "query" the oracle. The surrogate retrains each round and the loop closes.

# Architecture

┌─────────────┐      ┌────────────┐      ┌──────────────┐
│  Proposer   │─────▶│ Surrogate │─────▶│ Acquisition  │
│ (mutations) │      │ (GP / NN)  │      │  (qEI + DPP) │
└─────────────┘      └────────────┘      └──────┬───────┘
       ▲                    ▲                    │
       │                    │                    ▼
       │             ┌────────────┐      ┌──────────────┐
       └─────────────│   Oracle   │◀─────│    Batch     │
                     │ (AbBiBench)│      │  (selected)  │
                     └────────────┘      └──────────────┘


## Status

In active development. Currently working on baseline surrogate.

## Roadmap

- [ ]  AbBbench dataloader, cluster-based splits
- [ ]  ESM-2 baseline surrogate
- [ ]  GP surrogate with uncertainty
- [ ]  Acquisition function + proposer
- [ ]  Closed loop, baselines, regret curves
- [ ]  GNN structural surrogate
- [ ]  Multi-objective extension 
