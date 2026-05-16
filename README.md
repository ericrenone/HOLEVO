# HOLEVO

**No Single Probe Can Test All of Einstein's Symmetries at Once: Measurement Incompatibility in the Joint Estimation of Symmetry-Violation Couplings, and the Commutators of the Poincaré Algebra as the Irreducible Trade-Off Coefficients in TH(a,d)**

ERI Labs · Eric Ren · Jersey City, New Jersey · github.com/ericrenone

---

> "Only with the simultaneous estimation of multiple parameters are the quantum aspects of metrology fully revealed. This is due to the incompatibility of observables." — F. Albarelli, J. F. Friel, A. Datta, *Evaluating the Holevo Cramér-Rao Bound for Multiparameter Quantum Metrology*, Physical Review Letters **123**, 200503 (2019)

> "The optimal quantum measurements that correspond to different parameters may not commute and thus cannot be simultaneously implemented. Trade-offs among the estimation precisions for different parameters must be taken into consideration." — *Randomized Measurements for Multi-Parameter Quantum Metrology*, arXiv:2502.03536 (February 2025)

> "The challenge of accurately estimating multiple parameters in quantum systems stems from a fundamental incompatibility between the optimal measurements required for each parameter — a consequence of the laws governing quantum mechanics." — *Weight-Dependent and Weight-Independent Measures of Quantum Incompatibility in Multiparameter Estimation*, arXiv:2510.18864 (October 2025)

---

## Abstract

The previous document in this corpus established a single law: a test of any broken Einstein symmetry is the estimation of one coupling, and its attainable precision is bounded by the variance, in the probe, of that symmetry's generator. That law was a statement about *one* symmetry at a time. This document asks the question the law leaves open, and the answer is a no-go theorem.

The question: a real experiment does not test one symmetry in isolation. A probe state, prepared once, is in principle sensitive to *several* symmetry-violation couplings at once — a clock that tests local position invariance is also, in the same data, a potential probe of Lorentz violation; a matter-wave interferometer sensitive to spacetime smearing is also sensitive to rotational anomalies. So: can a single probe be used to test *all* of Einstein's symmetries simultaneously, each at the optimal precision the single-symmetry law allows?

The answer is no, and the obstruction is exact, structural, and — this is the wild part — already written down, three centuries ago, in the algebra of spacetime itself.

When several couplings θ₁, θ₂, … are imprinted on one probe through their respective symmetry generators G₁, G₂, …, the precision of estimating all of them jointly is *not* governed by the separate single-parameter bounds. It is governed by the **Holevo–Cramér–Rao bound**, the fundamental limit of multiparameter quantum estimation, and that bound is in general *strictly worse* than the sum of the individual bounds. The gap — the irreducible excess cost of measuring several couplings together rather than separately — is a measurement-incompatibility penalty, and it is controlled by a single quantity: the **commutators of the generators**, ⟨[Gᵢ, Gⱼ]⟩. When the generators commute, there is no penalty; the couplings can be jointly estimated at the single-symmetry optima, and one probe tests them all at once. When the generators do not commute, the penalty is non-zero, irreducible, and not removable by any choice of measurement, any amount of integration, or any cleverness of apparatus.

Now the structural fact that makes this a theorem about *physics* and not merely about metrology. The generators of Einstein's symmetries are the generators of the **Poincaré group** — the symmetry group of spacetime: time translation (the Hamiltonian H), space translation (momentum P), rotation (angular momentum J), and Lorentz boost (the boost operator K). These generators do not commute. Their commutation relations are the Poincaré algebra, and the algebra is richly non-abelian: a boost and a momentum fail to commute, returning the Hamiltonian; a boost and the Hamiltonian fail to commute, returning a momentum; a boost and a rotation fail to commute, returning a boost. Only the translations among themselves commute.

Therefore: **the structure constants of the Poincaré algebra are the measurement-incompatibility coefficients for joint tests of Einstein's symmetries.** The same commutators that make spacetime symmetry non-abelian make it impossible to optimally co-test the symmetries those generators produce. A probe optimized to test Lorentz-boost violation is, by the boost–energy commutator, necessarily *de*-optimized for testing local position invariance — and the size of that unavoidable trade-off is set by ⟨[K, H]⟩, a quantity fixed by the Poincaré algebra.

