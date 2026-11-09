## Describe your changes

<!-- Summary of the changes. -->
<!-- Please also include relevant motivation and context. -->
<!-- List any dependencies that are required for this change. -->

## Issue Link

<!-- Link to the relevant issue or task, if applicable (e.g. `closes #00` or `solves #00`) -->

## Type of change

- [ ] 🐛 Bug fix (non-breaking change that fixes an issue)
- [ ] ✨ New feature (non-breaking change that adds functionality)
- [ ] 💥 Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] 🧹 Maintenance / Refactoring (repo cleanup, chore, CI/CD, dependencies)
- [ ] 📖 Documentation (Addition or improvements to documentation)

## Checklist before requesting a review

- [ ] My branch is up-to-date with the target branch (`staging`) — if not, update your fork with changes from `staging` (use `git pull --rebase upstream staging` if possible).
- [ ] I have performed a self-review of my code.
- [ ] I have verified code hygiene locally:
  - `ruff format --check .`
  - `ruff check .`
- [ ] For any new/modified functions or classes, I have added docstrings and type annotations that clearly describe purpose, expected inputs, and returned values.
- [ ] I have placed in-line comments to clarify the intent of any complex passages of my code.
- [ ] I have updated the README or documentation to cover introduced changes where applicable.
- [ ] If this PR changes contributor workflow, I have updated `CONTRIBUTING.md` / `AGENTS.md`.
- [ ] I have added tests that prove my fix is effective or that my feature works (`pytest`).
- [ ] I have given the PR a title that clearly describes the change, written in imperative form following Conventional Commits (e.g., `feat(agent): ...`, `fix(telemetry): ...`).
- [ ] I have requested a reviewer and an assignee (assignee is responsible for merging). This applies only if you have write access to the repo; otherwise feel free to tag a maintainer.

## Checklist for reviewers

Each PR comes with its own improvements and flaws. The reviewer should check the following:
- [ ] The code is readable and adheres to project architectural guidelines
- [ ] The code is well tested
- [ ] The code is documented (including return types and parameters)
- [ ] The code is easy to maintain

## Author checklist after completed review

- [ ] I have added a line to `CHANGELOG.md` under `[Unreleased]` describing this change, in a section reflecting the type of change:
  - *Added*: when you have added new functionality
  - *Changed*: when default behavior of the code has been changed
  - *Fixed*: when your contribution fixes a bug
  - *Maintenance*: when your contribution relates to repo maintenance, CI/CD, or documentation

## Checklist for assignee

- [ ] PR is up to date with the `staging` base branch
- [ ] All tests and CI checks pass
- [ ] The PR is assigned to the next milestone (e.g., `v1.0.0`). If not, propose it for a future milestone (`v1.0.0 (proposed)`).
- [ ] Author has added an entry to `CHANGELOG.md`
- [ ] Once the PR is ready to be merged, squash commits and merge the PR into `staging`.
