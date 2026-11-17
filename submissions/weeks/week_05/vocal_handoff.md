# Week 05 Vocal Handoff: Neural Fields

```
HANDOFF
turns: 6
learns by: example-in-context
domain: machine learning | level: 2 | milestone: 2 reached | anchor: Adam optimizer
neural field | claim: no | prior: none | end: deployed | "since neural field can learn about arbitray continous functions of latitude and time"
multilayer perceptron | claim: no | prior: none | end: introduced | "explain multilayer percep[tion better and also what is activetion function"
activation function | claim: no | prior: none | end: deployed | "if we turned off the activetion function then i think we would just get linear function"
tensor | claim: no | prior: none | end: introduced | no quote
automatic differentiation | claim: no | prior: none | end: deployed | "it calculates the gradient for all simulataneously."
gradient descent | claim: no | prior: none | end: introduced | no quote
Adam optimizer | claim: no | prior: none | end: introduced | no quote
learning rate | claim: no | prior: none | end: introduced | no quote
epoch | claim: no | prior: none | end: introduced | no quote
initialization | claim: no | prior: none | end: introduced | no quote
conditioning | claim: no | prior: none | end: deployed | "the strength of cycle or amplitude."
FiLM | claim: no | prior: none | end: deployed | "I think FilM will achieve better held-out results as it can directly scales and shifts"
validation set | claim: no | prior: none | end: introduced | no quote
other deployed: none
other open: computational graph, forward pass, backward pass

domain: solar cycle physics | level: 3 | milestone: 2 reached | anchor: hemispheric asymmetry
Waldmeier effect | claim: no | prior: none | end: deployed | "waldier effect predicts that it will reach the peak much faster than 24."
other deployed: belt width, buoyancy threshold, Maunder minimum, hemispheric cycle, solar cycle, sunspot area, butterfly diagram
other open: corrected area, MSH, Joy's law, Hale's law, hemispheric asymmetry

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
```

---

### Section 2 Required Written Predictions (Locked Prior to Implementation)

1. **In-Sample Fit**:
   - *Prediction*: The in-sample negative log-likelihood (NLL) will improve (lower loss / more positive log-likelihood per hemicycle-year) compared to the Week 4 classical champion across the 18 development hemicycles.
   - *Mechanism*: A continuous neural field ($|\lambda|, s \to B$) is not constrained to rigid parametric shapes (such as Gaussian latitude slices or exponential drift profiles) and possesses the capacity to adapt to observed non-linearities and local butterfly wing contours across the dataset.

2. **Held-Out Fit**:
   - *Prediction*: The neural field will beat the Week 4 classical champion on held-out cycles.
   - *Mechanism*: By learning physical butterfly wing geometry and butterfly ridge curvature directly from the Poisson point process likelihood across 18 training wings, the network learns genuine underlying features rather than rigid parametric compromises.

3. **Conditioning Architecture (Section 4)**:
   - *Prediction*: **FiLM** (Feature-wise Linear Modulation) will outperform simple input **concatenation** on held-out cycles.
   - *Mechanism*: Input concatenation merely appends cycle amplitude to $(|\lambda|, s)$ at the input layer, requiring early layers to disentangle it. In contrast, FiLM directly applies affine transformations (scale $\gamma$ and shift $\beta$) to intermediate feature activations throughout the network depth, directly modulating latent field amplitude and ridge structure.

4. **Early-Stopping Leak (Section 3)**:
   - *Prediction*: Stopping training opportunistically at the epoch preferred by the held-out wing being evaluated (data leak) will buy approximately **2.0 nats/hemicycle-year**.
   - *Mechanism*: Evaluating against the test wing directly overfits to stochastic fluctuations of that specific wing's event times, setting an artificial, ungeneralizable performance ceiling compared to a strictly fixed epoch budget chosen on an independent validation cycle.
