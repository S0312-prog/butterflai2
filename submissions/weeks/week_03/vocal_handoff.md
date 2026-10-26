# Week 03 Vocal Handoff: 2D Latent-Belt Point Process Model

```
HANDOFF
turns: 7
learns by: example-in-context
domain: point processes | level: 2 | milestone: 2 reached | anchor: intensity surface
emission function | claim: no | prior: none | end: deployed | "c can remain same but B_crit will have to be 10 times original"
intensity surface | claim: no | prior: none | end: introduced | no quote
other deployed: counting process, rate function, non-homogeneous Poisson process, time-rescaling theorem
other open: 2D likelihood

domain: statistical inference | level: 3 | milestone: 2 reached | anchor: leave-one-cycle-out cross-validation
latent variable | claim: no | prior: none | end: deployed | "optimizer cannot fit both at the same time because b_crit cannot be greater than B"
gauge freedom | claim: no | prior: none | end: deployed | "c can remain same but B_crit will have to be 10 times original"
partial pooling | claim: no | prior: none | end: deployed | "fitting everything together with smae belt shape ensures continiuity if fitted on its own"
leave-one-cycle-out cross-validation | claim: no | prior: none | end: deployed | "if test events are seen then the t_0 will be predicted based on that"
held-out log-likelihood | claim: no | prior: none | end: introduced | no quote
quadrature mesh | claim: no | prior: none | end: introduced | no quote
other deployed: maximum likelihood, Kolmogorov-Smirnov statistic
other open: data leakage

domain: solar cycle physics | level: 3 | milestone: 2 reached | anchor: belt width
buoyancy threshold | claim: no | prior: correct | end: deployed | "sunspots with magnetic field above those are formed"
drift track | claim: no | prior: none | end: introduced | no quote
belt width | claim: no | prior: none | end: deployed | "same width with denser spots, width model with smaller with will be socred"
other deployed: hemispheric cycle, solar cycle, Maunder minimum, sunspot area, Waldmeier effect
other open: Joy's law, Hale's law
```

### Conceptual Summary
- **Latent Buoyancy & Gauge Fixing**: The emergence rate is governed by an unobserved toroidal field $B(|\lambda|, s)$ via the emission function $\Lambda = c \cdot \text{softplus}(B - B_{\text{crit}})$. To break gauge degeneracy between field amplitude and threshold, we fix $B_{\text{crit}} = 1$ and $\alpha = 1$, letting $c$ act as a global scaling factor. Sub-threshold fields ($B < 1$) produce true zero emergences, naturally capturing grand minima like the Maunder minimum.
- **2D Intensity & Quadrature**: $\Lambda(|\lambda|, s)$ has units of events/(deg $\cdot$ yr). Its 2D integral $\iint \Lambda\,d|\lambda|\,ds$ yields the expected total event count for the cycle. Raw 1D and 2D likelihoods cannot be directly compared due to differing base measures and dimensions.
- **Hierarchical Modeling (Partial Pooling)**: Across 18 development cycles, the spatial-temporal belt shape parameters are shared to prevent overfitting on data-sparse cycles, while cycle-specific timing shifts $t_{0,k}$ and amplitudes $A_k$ are retained.
- **Out-of-Sample Evaluation**: In leave-one-cycle-out (LOCO) cross-validation, alignment $t_0$ for test cycles must be derived strictly without peeking at test events to prevent data leakage.
- **Belt Width Scaling**: Evaluated against constant-width, latitude-dependent, and amplitude-dependent formulations to test whether stronger cycles feature broader latitudinal emergence profiles.
