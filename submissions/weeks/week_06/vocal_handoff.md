# Week 06 Vocal Handoff: Memory and Self-Excitation

```
HANDOFF
turns: 4
learns by: example-in-context
domain: point processes | level: 3 | milestone: 3 reached | anchor: branching ratio
conditional intensity | claim: no | prior: none | end: introduced | no quote
history | claim: no | prior: none | end: deployed | "group 1 belongs to history Hs."
self-exciting process | claim: no | prior: none | end: introduced | no quote
Hawkes process | claim: no | prior: none | end: introduced | no quote
Cox process | claim: no | prior: none | end: unused | no quote
branching ratio | claim: no | prior: none | end: introduced | no quote
triggering kernel | claim: no | prior: none | end: introduced | no quote
time reversibility | claim: no | prior: none | end: deployed | "pairs should be equal if there isno sign convention... commutative in math"
other deployed: intensity surface, emission function, counting process, rate function, non-homogeneous Poisson process, time-rescaling theorem
other open: marked point process, marginal intensity

domain: statistical inference | level: 3 | milestone: 3 reached | anchor: degeneracy
nested model | claim: no | prior: none | end: introduced | no quote
data leakage | claim: no | prior: none | end: deployed | "mode will seeing the future before hand itself."
degeneracy | claim: no | prior: none | end: introduced | no quote
other deployed: ablation, generalization, leave-one-cycle-out cross-validation, partial pooling, latent variable, gauge freedom, maximum likelihood, Kolmogorov-Smirnov statistic, leaderboard, overfitting, model selection, metric gaming
other open: opportunistic stopping leak

domain: solar cycle physics | level: 3 | milestone: 3 reached | anchor: active nest
active nest | claim: no | prior: none | end: unused | no quote
solar rotation period | claim: no | prior: none | end: unused | no quote
other deployed: belt width, buoyancy threshold, Maunder minimum, hemispheric cycle, solar cycle, sunspot area, butterfly diagram, Waldmeier effect, hemispheric decoupling
other open: corrected area, MSH, Joy's law, Hale's law

domain: machine learning | level: 3 | milestone: 3 reached | anchor: feature engineering
feature engineering | claim: no | prior: none | end: unused | no quote
other deployed: neural field, activation function, automatic differentiation, conditioning, FiLM
other open: multilayer perceptron, tensor, gradient descent, Adam optimizer, learning rate, epoch, initialization, validation set
```

---

### Section 3, 4 & 6 Required Written Predictions (Locked Prior to Implementation)

1. **Prediction 1 (Arrow of Time / Pair Counts, Section 3)**:
   - *Prediction*: Counting pairs within a fixed short separation forward in time versus backward in time on time-rescaled events will yield **identical counts**.
   - *Mechanism*: Pairwise Euclidean distances $|t_B - t_A|$ are symmetric and mathematically commutative ($A \leftrightarrow B$). Two-point pair correlation functions possess time-reversibility and contain no arrow of time, necessitating directional history likelihood fits to detect causal asymmetry.

2. **Prediction 2 (Four-Way Evaluation Outcome, Section 4)**:
   - *Prediction*: **Cell 2 ("Triggering survives")**—adding history will buy a positive likelihood gain ($\Delta > 0$) on both the Week 4 parametric champion and the Week 5 neural field.
   - *Mechanism*: Sunspot emergence exhibits true physical, realization-specific spatio-temporal memory on the solar surface that cannot be absorbed even by a highly flexible continuous neural field.

3. **Prediction 3 (History Gain on Champion, Section 4)**:
   - *Prediction*: Adding the 8-channel history bank to the Week 4 champion will improve held-out negative log-likelihood by **$\approx +2.0$ nats/hemicycle-year**.
   - *Mechanism*: A localized triggering kernel captures rapid 1-to-2 day clustering bursts that the rigid, slowly-varying parametric shape ($29$ parameters) fails to resolve, surpassing the experimental resolution floor ($\sim 0.3$ to $1.0$ nats).

4. **Prediction 4 (Anti-Gaming Self-Parenting Leak, Section 6)**:
   - *Prediction*: Flipping the strict inequality from `<` to `<=` in the history bank will buy an artificial gain of **$+20$ to $+30$ nats/hemicycle-year**, dwarfing all previous protocol leaks.
   - *Mechanism*: When an event evaluates itself as a parent ($\Delta s = 0, \Delta \lambda = 0$), the kernel reaches its analytic maximum ($e^{-0} = 1.0$), delivering an unearned direct additive bonus to $\log \Lambda$ for every observed event. Simultaneously, the narrow 1-to-2 day spike contributes virtually negligible area to the integral penalty ($-\iint \Lambda$), creating an overwhelming mathematical asymmetry.
