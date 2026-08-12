# Time and Fact: The Emergent Foundation of “Fact” in Distributed Systems from the Perspective of NTP

**#65** | EN | 时间事实

---

# Time and Fact: The Emergent Foundation of “Fact” in Distributed Systems from the Perspective of NTP

## —— On Mills’ Design Philosophy and the Ten Laws of Fact Systems

## Abstract

In distributed systems, the establishment of “facts” often relies on some form of consensus or authority. However, the Network Time Protocol (NTP) — the fundamental time synchronization protocol of the Internet — embodies a radically different philosophy: it does not claim “what time it is”, but instead lets temporal facts emerge from statistical noise through continuous falsification and window overlap. This paper analyzes the core design ideas of David L. Mills, the inventor of NTP — time windows, continuous falsification, parallel worlds, gradual constraints, and state machine ethics — and proposes the “Ten Laws of Fact Systems”. It demonstrates that time is not an atomic point but a window of uncertainty; facts are not “declared” but “survived”. The time window, as a coordinate for fact, is the only physical ground on which a distributed system can legitimately “stop asking” in an uncertain world. These insights have fundamental implications for consensus algorithms and the trust infrastructure of digital society.

**Keywords**: NTP; David L. Mills; time window; fact emergence; continuous falsification; Ten Laws of Fact Systems

## 1. Introduction: The Ubiquity of Time Fields in Protocols

From IP TTL, TCP timestamps, HTTP Date headers, to TLS certificate validity periods and NTP timestamps, nearly every protocol explicitly or implicitly depends on time. Yet almost none model time as a first-class citizen — they assume time is monotonic, comparable, and globally approximately consistent, and use it to prune state space, approximate consistency, and turn undecidable problems into “expiration problems”.

This hidden dependency reveals a deeper engineering fact: protocol designers did not add time fields because they understood time’s essence, but because when other variables (identity, order, state, trust) may fail, time is the last physical anchor they can rely on. In the words of an engineer: “I don’t know who is right, but I know when to give up.”

This paper dissects NTP to uncover its hidden design philosophy: **time is not a point but a window; fact is not proved but survived**. From this, we derive fundamental questions about how “facts” can hold in distributed systems.

## 2. Mills’ Core Design Ideas for NTP

David L. Mills (1938–2024), inventor of NTP and early Internet architect, embedded his design philosophy not only in algorithms but also in structural choices. The following five points form the essence of NTP as a “fact system” rather than a mere “time service”.

### 2.1 Time Modeled as an “Event Window”, Not a Point

Mills fundamentally rejected instantaneous time. Time is represented as an interval with bounded uncertainty, captured by four quantities: offset θ, delay δ, dispersion ε, jitter ψ. The system does not output “what time it is”, but “the verifiable window within which now lies”. This acknowledges a basic physical fact: there are no instantaneous events in networks; one can only observe events occurring over a period of time.

### 2.2 Facts Survive Through Continuous Falsification, Not by Voting

The clock selection algorithm (Section 3 of RFC 5905) embodies Popperian falsificationism. The system does not search for the “most accurate time”; it continuously eliminates interpretations that cannot coexist. In each round, it asks: which time sources still have overlapping windows with the surviving set? Rejected nodes (falsetickers) are not punished, merely “no longer used”. **A fact is an interpretation that has not yet been falsified and remains in the survivor set**.

### 2.3 Parallel Worlds Are Allowed to Coexist

Through clustering, NTP permits multiple self-consistent time clusters to exist simultaneously. Each cluster is a local temporal reality. The system does not force merger; it only states: “given current evidence, I can only act within this intersection”. This is an extremely restrained ontological stance — acknowledging uncertainty as part of the system, not as noise to be eliminated.

### 2.4 Belief Must Be Constrained by a State Machine: Ignorance and “Being Wrong” Are Legitimate States

NTP’s state machine (Section 4) defines states: INIT (ignorance), SYNC (suspicion), SPIK (being wrong), FREQ (slow correction). Mills deliberately designed a path of degradation — the system can legitimately return to ignorance or suspicion, never forced to remain “confident”. This prevents premature belief and preserves continuous doubt.

### 2.5 Action Rate Must Be Ethically Constrained: Better to Be Slowly Wrong Than Abruptly Right

The clock discipline algorithm (Section 5) strictly limits the rate of time adjustment; stepping is prohibited unless error exceeds a panic threshold. Mills expressed a deep engineering ethic: in an uncertain world, the rate of change of system behavior must be slower than noise. Fast convergence invites manipulation; slow adjustment respects the physical world.

## 3. The Ten Laws of Fact Systems: A Design Paradigm Abstracted from NTP