The TH(a,d) reading completes the corpus's arc. The hidden sector — ker(F) — is now not one coupling but a *vector* of symmetry-violation couplings, and the kernel has genuine multidimensional structure. The observable sector — col(F) — is the single probe. And the boundary between them is no longer a single generator but a *non-commuting set* of generators, whose failure to commute is the failure of the column space to resolve the kernel's directions independently. The corpus's inequality Var ≥ ℱ⁻¹ becomes, here, a *matrix* inequality that cannot be saturated — and the obstruction to saturation is the Poincaré algebra.

One probe cannot test all of Einstein's symmetries at once. The reason is that spacetime symmetry is non-abelian. The trade-off is not a limitation of technology; it is a theorem, and its coefficients were fixed when the Poincaré group was.

---

## Part I · The Question a Single-Symmetry Law Leaves Open

### I.1 A Thought Experiment: One Probe, Many Questions

Build the finest probe you can — an entangled ensemble of atoms, a delocalized matter wave, a state prepared with every quantum-metrological advantage. You intend to test the symmetries of Einstein's physics. You have, in front of you, one probe and a list of questions: Does the fine-structure constant depend on gravitational potential? Is Lorentz invariance exact at this energy? Is space rotationally symmetric to this precision? Does the probe's own spin couple anomalously to spacetime?

Each question, taken alone, is governed by the single-symmetry law: prepare the probe with maximal variance in that question's generator, and the attainable precision follows. But you have *one* probe, and you would like to answer *all* the questions from the *one* dataset it produces — that is what a real experiment does; it does not rebuild itself for each parameter.

Here is the trap, and it is a genuinely quantum trap with no classical analogue. The measurement that optimally extracts the local-position-invariance coupling from your probe is a specific measurement — a specific choice of what observable to read out. The measurement that optimally extracts the Lorentz-violation coupling is a *different* specific measurement. In classical estimation this would be no obstacle: you could read out everything at once, or copy the data and analyze it many ways. In quantum mechanics you cannot. A quantum measurement is a choice, and incompatible choices cannot both be made on the same system. If the optimal measurement for coupling θ₁ and the optimal measurement for coupling θ₂ do not commute, then reading one disturbs the other, and you cannot have both optima from one probe.

So the open question of the single-symmetry law is exactly this: are the optimal measurements for testing different Einstein symmetries compatible or not? If compatible, one probe tests them all. If not, there is an irreducible trade-off, and the law of the previous document — true for each symmetry alone — cannot be simultaneously realized.

### I.2 The Kernel Becomes a Vector

The TH(a,d) partition must be upgraded, and the upgrade is the content of the document.

In the single-symmetry framework the hidden sector — ker(F) — was one number: a single symmetry-violation coupling θ, zero if the symmetry holds. The kernel was one-dimensional. A one-dimensional kernel seen through one generator is the situation the quantum Cramér–Rao bound handles completely; it is saturable; the single-symmetry law is exact.

In the joint-testing framework the hidden sector is a **vector** of couplings, (θ₁, θ₂, …, θₘ), one per symmetry under test. The kernel is m-dimensional. And an m-dimensional kernel probed through m *non-commuting* generators is a fundamentally different object. The column space — the single probe — must resolve m hidden directions at once, and whether it can do so independently is decided by whether the generators that connect kernel to column space commute. The rank–nullity statement is now a statement about a *matrix*: the quantum Fisher information is a matrix, the bound on the covariance of the estimates is a matrix inequality, and matrix inequalities, unlike scalar ones, need not be saturable.

The single-symmetry law was the scalar case. This document is the matrix case, and the matrix case has an obstruction the scalar case cannot show.

---

## Part II · The Holevo Bound and the Incompatibility Penalty

### II.1 A Thought Experiment: The Cost of Asking Two Questions

Picture the joint estimation as a budget. You have one probe; you will extract from it estimates of two couplings, θ₁ and θ₂; and you measure your total error as the sum of the two variances. You want that total as small as possible.

If the two questions were *compatible* — if the optimal measurement for θ₁ and the optimal measurement for θ₂ were the same measurement, or commuting measurements — then the budget is simply additive. Each coupling is estimated at its own single-symmetry optimum, the total error is the sum of the two single-symmetry bounds, and asking two questions costs exactly as much as asking each once. One probe, both answers, no penalty.

If the two questions are *incompatible*, the budget does not add. Any measurement you choose is a compromise: tilt it toward optimal for θ₁ and it becomes suboptimal for θ₂, and vice versa. There is no measurement that is optimal for both, and so the achievable total error is *strictly greater* than the sum of the two single-symmetry bounds. The excess — the amount by which the joint cost exceeds the additive cost — is the **incompatibility penalty**. It is real, it is irreducible, and it is the price quantum mechanics charges for asking two incompatible questions of one system.

