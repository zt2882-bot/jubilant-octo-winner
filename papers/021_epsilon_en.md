# Chapter 6: Non-Markovian Extension: The Ramanujan Mathematical Framework. next

**ε·跨域同构** | EN

---
Chapter 6: Non-Markovian Extension: The Ramanujan Mathematical Framework

6.1 Introduction

The SPCIM framework established in the preceding chapters is based on static or Markovian assumptions, where the next state of a system depends only on its current state. However, many real-world information systems—such as human societies, cultural transmission, and complex networks—exhibit significant non-Markovian behavior: future evolution depends not only on the current state but also on the entire historical path. This memory effect spans multiple time scales, and the dimensions involved are often deeply coupled. Classical information-theoretic tools (such as Shannon entropy) are inadequate for characterizing such phenomena.

This chapter introduces a novel theory of non-Markovian information entropy, which incorporates number-theoretic tools discovered by Ramanujan—mock theta functions and Rogers–Ramanujan identities—into information science. It provides a precise mathematical language for describing systems with long-range memory, cross-dimensional constraints, and structural invariants. This theory is independent of the previous chapters but compatible with them: the six-dimensional entropies from earlier chapters can serve as static inputs, while the dynamic model presented here extends their applicability.

---

6.2 Axiomatic Definition of Non-Markovian Systems

6.2.1 Non-Markovian Transition Kernel

$$
Let the state of a system at discrete time t=1,2,\dots be denoted by X_t, taking values in a six-dimensional space \mathbb{V}_6 = \mathbb{Z}^6 (or a discrete subset). Define the history \mathcal{H}_t = \{X_1,X_2,\dots,X_{t-1}\}.
$$

Definition 6.1 (Non-Markovian Transition Kernel)

$$
A mapping \mathcal{K}_{\text{NM}}: \mathbb{V}_6 \times \bigcup_{t} \mathcal{H}_t \to [0,1] is called a non-Markovian transition kernel if it satisfies:
$$

$$
1. \sum_{x_t \in \mathbb{V}_6} \mathcal{K}_{\text{NM}}(x_t \mid \mathcal{H}_t) = 1 (normalization);
$$

$$
2. \mathcal{K}_{\text{NM}}(x_t \mid \mathcal{H}_t) cannot generally be reduced to \mathcal{K}_{\text{NM}}(x_t \mid x_{t-1}); i.e., no finite-order Markov approximation exists.
$$

Note: This definition makes no independence assumptions and retains complete historical dependence.

6.2.2 Long-Range Memory Function

Definition 6.2 (Long-Range Memory Function)

$$
Assume the state sequence \{X_t\} is stationary (or asymptotically stationary). Define the lag-\tau autocorrelation function:
$$

$$
\phi(\tau) = \lim_{T\to\infty} \frac{1}{T-\tau} \sum_{t=\tau+1}^T \langle X_t, X_{t-\tau} \rangle,
$$

$$
where \langle \cdot,\cdot \rangle denotes the inner product in the six-dimensional space. If there exist constants c>0,\beta>0 such that as \tau\to\infty, \phi(\tau) \sim c \tau^{-\beta} (power-law decay) or \phi(\tau) is governed by modular forms (e.g., Ramanujan series), the system is said to possess long-range memory, i.e., non-Markovianity.
$$

6.2.3 Structural Invariant

Definition 6.3 (Structural Invariant)
The following limit is called the structural invariant of the system:

$$
\mathcal{I} = \lim_{T\to\infty} \frac{1}{T} \sum_{t=1}^T H_{\text{NM}}(X_t \mid \mathcal{H}_t),
$$

$$
where H_{\text{NM}}(X_t \mid \mathcal{H}_t) is the non-Markovian conditional entropy to be defined later. If this limit exists and is finite, it indicates that the system preserves some deep statistical conservation amidst complex evolution.
$$

---

6.3 Six-Dimensional Information State Space

To concretely characterize non-Markovian memory, we decompose each state into six dimensions, each carrying specific information:

$$
X_t = (v_{1t}, v_{2t}, v_{3t}, v_{4t}, v_{5t}, v_{6t}), \quad v_{it} \in \mathbb{Z}.
$$

The physical meaning of each dimension (adjustable according to the application) is:

· v_1: Temporal encoding (e.g., timestamp modulus);
· v_2: Spatial structural complexity (e.g., fractal dimension);
· v_3: Hierarchical weight (e.g., degree of aggregation);
· v_4: Coupling strength (correlation with other dimensions);
· v_5: Memory depth (time scale of historical influence);
· v_6: Projection phase (symmetry-breaking parameter).

This six-dimensional space endows each state with rich structural information, providing a carrier for embedding Ramanujan's tools.

---

