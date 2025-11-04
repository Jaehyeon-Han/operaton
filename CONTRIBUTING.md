# How to contribute

* [Ways to contribute](#ways-to-contribute)
* [Browse our issues](#browse-our-issues)
* [Build from source](#build-from-source)
* [Create a pull request](#create-a-pull-request)
* [Code Style Guide](#code-style-guide)
  * [Code Formatting](#code-formatting)
  * [Naming Conventions](#naming-conventions)
  * [Documentation Standards](#documentation-standards)
  * [Architectural Guidelines](#architectural-guidelines)
* [Contribution checklist](#contribution-checklist)
* [Commit message conventions](#commit-message-conventions)
* [Review process](#review-process)

# Ways to contribute

We would love you to contribute to this project. You can do so in various ways.

If you are unsure about anything, have a question, or just want to talk about the project, please join our [forum](https://forum.operaton.org/) or [Slack channel](https://join.slack.com/t/operaton/shared_invite/zt-3fiodp5cz-vM2h5uDZi9JbCZZqG~6WEA).

## File bugs or feature requests

Found a bug in the code or have a feature that you would like to see in the future? [Search our open issues](https://github.com/operaton/operaton/issues) if we have it on the radar already or [create a new issue otherwise](https://github.com/operaton/operaton/issues/new/choose).

Please note, that our main goal after the fork is to provide minimal maintenance and ensure stability. We appreciate feature requests, but might decide not to merge them into the application in the first months.

Try to apply our best practices for creating issues:

* Only Raise an issue if your request requires a code change in Operaton
  * If you have an understanding question or need help building your solution, check out our [user forum](https://forum.operaton.org/).
* Create a high-quality issue:
  * Give enough context so that a person who doesn't know your project can understand your request
  * Be concise, only add what's needed to understand the core of the request
  * If you raise a bug report, describe the steps to reproduce the problem
  * Specify your environment (e.g. Operaton version, Operaton modules you use, ...)
  * Provide code. For a bug report, create a test that reproduces the problem. For feature requests, create mockup code that shows how the feature might look like. Fork our [unit test Github template](https://github.com/operaton/operaton-engine-unittest) to get started quickly.
  * Your time is valuable, so is ours. Please respect that we might not be able to work on your request immediately. We will try to give you feedback as soon as possible. 
    Please help us to understand your request fast by providing as much precise as possible.

## Write code

You can contribute code that fixes bugs and/or implements features. Here is how it works:

1. Select a ticket that you would like to implement. Have a look at [our backlog](https://github.com/operaton/operaton/issues) if you need inspiration. Be aware that some of the issues need good knowledge of the surrounding code.
1. Looking for a good place to start? Check out our guide on [Good First Issues](#good-first-issues) for tasks curated for newcomers.
1. Tell us in the ticket comments that you want to work on it. This is also the place where you can ask questions.
1. Follow our [Code Style Guide](#code-style-guide) for formatting, naming conventions, and documentation standards.
1. Check existing Architectural Decision Records (ADRs): Before implementing significant changes, review our [ADRs in docs/decisions/](docs/decisions/) to understand existing architectural decisions that may affect your implementation. If your change conflicts with or extends an existing decision, consider whether a new ADR is needed.
1. Check your code changes against our [contribution checklist](#contribution-checklist)
1. [Create a pull request](https://github.com/operaton/operaton/pulls). Note that you can already do this before you have finished your implementation if you would like feedback on your work in progress.


# Browse our issues

In this repository, we manage the [issues](https://github.com/operaton/operaton/issues) for the following Operaton code repositories and projects:

* https://github.com/operaton/operaton

We use [labels](https://github.com/operaton/operaton/labels) to mark and group our issues for easier browsing. We define the following label prefixes:

* `idea`: A suggestion for a new feature
* `bug`: Something isn't working
* `enhancement`: New feature or request
* `good first issue`: Good for newcomers
* `help wanted`: Extra attention is needed
* `question`: Further information is requested
* `documentation`: Improvements or additions to documentation
* `refactor`: Code refactoring
* `build`: Changes related to the build system, including Maven configurations, GitHub Actions workflows, etc.
* `dependencies`: Pull requests that update a dependency file
* `qa`: Tests, quality improvements and assurance
* `backport-c7`: Changes backported from Camunda 7
* `backport-cib7`: Changes backported from CIB seven
* `duplicate`: This issue or pull request already exists
* `invalid`: This will not be worked on
* `wontfix`: This will not be worked on

# Good First Issues

If you're new to the project and looking for a way to contribute, a great place to start is by tackling a "good first issue". These are issues that have been specifically curated to be accessible to newcomers.

You can find a list of all open good first issues [here](https://github.com/operaton/operaton/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

## What makes a "good first issue"?

We use the `good first issue` label to identify issues that are suitable for contributors who are not yet familiar with the codebase. These issues are expected to:

*   **Have a small scope:** The required changes should be isolated to a small number of files.
*   **Be well-defined:** The issue description should clearly outline the problem and the expected outcome. For bugs, it should include clear steps to reproduce.
*   **Require minimal project knowledge:** You shouldn't need a deep understanding of the project's architecture to work on the issue.
*   **Be a self-contained task:** The issue should be solvable without needing to tackle other issues first.

Examples of good first issues include fixing typos, improving documentation, adding a missing test case, or fixing a simple, well-documented bug.

## For Maintainers: Labeling Issues

As a maintainer, you can help new contributors by identifying and labeling appropriate issues. If you come across an issue that meets the criteria above, please add the `good first issue` label. This helps grow our community and allows new members to get involved more easily.

# Build from source

An entire repository can be built by running `mvn clean install` in the root directory.
This will build all sub modules and execute unit tests.
Furthermore, you can restrict the build to just the module you are changing by running the same command in the corresponding directory.
Check the repository's or module's README for additional module-specific instructions.
The `webapps` module requires NodeJS.
You can exclude building them by running `mvn clean install -pl '!webapps,!webapps/assembly'`.

Integration tests (e.g. tests that run in an actual application server) are usually not part of the default Maven profiles. If you think they are relevant to your contribution, please ask us in the ticket, on the forum or in your pull request for how to run them. Smaller contributions usu