# Conventional commit

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

- tooling (helper): [Commitizen](https://commitizen.github.io/cz-cli/)
  ![Alt text](https://github.com/commitizen/cz-cli/raw/master/meta/screenshots/add-commit.png)
