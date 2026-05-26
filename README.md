# antibody-lab-in-the-loop

A from-scratch implementation of active learning for antibody binding affinity optimisation.

## Aim

Build a closed-loop system that proposes antibody variants, predicts their binding affinity with calibrated uncertainty, and selects informative batches for evaluation - using AbBiBench Benchamark dataset as retrospective oracle.

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