The exact accounting of this budget is the Holevo–Cramér–Rao bound. It is the tight bound on the total weighted variance of a multiparameter quantum estimate; it reduces to the sum of single-parameter bounds when the parameters are compatible; and it lies strictly above that sum when they are not. The Holevo bound *is* the budget, penalty included.

### II.2 The Penalty Is the Commutator

What sets the size of the penalty? This is the precise question, and the answer is the hinge of the entire document.

When the couplings are imprinted on the probe through generators G₁, G₂, …, the incompatibility penalty in the Holevo bound is governed by the **expectation values of the commutators of the generators**, ⟨[Gᵢ, Gⱼ]⟩, in the probe state. The structure is clean:

- If all the generators commute — every [Gᵢ, Gⱼ] = 0 — the penalty vanishes. The Holevo bound equals the sum of single-symmetry bounds. The couplings are jointly estimable at their separate optima. One probe tests them all, and the single-symmetry law of the previous document holds simultaneously for every symmetry.
- If some generators do not commute — some ⟨[Gᵢ, Gⱼ]⟩ ≠ 0 — the penalty is non-zero. The Holevo bound exceeds the additive bound. The couplings whose generators fail to commute *cannot* both be estimated at their single-symmetry optima from one probe. There is an irreducible trade-off, and ⟨[Gᵢ, Gⱼ]⟩ is its coefficient.

This is a genuine quantum effect with no classical shadow. Classically, all parameters are jointly estimable to their separate optima; there is no penalty, ever. The penalty exists only because measurements are quantum, because incompatible measurements cannot be jointly performed, and because the generators' commutator is exactly the measure of that incompatibility. The previous document's single-symmetry law lives in the world where you ask one question; this document lives in the world where you ask several, and the commutator is what separates the two worlds.

### II.3 The col(F)/ker(F) Reading

In TH(a,d) terms: the hidden sector is the vector of couplings; the column space is the one probe; and the generators are the boundary connecting them. When the generators commute, the boundary resolves the kernel's directions cleanly — each hidden coupling projects onto an independent, separately optimizable feature of the probe, and the partition behaves like m independent copies of the single-symmetry case. When the generators do not commute, the boundary *cannot* resolve the kernel's directions independently — the hidden couplings project onto features of the probe that quantum mechanics forbids reading simultaneously, and the partition acquires an irreducible cross-coupling. The commutator ⟨[Gᵢ, Gⱼ]⟩ is the off-diagonal, non-resolvable part of the boundary. It is the precise sense in which the column space fails to see the kernel as a set of independent directions. The Holevo bound is the corpus's Var ≥ ℱ⁻¹ promoted to a matrix and confronted with the fact that the matrix cannot be inverted direction-by-direction when the boundary is non-abelian.

---

## Part III · The Poincaré Algebra Is the Trade-Off

### III.1 A Thought Experiment: Reading Einstein's Symmetries Off One Crystal

Here is where the document's claim stops being abstract metrology and becomes a statement about spacetime.

The symmetries of Einstein's physics are not an arbitrary list. They are the symmetries of spacetime itself, and they form a group — the Poincaré group — whose generators are exactly four kinds of operator: the Hamiltonian H, which generates translation in time; the momentum P, which generates translation in space; the angular momentum J, which generates rotation; and the boost K, which generates the change to a uniformly moving frame. Every test of an Einstein symmetry, as the previous document established, is a test imprinted through one of these four generators. A test of local position invariance is imprinted through H. A test of Lorentz-boost invariance is imprinted through K. A test of rotational invariance is imprinted through J. A test of spatial-translation invariance is imprinted through P.

Now ask whether these four generators commute. They do not — and their failure to commute is not incidental, it is the *defining content* of the Poincaré group, the thing that makes spacetime symmetry what it is. A boost followed by a spatial translation is not the same as a spatial translation followed by a boost; the difference is a time translation. A boost followed by a time translation differs from the reverse by a spatial translation. A boost about one axis followed by a boost about another differs from the reverse by a rotation. These non-commutations are the Poincaré algebra. They are why a moving clock runs slow, why simultaneity is relative, why the symmetry group of spacetime is the intricate non-abelian object that relativity revealed.