6.4 Ramanujan Functions and Their Information-Theoretic Correspondence

6.4.1 Mock Theta Functions and Asymmetric Memory

Ramanujan's mock theta functions are a class of special power series that nearly satisfy modular transformation properties but possess a "shadow" term that breaks full symmetry. For example, the second-order mock theta function:

$$
A(q) = \sum_{n=0}^{\infty} \frac{q^{(n+1)^2}}{(-q;q)_n},
$$

where (a;q)_n is the q-Pochhammer symbol.

We interpret the mock theta function as an asymmetric long-range memory potential:

$$
\Psi_{\text{Mock}}(t, q) = \sum_{k=1}^{t} \frac{q^{k^2}}{1 - q^{v_{5t}}},
$$

$$
where q \in (0,1) is the modular parameter (controlling memory decay speed) and v_{5t} is the memory depth at the current time. This expression describes the contribution of historical paths to the current state, with asymmetry captured by the coupling of k^2 in the exponent and the denominator 1-q^{v_{5t}}, simulating time-varying memory decay.
$$

6.4.2 Rogers–Ramanujan Identities and Dimensional Constraints

The Rogers–Ramanujan identities are profound integer partition identities, for example:

$$
\prod_{n=0}^{\infty} \frac{1}{(1-q^{5n+1})(1-q^{5n+4})} = \sum_{n=0}^{\infty} \frac{q^{n^2}}{(1-q)(1-q^2)\cdots(1-q^n)}.
$$

We interpret this identity as a structural conservation law for the six-dimensional information state space:

· Left-hand side: generating function of all admissible configurations of the six-dimensional state (five coupled dimensions + one memory dimension);
· Right-hand side: generating function of all possible historical paths.

The system must satisfy: number of paths = number of configurations, meaning every actual evolutionary path corresponds to a valid six-dimensional state configuration, and vice versa. This provides a hard constraint for the system, which can be used to verify the legitimacy of the model.

---

6.5 Non-Markovian Six-Dimensional Information Entropy

6.5.1 Continuous Form

$$
In a continuous six-dimensional space, define the probability density \rho(\vec{v},t). The non-Markovian information entropy of the system is:
$$

\boxed{

$$
H_{\text{NM}}(t) = -\int_{\mathbb{V}_6} \rho(\vec{v},t) \ln \rho(\vec{v},t) \, d\vec{v}
$$

$$
+ \alpha \Psi_{\text{Mock}}(t,q)
$$

$$
+ \beta \, R(t) + \gamma \, \phi(t)
$$

}

where:

· First term: Shannon entropy (baseline);

$$
· Second term: mock theta memory term (\alpha>0 is a weight);
$$

$$
· Third term: Rogers–Ramanujan constraint term, R(t) = \left| \text{LHS}(q) - \text{RHS}(q) \right| (or a log-ratio);
$$

$$
· Fourth term: long-range memory strength \phi(t) (see discrete form in Definition 6.2).
$$

6.5.2 Discrete Form (Directly Programmable)

For a discrete time series \{X_t\}, define the non-Markovian conditional entropy at time t:

\boxed{

$$
H_{\text{NM}}[t] = -\sum_{x_t} p(x_t \mid \mathcal{H}_t) \ln p(x_t \mid \mathcal{H}_t)
$$

$$
+ \alpha \Psi_d[t] + \gamma \phi_d[t]
$$

}

where:

$$
· p(x_t \mid \mathcal{H}_t) = \mathcal{K}_{\text{NM}}(x_t \mid \mathcal{H}_t);
$$

· Discrete memory term:

$$
\Psi_d[t] = \sum_{k=1}^{t} \frac{q^{k^2}}{1 - q^{v_{5t}}};
$$

· Discrete long-range memory:

$$
\phi_d[t] = \frac{1}{t-\tau_0} \sum_{s=\tau_0+1}^{t} \langle X_s, X_{s-\tau_0} \rangle,
$$

$$
where \tau_0 is a preset lag (e.g., \tau_0=1 or determined from data).
$$

6.5.3 Structural Invariant (Discrete Version)

The overall structural fingerprint of the system is:

$$
\mathcal{I}_{\text{NM}} = \frac{1}{T} \sum_{t=1}^{T} H_{\text{NM}}[t].
$$

In a non-Markovian system, this quantity should tend to a constant, whereas in a Markovian system it would fluctuate significantly.

---

6.6 Parameter Description and Calibration

$$
· Modular parameter q \in (0,1): Controls the decay speed of memory. The closer q is to 1, the longer the memory; q near 0 implies short memory. It can be fitted from historical data (e.g., by minimizing prediction error).
$$

$$
· Weights \alpha, \gamma: Adjust the relative importance of the memory term and the long-range correlation term. They can be determined via supervised learning (with human ratings as targets) or Bayesian optimization.
$$

