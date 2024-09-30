# Scikit-learn's priorities at Probabl

In the open source team at Probabl, we focus on scikit-learn and certain aspects of its
ecosystem. Since we have a fair amount of person-power dedicated to scikit-learn, it’s
important for us to communicate what aspects of the library are our priorities and what
our general goals are.

There are a few considerations we have taken into account in this process:

* What are big picture goals and themes which would help our users to have a better
  experience, as well as giving them tools to use our libraries (scikit-learn and
  beyond) across their machine learning pipeline, from training and exploration to
  production.
* In 2023, the scikit-learn community conducted a few surveys to better understand core
  contributors’ concerns and priorities. The results of these surveys have guided us in
  this process.
* The scikit-learn consortium conducts regular meetings with its sponsors, and a list of
  priorities emerge from those meetings that we have taken into account.
* The team at Probabl and their interests does not fully represent the broader
  contributor community, and to keep the community healthy, we considered priorities of
  people who are not at Probabl as well, and try to dedicate resources to those aspects.
* We will revisit our list of priorities about twice a year.

## General Objectives

Other than maintaining the project and making sure we keep our healthy release cycle,
which are included in the “long running projects” section, the main objective is to keep
scikit-learn relevant and usable for our users over the coming years. For this, we can
consider the following overarching areas encompassing most projects inside scikit-learn.
Note that here the order is arbitrary and does not indicate priority.

* Better documentation in terms of making it easier for people to find best practices in
  their domain for what they need to do.
    * This also includes giving users a better insight into what their technical
      decisions imply for their use-case.
* Improve UX in order for users to interact with scikit-learn in a more intuitive way,
  which includes the API, e.g. Pipeline and ColumnTransformer declarations, and also
  inspection tasks, e.g. inspecting the pipeline, data, predictions, etc.
* Improve third party integrations in terms of people being able to extend scikit-learn
  in an easier and more consistent way through public / developer APIs.
* Model evaluation, monitoring, inspection, and interpretation to have methodologically
  correct, fair and responsible, and compliant models.
    * Enable solving statistical learning problems that cannot be well solved with the
      current set of tools (eg. imputing a big matrix)
* Performance of scikit-learn should always be best of a kind on modern hardware used by
  users.
* Facilitate deployment (model or just predictor persistence across scikit-learn
  versions) and MLOps use cases.
    * This includes working well with other libraries and frameworks such as skops and
      ONNX.

## Release cycles:

* Release twice a year: May & November

## Current and Near Future Large Projects

Considering our general objectives, here are the projects on which we will have a major
focus. In order to reasonably advance each project, we need one person leading the
project, and at least two other maintainers who would review the relevant issues and
pull requests.

Notes:

* This is a living list and what we have here is a snapshot at this point in time. We
  will be releasing an update to this on twice a year basis.
* Not all projects mentioned here are being led by people at Probabl, but we are
  allocating resourced to these projects to help them advance. People who are currently
  working at Probabl on scikit-learn are:
    * Adrin Jalali, Guillaume Lemaitre, Jérémie du Boisberranger, Olivier Grisel,
      Stefanie Senger
* Due to available resources, not all of these projects are very active. Due to
  resource constraints, we have to focus on less projects to move them forward. If you
  would like to see certain aspects of the project to move faster and you're happy to
  support us, we're happy to hear from you here.

These projects are split into 3 groups. The first are the projects which have been
ongoing for a while, have achieved major milestones, and are expected to be mostly
concluded in the next 3 months to a year.

* New website: a PyData theme based website
    * @Charlie-XIAO leading, @adrinjalali, @GaelVaroquaux, and @ogrisel reviewing
* SLEP6 - metadata routing
    * @adrinjalali leading, @glemaitre, @OmarManzoor, @StefanieSenger, @agramfort,
      and sometimes @thomasjpfan developing and reviewing

A second group of projects are the ones which are not expected to finish in the near
future, but we focus on them and think they’re important to be developed. The order in
this list indicates a slight priority for us.

* Inspection
    * @glemaitre leading, @jeremiedbb, @ogrisel (in limited scope) reviewing
* Loss + Solvers
    * led externally to Probabl at the moment, @ogrisel, @jjerphan reviewing
* Developer API / third party support
    * This includes persisting C-level objects w/o pickle, separate estimator checks into
      basic API and scikit-learn specific tests, tags, documentation, etc.
    * @adrinjalali will start / lead, @glemaitre and @thomasjpfan help / review
* Front-end sklearn UI/UX (html notebook displays)
    * @GaelVaroquaux reviewing, will try to see if Inria can help
    * @glemaitre would like to help
    * @Charlie-XIAO might be able/interested in helping and reviewing
* Callbacks
    * @jeremiedbb leading, @glemaitre, @adrinjalali reviewing
        Most probably needs a SLEP first.
* Array API
    * mid-term goal: grid-search with skorch model + Logistic Regression and data that
      stays on the GPU
    * @ogrisel and @betatim leading, @thomasjpfan (leading initially and reviewing),
      @glemaitre (could help to unlock), @jeromedockes (starts to help)

The last group are long running projects which we have in mind, and dedicated resources
to advance them.

* Maintainance
    * Maintainance, including bug fixes and reviewing external PRs takes a significant
      amount of resources, and everyone in the team dedicates time for this.
* Releases
    * @glemaitre, @jeremiedbb
* Build, CI
    * @lesteve leading in practice, but we need more people here, @thomasjpfan helping
    * Note that we do need more people active in this space.
* Performance
    * @jjerphan, @ogrisel, @jeremiedbb
* Documentation
    * @arturoamorq, @glemaitre → we need more people here considering Arturo will have
      less time for scikit-learn as we progress.

And at the end there’s the list of topics that we would like to have / develop but we do
not have enough resources at the moment:

* Dataframe interoperability
    * Thomas led that effort so far, but the project is less active and has achieved
      certain milestones such as being able to output Pandas and Polars dataframes from
      transformers, and understanding them as input in ColumnTransformer.
    * Need to reassess and investigate the current dataframe playground and decide on a
      clear path forward.

* Missing values and categorical input type
    * Thomas started but less time to work on that nowadays
    * Categorical for non-histogram trees would be a good next candidate
    * Needs more resources to continue

* Hyper-parameter spaces
    * @jnothman has opened a SLEP, @adrinjalali and @amueller reviewing, but not very active at the moment.

##  Team Growth

We are hiring for a few positions focusing on certain aspects of the ecosystem, and the
new recruits will spend a fair amount of time on scikit-learn as well.

We will also try to find dedicated funding for certain aspects of the project, in areas
where there are shared interests between the scikit-learn project and stakeholders such
as hardware providers or relevant government agencies.
