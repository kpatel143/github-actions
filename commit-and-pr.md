# [Conventional commit](#cs)

It is specification that provides set of rules for creating explicit commit history. It makes easier for developers to contribute, by allowing them to explore a more structured commit history. Also it allow some automation like
automatic CHANGELOGs generation or automatic version bumps.

Normal structure look like this:
`type(scope?): subject`

- type: build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test
- scope: project name, issue id
- subject: description of what have been done

Some examples would be:

`chore: run tests on expert-chat ci`
`fix(BDS-1234): send X-USER-ID header`

## Implementation

### [commitlint](https://github.com/conventional-changelog/commitlint)

- enforce/warn configurable lint rules for following conventional commit.

![alt text](commitlint.png "Title")

- tooling (helper): [Commitizen](https://commitizen.github.io/cz-cli/) for CLI and VScode

  ![Alt text](https://github.com/commitizen/cz-cli/raw/master/meta/screenshots/add-commit.png)

- also with [JIRA support](https://www.npmjs.com/package/@digitalroute/cz-conventional-changelog-for-jira?activeTab=readme)

  ![alt text](jira-commit.png "Title")

  `type(scope): JIRA-1234 commit subject`

# Pull Requests guidelines - Enforce!

### [mergeable](https://mergeable.readthedocs.io/en/latest/index.html)

- define configurable rules in yml
- don't allow PR with empty description
- don't allow PR with not proper title
  ![alt text](failing-check.png "Title")
  ![alt text](failing-detail.png "Title")

### Working example: https://github.com/kpatel143/github-actions/pull/10
Uberbot already contains mergeable config: https://github.tools.sap/dsx/uberbot/blob/85ee6ecd42359bb6c67e0bdf28efc74547ce461b/.github/mergeable.yml


Rules: 
- description should not be empty
- title should follows [Conventional commit](#cs)


# Contribution guidelines
- single source of truth.
- for on-boarding and follow practice
Requirment levels are referring to: https://datatracker.ietf.org/doc/html/rfc2119

## Commits
- [MUST] use [Conventional commit](#cs) for message of commits. (can be enforced with [commitlint](https://github.com/conventional-changelog/commitlint))
- [MUST] contains a meaningful message
- [MUST] do small and frequent commits
  -  Advantages:
    -  easy to review PR with lot of changes.
    -  easy to rollback specific changes, while working on big refacoring/feature
## Pull Requests
- [MUST] small and frequent Pull Requests.
  - When you did some refactoring along with your feature, you are encouraged to open a separate pull request solely for this refactoring.
  - Advantages
    - it prevent loosing your work, in-case of hardware failure.
    - peers can get changes sonner and can work in parallel.
    - less conflict for peers.
- [MUST] follow [Conventional commit](#cs) in Pull Requests title
- [MUST] add description to Pull Requests to educate reviewer
## Reviewer assignment
  - [MUST-NOT] use `.CODEOWNERS` for knwon approval process. (ex. translation)
  - [SHOULD] use peers of same epic in PR reviews to make them aware about code-changes
  - [MAY] use whole scrum team as reviewer for specific change that everyone must know
  - [MUST] in-case of multiple reviewer, comment specific reviewer, who reponsible to do review.