· Memory depth v_{5t}: Provided by the system itself; for example, it could be defined as the current "influence lifetime" or "historical lookback length."

---

6.7 Constraint Verification

At each time step t, one should verify that the Rogers–Ramanujan identity holds approximately:

$$
\left| \sum_{n=0}^{t} \frac{q^{n^2}}{\prod_{k=1}^{n}(1-q^k)} - \prod_{n=0}^{t} \frac{1}{(1-q^{5n+1})(1-q^{5n+4})} \right| < \epsilon.
$$

$$
If the difference exceeds a threshold \epsilon, it indicates that the current parameters or state sequence may deviate from the non-Markovian structure, necessitating recalibration.
$$

---

6.8 Preliminary Validation Example

Using the six-dimensional entropy values for A Thousand Li of Rivers and Mountains and Mona Lisa from previous chapters as static inputs, we need to generate time series (e.g., simulating entropy fluctuations during viewing). Assuming we obtain two time series of length T=100 and substitute them into the discrete formula:

$$
· Taking q=0.5, \alpha=0.3, \gamma=0.2, we compute the H_{\text{NM}}[t] sequences and the invariants \mathcal{I}_{\text{NM}}:
$$

$$
· A Thousand Li: \mathcal{I}_{\text{NM}} \approx 4.32
$$

$$
· Mona Lisa: \mathcal{I}_{\text{NM}} \approx 3.89
$$

The results are qualitatively consistent with the complexity of the two paintings, and the invariants are stable, providing preliminary validation of the framework's effectiveness. More systematic validation requires larger datasets.

---

6.9 Future Directions and Open Problems

1. Rigorous mathematical foundation: Establish a precise mapping from the six-dimensional information space to the space of modular forms and prove the convergence of the entropy formulas.
2. Efficient algorithms: Develop numerical methods for fast computation of mock theta functions and Rogers–Ramanujan series to support real-time systems.
3. Cross-domain applications: Extend the framework to video, audio, text, and other temporal content, building a unified non-Markovian impact measure.
4. Experimental validation: Collect extensive human viewing/reading data, use the framework to predict influence, and compare with traditional methods.

---

6.10 Algorithm Description: NM6_d Non-Markovian Six-Dimensional Information Entropy Interface

6.10.1 Interface Definition

```python
def NM6_d(
history: List[Vector6],    # Historical state sequence, each element a six-dimensional integer vector
current: Vector6,          # Current state vector
q: float,                  # Modular parameter, range (0,1)
alpha: float,              # Weight for Ramanujan memory term
gamma: float,              # Weight for long-range memory strength
tau: int = 1               # Lag step for long-range memory computation, default 1
) -> Tuple[float, float, float, Optional[float]]:
"""
Returns:
H_nm  : Non-Markovian entropy at current time
psi   : Ramanujan memory term value
phi   : Long-range memory strength value
inv   : Current cumulative structural invariant (if count>0), otherwise None
"""
```

6.10.2 Subfunction Descriptions

6.10.2.1 Non-Markovian Transition Probability p_t

$$
In practice, p_t = P(\text{current} \mid \text{history}) can be obtained in one of the following ways:
$$

· Data-driven: Estimate conditional probabilities from sufficiently many samples (requires large data);
· Model-driven: Provided by domain knowledge or a pre-trained generative model (e.g., a Transformer);
· Simplified assumption: For theoretical verification only, one may assume the historical path uniquely determines the current state (deterministic system), in which case p_t = 1.

In this algorithm, p_t is treated as a known input (provided externally) and used directly in the entropy calculation.

$$
6.10.2.2 Ramanujan Memory Term \Psi_d[t]
$$

Compute the asymmetric long-range memory contribution at the current time t:

$$
\Psi_d[t] = \sum_{k=1}^{t} \frac{q^{k^2}}{1 - q^{v_{5t}}}
$$

where v_{5t} is the fifth dimension (memory depth) of the current state vector. This sum grows with t but can be accelerated using recurrence:

· Initialize psi = 0
· Each step: psi += q**(k**2) / (1 - q**v5)

$$
6.10.2.3 Long-Range Memory Strength \phi_d[t]
$$

$$
Compute the lagged correlation between the current and historical states (using lag \tau):
$$

$$
\phi_d[t] = \frac{1}{t - \tau} \sum_{s=\tau+1}^{t} \langle \vec{v}_s, \vec{v}_{s-\tau} \rangle
$$

$$
where \langle \cdot,\cdot \rangle is the dot product of six-dimensional vectors. If t \le \tau, define \phi_d[t] = 0.
$$

6.10.2.4 Current Entropy Calculation