Combine this with Part II. The incompatibility penalty for jointly testing two Einstein symmetries is set by the commutator of their generators. The commutators of the Einstein-symmetry generators are the Poincaré algebra, and the Poincaré algebra is non-abelian. Therefore the penalty is, for most pairs of Einstein symmetries, non-zero — and its coefficient is a structure constant of the Poincaré group.

### III.2 The Specific Trade-Offs

The Poincaré algebra dictates, pair by pair, which joint tests carry an irreducible penalty:

- **Lorentz-boost violation and local position invariance cannot be co-tested optimally.** Their generators are K and H, and the boost–energy commutator [K, H] is proportional to the momentum P — non-zero. A probe optimized to test Lorentz violation is, by this commutator, necessarily de-optimized for testing the position-dependence of the Hamiltonian, and conversely. The trade-off coefficient is ⟨P⟩-related — fixed by the algebra.
- **Lorentz-boost violation and spatial-translation anomalies cannot be co-tested optimally.** Their generators are K and P, and the boost–momentum commutator [K, P] is proportional to the Hamiltonian H — non-zero. The penalty coefficient is set by the probe's energy.
- **Lorentz-boost violation and rotational anomalies cannot be co-tested optimally.** Their generators are K and J, and the rotation–boost commutator [J, K] is proportional to K itself — non-zero. Boost-type tests and rotation-type tests trade off against each other.
- **Translations among themselves commute.** [P, P] = 0, and the spatial-translation generators commute with each other. Joint tests built purely on the translation sector carry *no* penalty — they are the compatible corner of the algebra.

The pattern is exact and it is the pattern of the Poincaré group: the boost generator is the source of nearly all the incompatibility, because the boost fails to commute with energy, with momentum, and with rotation. Lorentz-violation tests are therefore the *least* co-testable with anything else — a probe pointed at Lorentz violation is, by the structure of spacetime symmetry itself, a probe compromised for every other Einstein-symmetry test. The corpus's earlier remark, in the single-symmetry framework, that Lorentz tests want a probe of large boost-generator variance now has a sharp and sobering complement: that very variance, by the non-abelian algebra, is what spoils the same probe for the energy-, momentum-, and rotation-generated tests.

### III.3 Why This Is a Theorem and Not a Pessimism

It would be easy to misread this document as a counsel of despair — "you cannot test everything, so testing is limited." That is not the claim. The claim is sharper and more useful.

First, the trade-off is *quantitative*. The Holevo bound, with the Poincaré commutators as inputs, does not say "joint testing is impossible"; it says exactly how much total precision must be conceded, and how that concession can be *allocated* across the symmetries by choice of probe. An experiment designer who knows the penalty can choose where to spend it — sharpen the Lorentz test and accept a known, computed loss on the position-invariance test, or balance them, or anything between. The Poincaré algebra does not forbid joint testing; it prices it, exactly, and a priced trade-off is a design tool.

Second, the trade-off identifies the *compatible corners*. Because translations commute, symmetry tests that live purely in the translation sector can be co-optimized without penalty. The algebra therefore partitions the twenty anomalies of the previous documents not only into generator classes but into *compatibility clusters* — sets of tests that share commuting generators and can be pursued on one probe at full precision, separated from sets that cannot. That partition is a real piece of strategic guidance, derivable before any apparatus exists.

Third — and this is the genuinely new structural statement — it means the **non-abelian structure of spacetime symmetry is itself measurable as a metrological trade-off.** The commutators of the Poincaré algebra are not only the reason moving clocks run slow; they are the reason a single probe cannot optimally co-test the symmetries those clocks could check. The incompatibility penalty in a joint Einstein-symmetry experiment is a *shadow of the Poincaré algebra cast onto the experiment's error budget*. Measure the trade-off and you have measured the algebra. That is the document's wild claim, and it is a theorem: the structure constants of the Poincaré group are the incompatibility coefficients of fundamental-symmetry metrology, and the two are the same numbers.

---

## Part IV · Scope, Honestly Stated

The limits of this document are part of the claim.

**The clean form of the result is the pure-probe, unitary-encoding form.** The statement "incompatibility penalty is governed by ⟨[Gᵢ, Gⱼ]⟩" holds sharply for pure probes under noiseless unitary encoding of the couplings. With decoherence the quantum Fisher information becomes a matrix whose incompatibility part is modified, and the Holevo bound must be evaluated in its general form. This does not remove the penalty — decoherence generically *worsens* joint estimation — but it means the precise coefficient is the noiseless commutator only in the noiseless limit. The honest statement is that the Poincaré commutators set the *ideal* trade-off, the best a joint test could do, and that real noise is an additional, separately accountable cost.

