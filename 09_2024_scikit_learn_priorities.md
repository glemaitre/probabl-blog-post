# Open source software priorities at Probabl

## Retrospective

### scikit-learn

In a previous [blog
post](https://papers.probabl.ai/scikit-learns-priorities-at-probabl), we outline
Probabl's priorities for scikit-learn. In this section, we report on the progress of
these priorities.

#### Short-term priorities

We successfully complete two major short-term priorities:

1. Website Migration: We successfully migrate the scikit-learn website to the new
   PyData theme-based website. This modernization effort improves the user
   experience and aligns our documentation with the broader PyData ecosystem.

2. SLEP6 - Metadata Routing: We complete adapting most estimators to handle
   metadata routing as specified in
   [SLEP6](https://scikit-learn-enhancement-proposals.readthedocs.io/en/latest/slep006/proposal.html).
   This new API consistently handles metadata (e.g., `sample_weight`, `groups`, etc.)
   for all estimators. It allows for fewer bugs and enables new
   use cases that were not possible before.

Both of these projects represent major milestones for scikit-learn. In our current
round of priorities, we outline follow-up work for both the website and metadata
routing to further improve and expand on these changes.

#### Mid-term priorities

From the mid-term priorities, we successfully complete the following:

1. Implementation of a new scikit-learn estimator, called `TunedThresholdClassifierCV`,
   allowing optimization of the operational decision.

2. Progress on the Array-API adoption by making it possible to train and test a pipeline
   containing a `PCA` and `Ridge` estimator trained on `torch` tensors located on GPU.

#### Long-term priorities

In this last section, we report on long-term and sometimes recurring efforts that are
important for the project's health.

1. General maintenance of the project: We review a substantial number of pull requests
   and issues opened by external contributors.

2. Python 3.13 support: We work on supporting Python 3.13 free-threaded mode and set
   up regular testing to ensure compatibility until it becomes officially available.

3. Releases: Since February 2024, we release scikit-learn 1.5.0, 1.5.1, and 1.5.2.

4. Continuous Integration and Continuous Deployment: We keep our continuous
   integration and continuous deployment infrastructure up to date.

5. Community outreach: Since February 2024, we attend multiple Python conferences
   to promote the latest work on scikit-learn. We attend the following conferences:
   PyCon Lithuania, PyCon Italia, CZI Open Science, EuroSciPy, PyData Amsterdam, and
   PyData Paris.