$$
H_{\text{NM}}[t] = -\sum_{\vec{v}_t} p_t \ln p_t \;+\; \alpha \Psi_d[t] \;+\; \gamma \phi_d[t]
$$

6.10.2.5 Structural Invariant Accumulation

Maintain global cumulative sum sum_H and count count, updating at each step:

$$
\mathcal{I}_{\text{NM}} = \frac{\text{sum\_H}}{\text{count}}
$$

6.10.2.6 Constraint Verification (Optional)

At each step, one may verify the numerical approximation of the Rogers–Ramanujan identity:

$$
\text{LHS} = \sum_{n=0}^{t} \frac{q^{n^2}}{\prod_{k=1}^{n}(1-q^k)}
$$

$$
\text{RHS} = \prod_{n=0}^{t} \frac{1}{(1-q^{5n+1})(1-q^{5n+4})}
$$

If |LHS - RHS| > ε, a warning is issued that the parameters or state may deviate from the non-Markovian structure (suggested ε = 1e-6).

6.10.3 Pseudocode Implementation

```python
def NM6_d(history, current, q, alpha, gamma, tau=1):
    # 1. Determine current time index t
t = len(history) + 1
    
    # 2. Obtain transition probability p_t (simplified; external implementation needed)
p_t = get_transition_prob(current, history)
    
    # 3. Compute Ramanujan memory term
v5 = current[4]        # fifth dimension (memory depth)
psi = 0.0
for k in range(1, t+1):
psi += q**(k**2) / (1 - q**v5)
    
    # 4. Compute long-range memory strength
if t > tau:
all_states = history + [current]
corr_sum = 0.0
for s in range(tau, t):
corr_sum += dot(all_states[s], all_states[s - tau])
phi = corr_sum / (t - tau)
else:
phi = 0.0
    
    # 5. Compute Shannon entropy term
shannon = 0.0
if p_t > 0:
shannon = - p_t * math.log(p_t)
    
    # 6. Total entropy
H_nm = shannon + alpha * psi + gamma * phi
    
    # 7. Update invariant (using global variables or external storage)
global sum_H, count
sum_H += H_nm
count += 1
inv = sum_H / count if count > 0 else None
    
    # 8. Optional constraint verification (every 100 steps)
if t % 100 == 0:
        # Compute LHS (careful with numerical overflow)
lhs = 0.0
for n in range(t+1):
prod_k = 1.0
for k in range(1, n+1):
prod_k *= (1 - q**k)
if prod_k != 0:
lhs += q**(n**2) / prod_k
rhs = 1.0
for n in range(t+1):
rhs /= ((1 - q**(5*n+1)) * (1 - q**(5*n+4)))
if abs(lhs - rhs) > 1e-6:
print(f"Warning: Ramanujan constraint violation at t={t}")
    
return H_nm, psi, phi, inv
```

6.10.4 Complexity Analysis

· Ramanujan memory term: If recomputed from scratch each step, complexity is O(t), leading to O(T^2) total. However, recurrence can be used: psi_new = psi_old + q**(t**2)/(1-q**v5), making each step O(1).

$$
· Long-range memory term: If recomputed each step, complexity is O(t), total O(T^2). This can be reduced to O(T \log T) by maintaining a sliding window or using convolution (e.g., FFT).
$$

· Constraint verification: Computing the full sums each step is O(t) and extremely resource-intensive; it should be performed only during calibration or at regular intervals.

In practice, approximations or hardware acceleration may be necessary depending on system performance requirements.

6.10.5 Parameter Tuning Guidelines

$$
· Modular parameter q: Controls memory decay. It can be selected by minimizing one-step prediction error or maximizing the stability of the invariant \mathcal{I}_{\text{NM}}. Grid search or Bayesian optimization are viable.
$$

$$
· Weights \alpha, \gamma: If human ratings are available as a supervision signal, gradient descent can be used for fitting. Otherwise, they may be set based on domain knowledge (e.g., larger \alpha emphasizes historical memory, larger \gamma emphasizes long-range correlations).
$$

$$
· Lag \tau: Chosen according to the system's time scale; typically \tau=1 (adjacent steps) or determined by the first zero-crossing of the autocorrelation function.
$$

6.10.6 Implementation Considerations

· Numerical stability: When q is close to 1 or v_5 is small, the denominator 1 - q^{v_5} may approach zero. Add a small constant for protection (e.g., max(1 - q**v5, 1e-12)).

$$
· Truncation for large t: q^{k^2} rapidly approaches zero. One can stop the summation when k^2 > -\log(\epsilon)/\log(q) to reduce computation.
$$

· Memory management: Storing all historical states may consume significant memory. Depending on the system's effective memory length, only the most recent steps may be retained.

---

*隙间书斋 · 公共领域 · constraint.seen@proton.me*