**Incompatibility can be mitigated, not eliminated, by collective measurements.** Multiparameter estimation theory establishes that the Holevo bound can be approached using entangled measurements across many copies of the probe. This relocates the penalty — it does not abolish it. The Holevo bound itself, the true asymptotic limit, still lies above the additive bound whenever the generators fail to commute. The non-abelian algebra is not defeated by collective measurement; it is confronted at its true value, which remains non-zero.

**This is a statement about co-testing on one probe, not about physics being untestable.** Every Einstein symmetry can be tested to extraordinary precision *individually*, on a probe dedicated to it — that is the content of the previous document and it stands. This document constrains only the joint, single-probe program: it says the dedicated optima cannot all be achieved at once on one state. Running separate, dedicated experiments evades the penalty entirely. The trade-off is a property of the ambition to do everything with one probe, and it is precisely that ambition the document prices.

**It does not unify the twenty anomalies into one phenomenon.** As in the previous documents, the twenty remain twenty distinct hypotheses about distinct couplings. What this document adds is a relation *among the tests* — a compatibility structure inherited from the Poincaré algebra — not a relation among the underlying physical effects. A taxonomy of which tests share a probe, and which trade off, is organizational truth, not theoretical unification, and is offered only as the former.

The single defensible sentence is the one the abstract states and Part III proves: **joint estimation of several Einstein-symmetry-violation couplings on one probe is governed by the Holevo–Cramér–Rao bound; that bound exceeds the sum of single-symmetry bounds by an incompatibility penalty set by the commutators of the symmetry generators; those generators are the generators of the Poincaré group; and therefore the non-abelian structure constants of spacetime symmetry are the irreducible trade-off coefficients of fundamental-symmetry metrology — one probe cannot optimally test all of Einstein's symmetries at once, and the reason is the algebra of spacetime itself.** It is a theorem, it is checkable, and it tells an experiment designer exactly which tests to combine and which to separate. There is no machine with seven layers and no φ-suppressed prediction. There is one bound, one algebra, and a trade-off whose coefficients were fixed when spacetime got its symmetry group.

---

## References

Holevo, A. S. *Probabilistic and Statistical Aspects of Quantum Theory.* North-Holland, Amsterdam, 1982.

Helstrom, C. W. *Quantum Detection and Estimation Theory.* Academic Press, New York, 1976.

Albarelli, F., Friel, J. F., Datta, A. "Evaluating the Holevo Cramér-Rao Bound for Multiparameter Quantum Metrology." *Physical Review Letters* **123**, 200503 (2019).

Albarelli, F., Barbieri, M., Genoni, M. G., Gianani, I. "A Perspective on Multiparameter Quantum Metrology." *Physics Letters A* **384**, 126311 (2020).

Ragy, S., Jarzyna, M., Demkowicz-Dobrzański, R. "Compatibility in Multiparameter Quantum Metrology." *Physical Review A* **94**, 052108 (2016).

Carollo, A., Spagnolo, B., Dubkov, A. A., Valenti, D. "On Quantumness in Multi-Parameter Quantum Estimation." *Journal of Statistical Mechanics* **2019**, 094010 (2019).

Das, A., Conlon, L. O., Suzuki, J., Yung, S. K., Lam, P. K., Assad, S. M. "Holevo Cramér-Rao Bound: How Close Can We Get Without Entangling Measurements?" *Quantum* **9**, 1867 (2025).

"Weight-Dependent and Weight-Independent Measures of Quantum Incompatibility in Multiparameter Estimation." arXiv:2510.18864 (October 2025).

"Randomized Measurements for Multi-Parameter Quantum Metrology." arXiv:2502.03536 (February 2025).

Weinberg, S. *The Quantum Theory of Fields, Volume I: Foundations.* Cambridge University Press, 1995. (For the Poincaré algebra.)

Kostelecký, V. A., Russell, N. "Data Tables for Lorentz and CPT Violation." *Reviews of Modern Physics* **83**, 11–31 (2011).

---

ERI Labs · Eric Ren · Jersey City, New Jersey · github.com/ericrenone · May 2026

One probe cannot test all of Einstein's symmetries at once. The trade-off coefficients are the commutators of the Poincaré algebra — the non-abelian structure of spacetime, read off an error budget.
