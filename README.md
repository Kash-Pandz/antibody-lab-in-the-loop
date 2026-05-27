# antibody-lab-in-the-loop

A from-scratch implementation of active learning for antibody binding affinity optimisation. Uses the AbBiBench dataset as a restrospective oracle: a generative proposer suggests antibody variants, an uncertainty-aware suurogate predicts their binding scores, and an acquisition function selects informative batches to "query" the oracle. The surrogate retrains each round and the loop closes.

## The Core Loop
1. Train a model on initial antibody data (in this case binding affinity data from AbiBiBench) - other developtability properties can be used e.g. expression, thermostability or aggregation
2. Predict and select - the model proposes candidate sequences, and an acuisition function picks which ones to test next, balancing exploitation (high predicted performance) against exploration (high uncertainty/information gain)
3. Experimentally measure the selected candidates in the wet lab
4. Update the model with new data and repeat


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
