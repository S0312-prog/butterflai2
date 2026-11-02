# Week 04 Vocal Handoff: Scoreboard 1

```
HANDOFF
turns: 5
learns by: example-in-context
domain: point processes | level: 2 | milestone: 2 reached | anchor: marginal intensity
marginal intensity | claim: no | prior: none | end: introduced | no quote
other deployed: intensity surface, emission function, counting process, rate function, non-homogeneous Poisson process, time-rescaling theorem
other open: marked point process

domain: statistical inference | level: 3 | milestone: 2 reached | anchor: metric gaming
ablation | claim: no | prior: none | end: deployed | "Goal of sinle knob ablation is to find the generalization of that"
generalization | claim: no | prior: none | end: deployed | "find the generalization of that individual knob rather than whole model"
leaderboard | claim: no | prior: none | end: introduced | no quote
overfitting | claim: no | prior: none | end: introduced | no quote
model selection | claim: no | prior: none | end: introduced | no quote
metric gaming | claim: no | prior: none | end: introduced | no quote
other deployed: leave-one-cycle-out cross-validation, partial pooling, latent variable, gauge freedom, maximum likelihood, Kolmogorov-Smirnov statistic
other open: data leakage

domain: solar cycle physics | level: 3 | milestone: 2 reached | anchor: hemispheric asymmetry
hemispheric asymmetry | claim: no | prior: none | end: introduced | no quote
other deployed: belt width, buoyancy threshold, Maunder minimum, hemispheric cycle, solar cycle, sunspot area, Waldmeier effect
other open: corrected area, MSH, Joy's law, Hale's law
```

### Session Summary & Novel Knob (Task 36)
- **Conceptual Grounding**: Single-knob **ablations** isolate causal mechanisms and prevent **overfitting**, whereas bundling multiple modifications can hide underperforming components behind high-performing ones.
- **Novel Knob for Task 36**:
  - **Target Stage**: `drift` (shipped with only one value, `"exponential"`).
  - **Hypothesis**: Sunspot belts do not drift towards the equator at a constant exponential rate; the drift velocity changes over time $s$, decelerating as the active zone approaches the equator.
  - **Mathematical Formulation**:
    $$\mu(s) = \mu_a \exp(-s / \mu_b) \cdot (1 + \kappa \cdot s)$$
  - **Baseline Reduction**: When $\kappa = 0$, $\mu(s) = \mu_a \exp(-s / \mu_b)$, reducing identically to the baseline exponential drift track.
  - **Expected Physical Sign**: $\kappa > 0$ (the equatorward migration slows down later in the cycle).
- **Leaderboard Metrics**: Models on the **leaderboard** are scored on both full 2D **held-out NLL** (nats/hemicycle-year) and the 1D time-rescaling KS statistic on the **marginal intensity** $\lambda(s) = \int \Lambda(|\lambda|, s)\,d|\lambda|$.
- **Anti-Gaming**: Protocol violations (such as coarsening quadrature meshes or adding empty observation window padding) manipulate the metric without improving predictions.
