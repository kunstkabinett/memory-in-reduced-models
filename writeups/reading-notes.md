# Reading notes

Literature checked on 2026-10-17. This is a brief review, not an exhaustive priority search. References and versioned links are in the [README](../README.md).

The Sanderse et al. survey, §7, situates memory within Mori–Zwanzig reduction. Exact projection identities motivate approximations; they do not make their unknown terms easy to compute. This agenda concentrates on learning convolution kernels, not every form of multiscale closure.

The anchor is Lang and Lu's *Learning Memory Kernels in Generalized Langevin Equations*. The open v3 manuscript was read through Appendix A, including the numerical comparisons. Its two stages estimate smooth correlations and then fit a kernel using a Sobolev loss. Theorem 4.2 is conditional on correlation-estimation accuracy; it is not an end-to-end finite-data guarantee. The scalar, smooth, exponentially decaying setting and spectral bounds matter. Power-law examples extend the numerical exploration beyond the stated analysis. Figures 2 and 4 compare estimators and weighting choices; Appendix A explores temporal versus ensemble averaging. These are synthetic demonstrations, not validation on experimental molecular data.

The later error-analysis paper already treats kernel perturbations, including matrix-valued and non-translation-invariant kernels. Sections 1, 3–4, and 6 distinguish its fixed white-noise setting from fluctuation-dissipation-consistent colored noise. The latter is an explicit future direction in the open manuscript. Its stability hypotheses must be checked before transferring a bound to a proposed physical model.

Publication records were checked separately: the learning paper appeared in February 2026 and the error-analysis paper in September 2026. We used their freely available manuscript versions, not an assumed identical publisher text. Targeted searches for subsequent learning and stability work informed the questions; they do not establish novelty.

The limited-observation question follows the anchor's stated future work. Memory compression is our proposed organizing question. The noise question follows the later manuscript's stated limitation. Each question should be narrowed and checked against the literature when someone chooses a specific problem.
