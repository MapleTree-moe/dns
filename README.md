# Mapletree.moe DNS
This repository contains the code for deploying all of the DNS records for
domains under the MapleTree Organization.

- [Mapletree.moe DNS](#mapletreemoe-dns)
  - [Getting Started](#getting-started)
  - [Software used](#software-used)
  - [Commit Messages](#commit-messages)
  - [Workflows](#workflows)
  - [Comments](#comments)
  - [Licensing](#licensing)

## Getting Started
To make changes to the domain records, follow the steps below:

  1. Make sure your environment has `python>=3.10` and `virtualenv` available.
  As this differs from environment to environment, getting this part set up is
  left as an exercise for the user.
  2. Clone the repository: `git clone`
  3. Create the virtualenv: `virtualenv env`
  4. Activate the virtualenv: `source env/bin/activate`
  5. Install requirements: `pip install -r requirements.txt`
  6. Install pre-commit hooks: `pre-commit install`
  7. Create a new branch to work inside: `git checkout -b <branch name>`
  8. Make your changes, see relevant notes below.
  9. Commit your changes. If there are any warnings or errors, correct them.
  10. Push your changes to the repository `git push`
  11. Open a pull request, and wait for [nagato-senpai][1] to report back with
  the completed plan for the update.
  12.  Approve the PR, or get someone else to review and approve it for you.

For more information on workflow, see below.

## Software used
The DNS records are managed through [OctoDNS][2] which has robust documentation
and tutorials that have been made available by several users such as
[DigitalOcean][3]. This allows DNS to be managed as code and deployed
accordingly.

For linting and checks, [Pre-Commit][4] and [yamllint][5] are used. If you wish
to know more about what checks are part of pre-commit, you can refer to
`.pre-commit-config.yaml` at the base of the repository. For the moment,
yamllint is simply used with the default settings but set to strict mode. If a
custom ruleset is developed in the future, it will be found at `.yamllint.yaml`.

## Commit Messages
Commit Messages are required to comply with the [Conventional Commits][6]
standard.

## Workflows
There are two main workflows used, `octodns-validate` and `octodns-deploy`.
Validate is ran against all PR requests and results in `nagato-senpai`
generating a markdown formatted list of changes that will be posted to the pull
request.

**NOTE**: If the workflow runs, you are making too many changes at one time. It
is best for changes to be made in small groups with a single unified reason.
For example, instead of adding three new services at once, please make one PR
for each new service added.

## Comments
As the configuration is written in YAML, comments should be primarily reserved
for things that are not self evident. Additionally, please make use of `FIXME`
and `TODO` to indicate where effort should be focused in the codebase.

## Licensing
While there's not really anything here that qualifies as software, the repo is
licensed under [UNLICENSE][7] to help support the project and move it higher up
the list of used licenses here on Github.

[1]: https://github.com/nagato-senpai
[2]: https://github.com/octodns/octodns
[3]: https://www.digitalocean.com/community/tutorials/how-to-deploy-and-manage-your-dns-using-octodns-on-ubuntu-18-04
[4]: https://pre-commit.com
[5]: https://yamllint.readthedocs.io
[6]: https://www.conventionalcommits.org/en/v1.0.0/
[7]: https://unlicense.org