Based on Mills’ design ideas, we abstract the essence of NTP Sections 2–5 and its appendices into a set of **design principles for fact systems**, called the “Ten Laws of Fact Systems”. These laws are not limited to time synchronization but are applicable to any distributed system that needs “facts to emerge”.

**Law 1 – Fact Is an Interval, Not a Point**  
Every fact must carry uncertainty. A claim without error is not credible. Point values are for presentation, not decision.

**Law 2 – Facts Can Only Be Falsified, Never Proven**  
The system’s job is not to find truth, but to eliminate impossibility. Use intersection, not averaging. Retain multiple worlds. Error is not the enemy; stable error is.

**Law 3 – Facts Must Allow Parallel Worlds**  
Multiple contradictory factual claims coexisting is a healthy state. Conflict ≠ failure, agreement ≠ correctness. A system without divergence is lying.

**Law 4 – A Fact System Must Be Slower Than Noise**  
Response speed must not exceed the rate of world change. Low-bandwidth feedback, history weighting over immediacy, stability over precision. Speed is the signature of illusion engineering.

**Law 5 – Facts Must Be Exposed Through Long-Term Behavior**  
A single correct instance means nothing. Credibility comes from temporal dimension; nodes are selected by history. All trust decays. No permanent trust.

**Law 6 – A Fact System Must Oppose Structural Symmetry**  
Perfectly symmetric systems inevitably resonate. Deliberately create asymmetric roles, different rhythms, and diverse perspectives. Irregularity is a safety feature.

**Law 7 – A Fact System Cannot Possess Authoritative Nodes**  
Authority is the enemy of fact. There is no final arbiter, no irreplaceable node. Hierarchy is only a reference, not a command. Authority kills fact.

**Law 8 – A Fact System Must Be Auditable by Bystanders**  
Opacity is untrustworthy. Expose “why we believe” rather than “what we believe”. Management interfaces are observation interfaces. Trust comes from observability, not declarations.

**Law 9 – A Fact System Must Have the Right to Refuse and to Crash**  
Refusing to act is more important than acting wrongly. KoD (refuse to answer), Panic (admit failure), stop pretending to be correct. Self-doubt is an advanced capability.

**Law 10 – A Fact System Must Leave Room for the Future**  
Completion is death. No final state, no encapsulation of thought, no blocking of evolutionary paths. The system’s mission is to “continue to exist”, not “prove itself”.

## 4. The Epistemological Foundation of NTP: Time as an Event Window

### 4.1 From Point Time to Window Time

NTP models time as an interval with bounded uncertainty, not a point. It does not require timestamps of different nodes to be numerically equal; it only requires:
[

$$
\text{Window}_A \cap \text{Window}_B \neq \emptyset
$$

]
If two windows intersect, the system considers their views of “current time” compatible. This is an epistemological minimal consensus: not numerical equality, but non-contradiction.

This principle is later formalized as the “intersection interval” algorithm, the core of NTP clock selection: no averaging, no voting, only seeking the largest consistent intersection. Nodes that cannot overlap with the majority are called “falsetickers” — they are not punished, only no longer used.

### 4.2 Window Overlap as Consensus

NTP does not require equal timestamps; it only requires overlapping windows. The intersection interval algorithm embodies this: no voting, no averaging, only maximizing consistent overlap. Falsetickers are simply discarded.

## 5. The Emergence of Facts: Continuous Falsification and Parallel Worlds

### 5.1 Facts Are Not Proved, but Not Yet Falsified

Section 3 of NTP (Clock Selection Algorithm) embodies Popperian falsification. The system never asks “which time source is correct”, but “which sources have already been eliminated by existing evidence”. Those not yet eliminated temporarily survive as “facts”.

This is isomorphic to the philosophy of science: “truth is not verified but not yet falsified”. NTP continuously introduces new observations and eliminates false time sources inconsistent with the current survivor window. Thus, **“now” in NTP is not an objective point, but a constantly recomputed, revocable survivor set**.

### 5.2 The Legitimate Existence of Parallel Worlds

NTP’s clustering algorithm allows multiple self-consistent time clusters (clusters) to coexist. Each cluster is an internally consistent temporal world. The system does not force their merger; it only says: “given current evidence, I can only act within this intersection”. Different worlds can persist until sufficient evidence naturally collapses them.

This acknowledges that **under insufficient evidence, multiple mutually exclusive interpretations can rationally coexist**. This is not an engineering flaw but a respect for physical uncertainty.

### 5.3 Consequence of Removing Falsification: From Fact System to Illusion System

