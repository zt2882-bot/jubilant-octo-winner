# The Perception-First Axiom: Formalization and Cross-Domain Validation

**Perception & Physics** | EN

---

# The Perception-First Axiom: Formalization and Cross-Domain Validation

> Gap Library · Public Domain | Preprint · 2026-07-19

---

## Abstract

This paper proposes and formalizes the **Perception-First Axiom**: in high-dynamic, high-dimensional systems, a *sensing* approach that passively exploits pre-existing physical constraints is necessarily more information-efficient than a *surveying* approach that imposes active measurement. We validate the universality of this axiom across eight independent domains — quantum mechanics (Bell inequalities), autonomous driving (Tesla vs Waymo), underwater vision (Wat3R vs sonar), compound-eye biology (mantis shrimp vs human vision), chiral chemical detection (calcite crystal faces vs HPLC), financial markets (free markets vs unified quantitative models), the immune system (multi-antigen weak recognition vs CAR-T), and social policy (local pilots vs central planning). On this basis, we derive an actionable engineering criterion for diagnosing whether any information-acquisition system has fallen into the **measurement autophagy loop**.

---

## 1. The Axiom

**Perception-First Axiom**:

> In any high-dynamic, high-dimensional physical system, the optimal information-acquisition strategy is to "go with the flow" — using the system's pre-existing ontological constraints as the channel for processing information — rather than "imposing constraints" — extracting information by actively injecting additional measurement constraints.

**Equivalent formulations**:

- Let the photons' flight trajectories themselves perform the ranging, rather than firing lasers to measure distance.
- Let the molecules' chiral preferences themselves perform the separation, rather than using chemical reagents to sort them.
- Let the market's free trades themselves perform the pricing, rather than having a model compute it.

**Mathematical formulation**: let the system's information efficiency be $E = \frac{\text{useful information output}}{\text{total resource consumption}}$. There exists a critical dynamic parameter $D_{crit}$ such that when the system's dynamicity $D > D_{crit}$:

$$E(\text{sensing}) > E(\text{surveying})$$

and the gap $\Delta E = E_{sense} - E_{measure}$ increases monotonically with $D$.

---

## 2. Validation Across Eight Domains

### 2.1 Quantum Mechanics

The Bell inequality experiments (Aspect, 1982) ruled out local hidden-variable theories. Measurement does not "reveal" a pre-existing value — the act of measurement itself changes the system. Quantum systems therefore cannot be described by the classical surveying paradigm. The success of the Feynman path integral lies precisely in this: it does not measure a particle's specific trajectory — it computes the probability amplitude superposition over all possible paths. This is the sensing paradigm — it does not ask "where is the particle," it only computes the probability space.

### 2.2 Autonomous Driving

| | Tesla (sensing) | Waymo (surveying) |
|---|---|---|
| Sensors | 8 cameras, passive reception | LiDAR, active emission |
| Hardware cost | ~$300 | ~$100,000 |
| Compute allocation | sensing + decision | 90% point-cloud denoising |
| Data flywheel | 6M vehicles, real-time | hundreds + simulation |

Waymo's LiDAR produces terabytes of point-cloud data per hour, most of it ground reflections, raindrop scattering, and dust echoes. This is exactly the "measurement autophagy loop": the more precisely you measure → the more noise → the greater the compute demand → the more complex the denoising algorithms.

### 2.3 Underwater 3D Reconstruction

Wat3R pure-vision multi-view versus underwater sonar point-by-point measurement. Sonar faces the same autophagy problem of multi-reflection noise superposition.

### 2.4 Compound-Eye Biology

The mantis shrimp's 12 photoreceptor types do not compare against each other — they directly look up recognition from a table. A tiny brain processes 4× the input of humans. Humans spend massive cortical resources on color comparison, in exchange for 5nm resolution precision — but at the cost of huge latency and energy. Each is optimal in its own ecological niche.

### 2.5 Chiral Chemical Detection

HPLC chiral-column separation — each separated peak = one measurement, and baseline drift = autophagy noise. A calcite crystal face directly queues the L/D molecules — the crystal face's chiral structure is itself an "ontological constraint," letting a constraint that already exists in nature perform the separation.

### 2.6 Financial Markets

A free market = a natural compound eye of millions of traders. A unified quantitative model = the surveying school — attempting to use one model to "measure" the market. The collapse of Long-Term Capital Management (1998) is a perfect case of surveying autophagy: the more precise the model → the higher the leverage → the more lethal the tail events the model failed to cover.

### 2.7 The Immune System

Antibodies are sensing units — they do not "understand" antigen structure, they only perform pattern matching. CAR-T is the surveying school — forcing one receptor to recognize one antigen → off-target effects + cytokine storms. Multi-target weak-binding approaches (compound-eye immune arrays) are under active research.

### 2.8 Social Policy

Central planning's "five unifications" = the surveying school — attempting to precisely measure all demand and precisely allocate all resources. It failed systematically (the Soviet Union, the Great Leap Forward). Multi-probe local pilots (the Shenzhen model) = the sensing school — each tries, each adjusts, no unification, probabilistic coupling.

---

## 3. Diagnostic Criteria for the Measurement Autophagy Loop

**Criterion 1**: if more than 50% of a system's total resources are consumed on "filtering / denoising / error-correction / calibration," the system has entered the autophagy zone.

**Criterion 2**: if an increase in precision is accompanied by a decrease in useful information density ($\partial(\text{SNR})/\partial(p) < 0$), autophagy has already occurred.

**Criterion 3**: if users no longer ask "is this data trustworthy" but instead ask "which version is this data" — autophagy has reached terminal stage.

---

## 4. Discussion

The Perception-First Axiom is not a negation of surveying. Surveying is effective in low-dynamic, small-form systems — Beidou geodesy, chip lithography, standard metrology. The disaster of surveying comes from extrapolating its success to high-dynamic, massive-form systems — this is precisely the paradigm revolution physics underwent from Newton to quantum mechanics. Engineering has not yet completed this paradigm shift.

---

## References

[1] A. Aspect et al., "Experimental Realization of Einstein-Podolsky-Rosen-Bohm Gedankenexperiment," Phys. Rev. Lett., 1982.
[2] A. Karpathy et al., Tesla AI Day Presentation, 2021.
[3] J. Ren et al., "Wat3R: Underwater 3D Geometry Learning without Annotations," arXiv, 2026.
[4] H. H. Thoen et al., "A Different Form of Color Vision in Mantis Shrimp," Science, 2014.
[5] R. Lowenstein, "When Genius Failed: The Rise and Fall of Long-Term Capital Management," Random House, 2000.

---

*Gap Library · Public Domain · constraint.seen@proton.me*
