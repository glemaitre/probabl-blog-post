# Open source software priorities at Probabl

At Probabl, we continue our dedicated efforts to support and enhance `scikit-learn` and
its ecosystem. In this post, we provide a retrospective on the work we have
accomplished on `scikit-learn` and other supported open-source packages over the past
6 months. Additionally, we outline our updated priorities and focus areas for the next
6 months.

As we reflect on our progress and look ahead, it is important to reiterate the key
considerations that guide our decision-making process:

* Identifying big picture goals and themes that improve user experience and provide
  tools for the entire machine learning pipeline, from training and exploration to
  production.
* Insights from community surveys conducted in 2023 to understand core contributors'
  concerns and priorities. Additionally, we will soon incorporate feedback from the
  ongoing [user `scikit-learn` survey](https://forms.gle/zUXvWjGUN1nWhJ2V6) to further
  align our efforts with user needs and expectations.
* Commitment to revisiting our list of priorities approximately twice a year.

Let's review our achievements and set the stage for our upcoming focus areas.

## Retrospective on the past 6 months

This section summarizes the progress of Probabl's work on the different supported
open-source projects.

### [`scikit-learn`](https://github.com/scikit-learn/scikit-learn)

In a previous [blog
post](https://papers.probabl.ai/scikit-learns-priorities-at-probabl), we outlined
Probabl's priorities for `scikit-learn`. In this section, we report on the progress of
these priorities.

#### Short-term priorities

We successfully completed two major short-term priorities:

1. Website Migration: We successfully migrated the `scikit-learn` website to the new
   PyData theme-based website. This modernization effort improves the user
   experience and aligns our documentation with the broader PyData ecosystem.

2. SLEP6 - Metadata Routing: We completed adapting most estimators to handle
   metadata routing as specified in
   [SLEP6](https://scikit-learn-enhancement-proposals.readthedocs.io/en/latest/slep006/proposal.html).
   This new API consistently handles metadata (e.g., `sample_weight`, `groups`, etc.)
   for all estimators. It allows for fewer bugs and enables new
   use cases that were not possible before.

Both of these projects represent major milestones for `scikit-learn`. In our current
round of priorities, we outline follow-up work for both the website and metadata
routing to further improve and expand on these changes.

#### Mid-term priorities

From the mid-term priorities, we successfully completed the following:

1. Implementation of a new `scikit-learn` estimator, called `TunedThresholdClassifierCV`,
   allowing optimization of the operational decision.

2. Progress on the Array-API adoption by making it possible to train and test a pipeline
   containing a `PCA` and `Ridge` estimator trained on `torch` tensors located on GPU.

3. Some work to improve the developer experience by improving the developer tools
   available in `scikit-learn` and made available for third-party projects.

#### Long-term priorities

In this last section, we report on long-term and sometimes recurring efforts that are
important for the project's health.

1. General maintenance of the project: We reviewed a substantial number of pull requests
   and issues opened by external contributors.

2. Python 3.13 support: We worked on supporting Python 3.13 free-threaded mode and set
   up regular testing to ensure compatibility until it becomes officially available.

3. Releases: Since February 2024, we released `scikit-learn` 1.5.0, 1.5.1, and 1.5.2.

4. Continuous Integration and Continuous Deployment: We kept our continuous
   integration and continuous deployment infrastructure up to date.

5. Community outreach: Since February 2024, we attended multiple Python conferences
   to promote the latest work on `scikit-learn`. We attended the following conferences:
   PyCon Lithuania, PyCon Italia, CZI Open Science, EuroSciPy, PyData Amsterdam, and
   PyData Paris.

### Computing orchestration

We dedicated resources to maintain the following projects that are related to computing
orchestration: `joblib`, `loky`, `cloudpickle`, `threadpoolctl`, and support for
Python free-threaded mode.

`threadpoolctl` has been released in the past few months and includes better support
for BLAS libraries (FlexBLAS, OpenBLAS, Netlib, Accelerate, etc.).

We dedicated substantial work to ensuring scikit-learn's compatibility with Python 3.13's
free-threaded mode, including extensive testing, necessary adaptations, and reporting
any issues to upstream projects.

### [`fairlearn`](https://github.com/fairlearn/fairlearn)

In the past few months, the main focus of the project has been to ensure that the
estimators developed in `fairlearn` are compatible with `scikit-learn`. To achieve this,
we used the testing framework provided by `scikit-learn` to test the `fairlearn`
estimators.

### [`skops`](https://github.com/skops-dev/skops)

The main activity in the project relates to non-trivial maintenance tasks
to ensure that the project is in a healthy state and compatible with the latest
versions of `scikit-learn` and `NumPy`.

### [`skrub`](https://github.com/skrub-data/skrub)

In the past few months, we focused on delivering new features such as:

1. Support for `polars` dataframes in `skrub` estimators.

2. Adding interactive reports of dataframes through a `TableReport` that provides
   information to carry out Exploratory Data Analysis (EDA).

3. Easing the creation of predictive models by removing boilerplate code using a factory
   function called `tabular_learner`.

4. Improving the landing page of the `skrub` website to make it more user-friendly and
   informative.

### Python in the browser (WebAssembly)

We make sure that `scikit-learn` is compatible with the WebAssembly stack:
[`pyodide`](https://github.com/pyodide/pyodide),
[`jupyterlite`](https://github.com/jupyterlite/jupyterlite). We reported potential
issues upstream and helped run the SciPy test suite for the pyodide project.

### [`hazardous](https://github.com/soda-inria/hazardous)

The current focus for this project is to define the scope of the library such that it
does not overlap with existing tools. While the code is developed in parallel with
a research project, we are working on improving tests and documentation to make the library
more robust and ready for a first release.

## Focus Areas for the Next 6 Months

As we look ahead to the next six months, we have identified several key areas where we
will concentrate our efforts to further enhance `scikit-learn` and its ecosystem. These
focus areas align with our general objectives and aim to address current challenges
and opportunities in the machine learning landscape.

TODO: incorporate the team focus for each project here. We need to decide first the
priorities for each project.
