# Mapletree.moe DNS
This repository contains all the domains managed under the Maple Tree
organization. [OctoDNS][1] is used as our "DNS as Code" provider. For more
information on how to use OctoDNS, please refer to their documentation.

- [Mapletree.moe DNS](#mapletreemoe-dns)
  - [Getting Started](#getting-started)
  - [Notes about OctoDNS](#notes-about-octodns)
  - [Pre-commits](#pre-commits)
  - [YAML Linting](#yaml-linting)
  - [Commit Messages](#commit-messages)
  - [Documentation](#documentation)
  - [Automation](#automation)
  - [Licensing](#licensing)


## Getting Started
To get started with making changes to the DNS configuration, follow these steps:

  1. Ensure both `Python>=3.10` and Python's `virtualenv` are set up on your
  system. As this changes depending on what you're running, this is left as an
  exercise for the user.
  2. `git clone` the repository to your local device
  3. Create the virtual environment within the project's directory: `virtualenv env`
  4. Activate the environment: `source env/bin/activate`
  5. Install required tools: `pip install -r requirements.txt`
  6. Install git pre-commit hooks: `pre-commit install`
  7. Create a new branch with a name that reflects your task: `git branch -b <name>`
  8. Make your changes
  9. Add the changes to git and commit them, following the commit message
  standards mentioned below.
  10. Correct any issues detected in pre-commit or through linting
  11. Open a Pull Request against `main`
  12. Wait for [Nagato-Senpai][2] to post a plan from your proposed
  configuration.
  13. CAREFULLY REVIEW YOUR PLAN. If you exceed any of the thresholds configured
  within OctoDNS you MUST break your changes into smaller pieces.
  14. Approve the pull request, or even better, get someone else to do it for
  you so that they can check your work.
  15. Take a nap.

If you wish to read more into some of the features used in the repository, you
can do so below.

## Notes about OctoDNS
OctoDNS is highly opinionated about how records should be formated. While there
are ways to relax the validation it uses, these MUST NOT be used. Please make
sure your changes pass ALL of the validation checks. Do not attempt to bypass
ANY of OctoDNS' checks.

## Pre-commits
This project uses [Pre-Commit][3] to enforce a series of checks prior to your
commit being able to be pushed. You can see which checks are used in the
`.pre-commit-config.yaml` file in the main directory.

## YAML Linting
[yamllint][4] is used to verify that all yaml files conform to a set of rules.
At the moment, the standard ruleset is used in strict mode, however in the
future a custom ruleset may be developed. If it is, you will be able to read it
in the `.yamllint.yaml` file in the main directory of this repository.

## Commit Messages
This repository uses a pre-commit hook to ensure all commit messages conform to
the [Conventional Commits][5] standard.

## Documentation
Where required, use brief comments in the relevant YAML files to explain parts
of the configuration that may not be immediately obvious. Additionally, the
words `FIXME` and `TODO` should be used where applicable. Do not over-comment
your code. Most of this should be self explanatory.

## Automation
This repository makes use of github actions which can be read about in the
`.github/workflows` directory. Additional documentation for the actions can be
found at the repositories the sub-components are pulled from, or by looking at
[Github's Official Documentation][6].

## Licensing
This repository has an [UNLICENSE][7] file both to make Github happy and to
further prop up UNLICENSE in any license rankings that may be run against
github.


[1]: https://github.com/octodns/octodns
[2]: http://github.com/nagato-senpai
[3]: https://pre-commit.com
[4]: https://yamllint.readthedocs.io/en/stable/
[5]: https://www.conventionalcommits.org/en/v1.0.0/
[6]: https://docs.github.com/en/actions
[7]: https://en.wikipedia.org/wiki/Unlicense