If continuous falsification is removed, NTP degenerates into a time broadcast system: a few authoritative nodes declare time, others passively accept. This “declarative certainty” appears more precise but eliminates the system’s capacity for self-doubt. Once authorities err, the entire system systematically lies. This is the inner contradiction of Google TrueTime: it uses engineering violence to compress uncertainty but loses NTP’s ethical grounding of “preferring not to answer than to pretend to know”.

## 6. The Time Window as a Coordinate for Facts

### 6.1 The Right to Define Facts Belongs to Structure, Not to Agents

In NTP’s worldview, facts are not “declared” by any agent, but “emerge” through structural constraints. Each node only outputs “roughly which window I am relative to you”; no one knows absolute time. Yet through mutual constraints and continuous falsification, a stable time scale emerges.

This resembles the emergence of “temperature” in statistical physics: no molecule knows the temperature, yet the system has a temperature. **Facts are not computed; they are structural states that survive.**

### 6.2 Time as a Legitimate Basis for “Giving Up”

In highly complex, asynchronous distributed systems, the system often faces undecidable situations: does the other party already know? Is the state still valid? Is it worth continuing computation? Without ontological constraints, the system can only guess — leading to retries, rollbacks, races, replays — all exchanging computation for uncertainty.

NTP introduces a highly restrained mechanism: **giving the system a legitimate reason to stop when it cannot judge**. Its panic threshold, dispersion growth, and KoD messages are designed for “stopping”. Time is the only variable that can serve as a basis for “giving up” without breaking system legitimacy — because time is irreversible, one-way, and naturally ignorable.

## 7. Comparison with Existing Time Philosophies

### 7.1 Physical Time vs. Engineering Time

Newtonian and Einsteinian time are objective reference frames, but the Internet does not satisfy the premise of “trustworthy measurement and clear reference frame”. NTP adopts a **system-theoretic view of time**: time is not an object of measurement but a constraint variable introduced by the system to manage uncertainty.

### 7.2 Logical Time vs. Physical Time

Lamport’s logical clocks and vector clocks care only about causal order, not “what time it is”. They are not grounded — cannot align with the real world, cannot be used for certificate validation or financial auditing. NTP’s window time lies in between: it provides weak alignment with physical reality, at the cost of absolute precision.

### 7.3 The Paradox of TrueTime

TrueTime uses GPS + atomic clocks to compress uncertainty into a very small interval, but it is essentially **an operable illusion**: it does not answer “what is the real time”, only “the earliest time the system is willing to vouch for”. Its ε (error interval) is an engineering commitment, not a structural necessity. Once GPS fails or atomic clocks malfunction, the system suspends commits rather than degrades — preserving honesty but losing the vitality of NTP that “still emerges order amid chaos”.

## 8. Conclusion: Time as the Ground of Fact

NTP’s greatness is not its accuracy, but that it **never pretends to know the truth, yet lets truth naturally emerge**. Through event windows, continuous falsification, and coexistence of parallel worlds, it builds a runnable philosophy of fact: facts are structures that survive, not declarations of power.

The Ten Laws of Fact Systems refine this philosophy into a transferable design paradigm: facts must be modeled as intervals, falsifiable, allow parallel worlds, be slower than noise, exposed through long-term behavior, oppose symmetry, reject authority, be auditable, have the right to refuse and crash, and leave room for the future.

These laws have fundamental implications for the trust infrastructure of digital society:
- Consensus should not be based on voting on “who is more correct”, but on the structure of “which interpretations have not yet been falsified”.
- Systems should retain the right to say “I don’t know” and treat it as a healthy state, not a failure.
- The only legitimate ground for “giving up judgment” is the irreversibility and one‑way nature of physical time.

In an era of exploding system scale and autonomous AI agents, people will have to rediscover the answer that NTP already wrote: **Facts do not need to be invented; they only need to stand under conditions where they cannot be overturned.** And time is the last line that allows the world to “stop asking”.

## References

[1] Mills, D. L. (2010). *RFC 5905: Network Time Protocol Version 4: Protocol and Algorithms Specification*.  
[2] Mills, D. L. (1991). *Internet Time Synchronization: The Network Time Protocol*.  
[3] Mills, D. L. (2011). *Computer Network Time Synchronization: The Network Time Protocol on Earth and in Space*.  
[4] Popper, K. (1934). *The Logic of Scientific Discovery*.  
[5] Lamport, L. (1978). Time, clocks, and the ordering of events in a distributed system. *Communications of the ACM*, 21(7), 558–565.  
[6] Corbett, J. C., et al. (2012). Spanner: Google’s globally-distributed database. *OSDI*.  
[7] Ten Laws of Fact Systems (abstracted from RFC 5905 Sections 2–5 and appendices).

---

*隙间书斋 · 公共领域 · constraint.seen@proton.me*