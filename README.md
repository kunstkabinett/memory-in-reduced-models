# Learning memory in reduced models

A model of a molecule need not track every surrounding atom. But the variables it leaves out can continue to influence its motion. This influence can appear as memory: the future depends on more than the present state. Learning that memory could make small models more faithful to the physical systems they describe.[^sanderse-2024]

In a simple generalized Langevin model, a retained velocity $v(t)$ obeys

$$
\dot v(t) = -\int_0^t K(t-s)v(s)\,ds + \eta(t).
$$

Here $K$ is the memory kernel and $\eta$ is a random force representing unresolved motion; mass is set to one and external forces are omitted. The kernel describes how strongly earlier motion matters. We would like to recover it from observed trajectories.

Lang and Lu give a starting point: a method for learning scalar kernels, with stability estimates under smoothness, decay, and spectral assumptions. Their bounds depend on how accurately correlation functions and their derivatives are estimated.[^lang-lu-learning] Later work connects kernel error to prediction error for models with additive white noise, under further stability conditions.[^lang-lu-error]

Several directions seem worth exploring:

- What can short, noisy observations tell us about memory?
- How much long-time memory can a small model safely forget?
- How can learned memory and random forcing remain physically consistent?

These are starting questions, not claims of novelty. A useful first step is to revisit a simple example with known memory and see what changes when observations become sparse. An explanation of failure could be as useful as a better reconstruction.

See the [questions](https://github.com/public-observatory/memory-in-reduced-models/issues?q=is%3Aissue+label%3Aquestion), [reading notes](writeups/reading-notes.md), and [contribution guide](https://public-observatory.github.io/docs.html).

[^sanderse-2024]: Benjamin Sanderse, Panos Stinis, Romit Maulik, and Shady E. Ahmed, *Scientific machine learning for closure models in multiscale problems: a review* (2024), research survey preprint [arXiv:2403.02913v2](https://arxiv.org/abs/2403.02913v2), §7.
[^lang-lu-learning]: Quanjun Lang and Jianfeng Lu, *Learning Memory Kernels in Generalized Langevin Equations* (2026), SIAM Journal on Mathematics of Data Science 8(1), 141–166, [doi:10.1137/24M1651101](https://doi.org/10.1137/24M1651101). Open manuscript: [arXiv:2402.11705v3](https://arxiv.org/abs/2402.11705v3) (2025), §§2–6 and Appendix A; section references refer to this version.
[^lang-lu-error]: Quanjun Lang and Jianfeng Lu, *Error Analysis of Generalized Langevin Equations with Approximated Memory Kernels* (2026), SIAM/ASA Journal on Uncertainty Quantification 14(3), 1304–1335, [doi:10.1137/26M1837290](https://doi.org/10.1137/26M1837290). Open manuscript: [arXiv:2512.10256v1](https://arxiv.org/abs/2512.10256v1) (2025), §§1, 3–4, 6; section references refer to this version.
