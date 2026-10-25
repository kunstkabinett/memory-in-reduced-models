# Learning memory in reduced models

A simulation of a protein cannot afford to follow every water molecule around it. A reduced model keeps a few variables and drops the rest. But the dropped variables do not stop acting: they push back on the retained ones with a delay, so that the future depends on the past and not only on the present. Getting this memory right is what makes a cheap model faithful.[^sanderse-2024]

The simplest setting is the generalized Langevin equation. A retained velocity $v(t)$ obeys

$$
\dot v(t) = -\int_0^t K(t-s)v(s)\,ds + \eta(t),
$$

where the kernel $K$ records how strongly past motion acts now, and $\eta$ is the random force exerted by everything left out; mass is set to one and external forces are omitted. The kernel is rarely known. It has to be learned from trajectories.

Lang and Lu learn scalar kernels from estimated correlation functions, with stability estimates under smoothness, decay and spectral assumptions.[^lang-lu-learning] Later work bounds the prediction error caused by an error in the kernel, for additive white noise.[^lang-lu-error] Two questions lie just beyond these results:

- **[What can limited data reveal?](https://github.com/project-wk/memory-in-reduced-models/issues/1)** From short, noisy or sparsely sampled trajectories, which features of a kernel can be recovered, and when do two different kernels become indistinguishable?
- **[Can memory and noise be learned together?](https://github.com/project-wk/memory-in-reduced-models/issues/3)** In a thermal system the kernel and the random force are tied by the fluctuation–dissipation relation. Which guarantees survive when approximating the kernel also changes the noise?

A good first contribution takes a simple example with known memory and follows what is lost as the data thin out. A clear account of a failure is worth as much as a better reconstruction. The [reading notes](writeups/reading-notes.md) say what each source proves.

[^sanderse-2024]: Benjamin Sanderse, Panos Stinis, Romit Maulik, and Shady E. Ahmed, *Scientific machine learning for closure models in multiscale problems: a review* (2024), research survey preprint [arXiv:2403.02913v2](https://arxiv.org/abs/2403.02913v2), §7.
[^lang-lu-learning]: Quanjun Lang and Jianfeng Lu, *Learning Memory Kernels in Generalized Langevin Equations* (2026), SIAM Journal on Mathematics of Data Science 8(1), 141–166, [doi:10.1137/24M1651101](https://doi.org/10.1137/24M1651101). Open manuscript: [arXiv:2402.11705v3](https://arxiv.org/abs/2402.11705v3) (2025), §§2–6 and Appendix A; section references refer to this version.
[^lang-lu-error]: Quanjun Lang and Jianfeng Lu, *Error Analysis of Generalized Langevin Equations with Approximated Memory Kernels* (2026), SIAM/ASA Journal on Uncertainty Quantification 14(3), 1304–1335, [doi:10.1137/26M1837290](https://doi.org/10.1137/26M1837290). Open manuscript: [arXiv:2512.10256v1](https://arxiv.org/abs/2512.10256v1) (2025), §§1, 3–4, 6; section references refer to this version.
