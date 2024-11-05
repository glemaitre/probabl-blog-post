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

- Short-term priorities

   1. Website Migration: We successfully migrated the `scikit-learn` website to the new
      PyData theme-based website. This modernization effort improves the user
      experience and aligns our documentation with the broader PyData ecosystem.
   1. SLEP6 - Metadata Routing: We completed adapting most estimators to handle
      metadata routing as specified in
      [SLEP6](https://scikit-learn-enhancement-proposals.readthedocs.io/en/latest/slep006/proposal.html).
      This new API consistently handles metadata (e.g., `sample_weight`, `groups`, etc.)
      for almost all estimators. It allows for fewer bugs and enables new
   use cases that were not possible before.

Both of these projects represent major milestones for `scikit-learn`. In our current
round of priorities, we outline follow-up work for both the website and metadata
routing to further improve and expand on these changes.

-  Mid-term priorities

   1. Implementation of a new `scikit-learn` estimator, called
      `TunedThresholdClassifierCV`, allowing optimization of the operational decision.
   1. Progress on the Array-API adoption by making it possible to train and test a
      pipeline containing a `PCA` and `Ridge` estimator trained on `torch` tensors
      located on GPU.
   1. Some work to improve the developer experience by improving the developer tools
      available in `scikit-learn` and made available for third-party projects.

- Long-term priorities

   1. General maintenance of the project: We reviewed a substantial number of pull
      requests and issues opened by external contributors.
   1. Python 3.13 support: We worked on supporting Python 3.13 free-threaded mode and
      set up regular testing to ensure compatibility until it becomes officially
      available.
   1. Releases: Since February 2024, we released `scikit-learn` 1.5.0, 1.5.1, and 1.5.2.
   1. Continuous Integration and Continuous Deployment: We kept our continuous
      integration and continuous deployment infrastructure up to date.
   1. Community outreach: Since February 2024, we attended multiple Python conferences
      to promote the latest work on `scikit-learn`. We attended the following
      conferences: PyCon Lithuania, PyCon Italia, CZI Open Science, EuroSciPy, PyData
      Amsterdam, and PyData Paris.

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

We also helped at releasing `fairlearn` and make sure it is compatible with the
different upstream dependencies (e.g. `numpy`, `scikit-learn`).

### [`skops`](https://github.com/skops-dev/skops)

The main activity in the project relates to non-trivial maintenance tasks
to ensure that the project is in a healthy state and compatible with the latest
versions of `scikit-learn` and `NumPy`.

### [`skrub`](https://github.com/skrub-data/skrub)

In the past few months, we focused on delivering new features such as:

1. Support for `polars` dataframes in `skrub` estimators.
1. Adding interactive reports of dataframes through a `TableReport` that provides
   information to carry out Exploratory Data Analysis (EDA).
1. Easing the creation of predictive models by removing boilerplate code using a factory
   function called `tabular_learner`.
1. Improving the landing page of the `skrub` website to make it more user-friendly and
   informative.

### Python in the browser (WebAssembly)

We make sure that `scikit-learn` is compatible with the WebAssembly stack:
[`pyodide`](https://github.com/pyodide/pyodide),
[`jupyterlite`](https://github.com/jupyterlite/jupyterlite). We reported potential
issues upstream and helped run the SciPy test suite for the pyodide project.

### [`hazardous`](https://github.com/soda-inria/hazardous)

The current focus for this project is to define the scope of the library such that it
does not overlap with existing tools. While the code is developed in parallel with a
research project, we are working on improving tests and documentation to make the
library more robust and ready for a first release.

## Focus Areas for the Next 6 Months

As we look ahead to the next six months, we have identified several key areas where we
will concentrate our efforts to further enhance `scikit-learn` and its ecosystem. These
focus areas align with our general objectives and aim to address current challenges
and opportunities in the machine learning landscape.

### [`scikit-learn`](https://github.com/scikit-learn/scikit-learn)

We start by focusing on the future work for `scikit-learn`.

1. Statistical correctness: *ogrisel, snath-xoc, antoinebaker, jeremiedbb*
   - We will continue our maintenance work to ensure that sample weights are
      correctly handled in estimators.
   - We will improve the documentation to better explain which cross-validation
      strategies should be used in line with the end-user's goal.
   - We will work on improving the solvers of linear models.
1. New visualizations: *lucyleeow, glemaitre, jeremiedbb*
   - We will develop some additional displays to help with model inspection.
   - We will work on adapting the existing displays to visualize the outputs of
     cross-validation results.
   - We will search for ways to improve the HTML representation of estimators.
1. Callbacks API: *jeremiedbb, adrinjalali, glemaitre, ogrisel*
   - We will work on merging the infrastructure for callbacks together with a callback
     to provide progress bars.
   - Subsequently, we will work on additional callbacks.
1. Improve histogram gradient-boosting: *GaelVaroquaux, glemaitre, lesteve, ogrisel*
   - We will benchmark the `HistGradientBoosting` estimators to understand the room
     for improvement of these estimators to match the performance of LightGBM and
     XGBoost.
   - We will assess if we should merge both `GradientBoosting` and
     `HistGradientBoosting` estimators into a single class.
1. Array API: *betatim, ogrisel, lesteve, StefanieSenger, OmarManzoor, EmilyXinyi*
   - We will continue our work on the Array API adoption. Notably, we will work on
     adopting the API for `Nystroem`, `Ridge` and at least one solver of
     `LogisticRegression`.
1. Python 3.13 support: *lesteve, ogrisel*
   - We will continue our work on supporting Python 3.13 free-threaded and release
     wheels and binaries for the new Python version.
1. Metadata routing: *adrinjalali, StefanieSenger, glemaitre, OmarManzoor, adam2392*
   - We will continue some further work related to metadata routing and SLEP6.
   - We will define, whenever possible, a default behavior for `sample_weight`.
   - We will provide a visualization tool to understand how metadata are routed
     between estimators.
   - We will write or modify examples to illustrate how to use metadata routing.
1. Model inspection: *lucyleeow, glemaitre, TamaraAtanasoska*
   - We will check on adapting the current mean decrease in impurity (MDI) to work
     on test sets.
   - We will work on SLEP11 to provide a unified interface to inspect the "feature
     importances" of estimators.
1. Developer API: *adrinjalali, glemaitre, adam2392, Charlie-XIAO, OmarManzoor*
   - We will continue our work on improving the test suite by migrating some common
     tests to the estimator checks, to finalize common check categories, and to
     improve the associated documentation.
1. Documentation improvements:
   - We plan to further improve the gallery of examples, the contributor guide, and
     the developer guide. To carry on this work, we will organize two dedicated
     sprints focusing especially on the documentation.
1. Project maintenance:
   - We will continue our regular triage of issues and reviewing community pull
     requests.
   - We will make sure to keep our continuous integration and continuous deployment
     infrastructure up to date.
   - We will make sure to reinstate our ASV benchmark allowing use to detect potential
     performance regressions.
1. Releases:
   - We will continue to release on a regular basis.

### Computing orchestration

We have to adapt all the stack (`joblib`, `loky`, `cloudpickle`, `threadpoolctl`) to the
CPython free-threaded mode. This will involve some stress testing to ensure that the
parallelism works as expected.

### [`fairlearn`](https://github.com/fairlearn/fairlearn)

*tamaratanasoska, adrinjalali*

We will contribute to the community roadmap that has recently been updated:
https://docs.google.com/document/d/1rNCqRQP0g6kVplqB4DSW3o9ruXuJQun9yYv6FBouaac/edit?tab=t.0#heading=h.v4tu3p4sz3uj

### [`skops`](https://github.com/skops-dev/skops)

*tamaraatanasoska, adrinjalali*

The main activity in the project relates to non-trivial maintenance tasks
to ensure that the project is in a healthy state and compatible with the latest
versions of `scikit-learn` and `NumPy`.

### [`skrub`](https://github.com/skrub-data/skrub)

*Vincent-Maladiere, glemaitre*

We will help a tackling item from the community roadmap available at:
https://skrub-data.org/stable/vision.html#roadmap

### [`hazardous`](https://github.com/soda-inria/hazardous)

*Vincent-Maladiere, ogrisel, glemaitre*

1. Implement metrics for competing risks
   - Concordance Index
   - Refine metrics API
1. Implement early stopping based on validation score
1. Improve the documentation and examples
1. Start releasing the package
1. Generalize `MultiIncidenceGradientBoosting` as a meta-estimator to wrap any
   classifier that supports `sample_weight`

## Our contributors

The following open source engineers from Probabl are contributing to the above
priorities for the different projects:

- [Adrin Jalali](https://github.com/adrinjalali)
- [Antoine Baker](https://github.com/antoinebaker)
- [Guillaume Lemaitre](https://github.com/glemaitre)
- [Jérémy du Boisberranger](https://github.com/jeremiedbb)
- [Loïc Esteve](https://github.com/lesteve)
- [Olivier Grisel](https://github.com/ogrisel)
- [Shruti Nath](https://github.com/snath-xoc)
- [Stefanie Senger](https://github.com/StefanieSenger)
- [Tamara Atanasoska](https://github.com/tamaraatanasoska)
- [Vincent Maldière](https://github.com/Vincent-Maladiere)

We want to acknowledge that all this work would not have been possible without the
incredible support of the scikit-learn community. The continuous engagement, feedback,
and contributions from community members, whether through code, documentation, bug
reports, or discussions, have been instrumental in shaping and advancing these
projects.
